async function tursoFetch(sql, args=[]) {
  const res = await fetch(process.env.TURSO_URL, {
    method:'POST',
    headers:{'Authorization':'Bearer '+process.env.TURSO_TOKEN,'Content-Type':'application/json'},
    body: JSON.stringify({ requests: [{ type:'execute', stmt:{ sql, args: args.map(v=>({type:'text', value: String(v ?? '')})) } }, {type:'close'}] })
  });
  const j = await res.json(); 
  if(!res.ok) console.error(JSON.stringify(j));
  return j.results?.[0]?.response?.result || {cols:[], rows:[]};
}
function rowsToObjects(r){ if(!r||!r.cols) return []; const c=r.cols.map(x=>x.name); return r.rows.map(row=>{ const o={}; row.forEach((cell,i)=>{ o[c[i]]=cell?cell.value:null; }); return o; }); }

(async()=>{
  const { Resend } = await import('resend');
  const resend = new Resend(process.env.RESEND_API_KEY);
  const data = rowsToObjects(await tursoFetch("SELECT id, carta_completa, frase_destacada, email_futuro, talisman_tipo FROM cartas_futuro WHERE date(fecha_devolucion) <= date('now') AND quiere_email=1 AND email_enviado=0"));
  console.log(`Cartas a enviar: ${data.length}`);
  for(const row of data){
    try{
      await resend.emails.send({
        from: 'Gael <onboarding@resend.dev>',
        to: row.email_futuro,
        subject: `Tu carta de hace 3 años — ${row.talisman_tipo || 'talismán'}`,
        html: `<div style="font-family:Georgia,serif;max-width:600px;line-height:1.7;color:#0b0a13"><p>Hace 3 años escribiste:</p><blockquote style="border-left:2px solid #c9a35f;padding-left:1rem;font-style:italic;color:#17131f">“${row.frase_destacada||''}”</blockquote><hr style="border:none;border-top:1px solid #e9e2d0;margin:1.5rem 0"><div style="white-space:pre-wrap">${row.carta_completa||''}</div><br><p style="color:#8f8272;font-size:0.8em;margin-top:2rem">— Universo Gael, Aventuras Introspectivas<br>La gruta guardó tu carta 3 años, hoy vuelve a ti.</p></div>`
      });
      await tursoFetch("UPDATE cartas_futuro SET email_enviado=1 WHERE id=?", [row.id]);
      console.log(`Enviada a ${row.email_futuro} id=${row.id}`);
    }catch(e){ console.error(`Error enviando id=${row.id}`, e); }
  }
})();
