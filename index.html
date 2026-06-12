<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover" />
<meta name="theme-color" content="#071a22" />
<meta name="apple-mobile-web-app-capable" content="yes" />
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent" />
<title>Rotaciones · ovi</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,500;9..144,600;9..144,700&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --bg0:#071a22; --bg1:#0a2530; --surface:#0f2c38; --surface2:#12343f;
    --border:rgba(255,255,255,.08); --text:#eaf6f8; --dim:#84a7b1; --faint:#557079;
    --sun:#ff7a4d; --teal:#2dd4bf;
  }
  *{box-sizing:border-box; -webkit-tap-highlight-color:transparent;}
  html,body{margin:0;}
  body{
    font-family:Inter,system-ui,sans-serif; color:var(--text);
    background:linear-gradient(180deg,var(--bg0),var(--bg1)); min-height:100vh;
    padding:0 16px calc(40px + env(safe-area-inset-bottom)); -webkit-font-smoothing:antialiased;
  }
  #app{max-width:460px; margin:0 auto;}
  .display{font-family:Fraunces,Georgia,serif;}
  .tnum{font-variant-numeric:tabular-nums;}
  .card{background:var(--surface); border:1px solid var(--border); border-radius:16px; padding:16px;}
  .label{font-size:12px; font-weight:600; letter-spacing:.06em; text-transform:uppercase; color:var(--dim);}
  button{font-family:inherit;}
  .tap{transition:transform .12s ease, background .2s ease, border-color .2s ease;}
  .tap:active{transform:scale(.97);}
  .fade{animation:fade .28s ease both;}
  @keyframes fade{from{opacity:0; transform:translateY(6px);} to{opacity:1; transform:translateY(0);}}
  @keyframes toast{from{opacity:0; transform:translate(-50%,12px);} to{opacity:1; transform:translate(-50%,0);}}
  input[type=date]{color-scheme:dark; font-family:inherit;}
  ::-webkit-scrollbar{width:0; height:0;}
  table{border-collapse:separate; border-spacing:4px; width:100%;}
  @media (prefers-reduced-motion: reduce){*{animation:none!important; transition:none!important;}}
</style>
</head>
<body>
<div id="app"></div>

<script>
/* ---------------- Datos base ---------------- */
const ROTATIONS = [
  { id:"lagos",       label:"Lagos",       color:"#3b82f6" },
  { id:"olas",        label:"Olas",        color:"#22d3ee" },
  { id:"kraken",      label:"Kraken",      color:"#a855f7" },
  { id:"diablo",      label:"Diablo",      color:"#fb4565" },
  { id:"colchonetas", label:"Colchonetas", color:"#fbbf24" },
  { id:"calapirata",  label:"Calapirata",  color:"#34d399" },
];
const POSITIONS = [
  {id:"1",short:"1"},{id:"2",short:"2"},{id:"3",short:"3"},
  {id:"4",short:"4"},{id:"5",short:"5"},{id:"6",short:"6"},
  {id:"descanso",short:"D"},
];
const ROT_BY_ID = Object.fromEntries(ROTATIONS.map(r=>[r.id,r]));
const posLabel = id => id==="descanso" ? "Descanso" : "Posición "+id;

/* ---------------- Utilidades ---------------- */
const toKey = d => `${d.getFullYear()}-${String(d.getMonth()+1).padStart(2,"0")}-${String(d.getDate()).padStart(2,"0")}`;
const parseKey = k => { const [y,m,d]=k.split("-").map(Number); return new Date(y,m-1,d); };
const shiftKey = (k,n)=>{ const d=parseKey(k); d.setDate(d.getDate()+n); return toKey(d); };
const todayKey = ()=>toKey(new Date());
const fmtLong = k => new Intl.DateTimeFormat("es-ES",{weekday:"short",day:"numeric",month:"short",year:"numeric"}).format(parseKey(k));
const fmtShort = k => new Intl.DateTimeFormat("es-ES",{weekday:"short",day:"numeric",month:"short"}).format(parseKey(k));
const hexA = (hex,a)=>{ const n=parseInt(hex.slice(1),16); return `rgba(${(n>>16)&255},${(n>>8)&255},${n&255},${a})`; };

/* ---------------- Iconos ---------------- */
const ico = {
  waves:'<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M2 6c.6.5 1.2 1 2.5 1C7 7 7 5 9.5 5c2.6 0 2.4 2 5 2 1.3 0 1.9-.5 2.5-1"/><path d="M2 12c.6.5 1.2 1 2.5 1 2.5 0 2.5-2 5-2 2.6 0 2.4 2 5 2 1.3 0 1.9-.5 2.5-1"/><path d="M2 18c.6.5 1.2 1 2.5 1 2.5 0 2.5-2 5-2 2.6 0 2.4 2 5 2 1.3 0 1.9-.5 2.5-1"/></svg>',
  cal:'<svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="4" width="18" height="18" rx="2"/><path d="M16 2v4M8 2v4M3 10h18"/></svg>',
  chart:'<svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 3v18h18"/><rect x="7" y="11" width="3" height="6"/><rect x="13" y="7" width="3" height="10"/></svg>',
  left:'<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M15 18l-6-6 6-6"/></svg>',
  right:'<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M9 18l6-6-6-6"/></svg>',
  trash:'<svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 6h18M8 6V4h8v2M19 6l-1 14H6L5 6"/></svg>',
  pencil:'<svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 20h9M16.5 3.5a2.1 2.1 0 0 1 3 3L7 19l-4 1 1-4Z"/></svg>',
  check:'<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6L9 17l-5-5"/></svg>',
};

/* ---------------- Estado + persistencia ---------------- */
const STORE = "ovi-rotaciones-v1";
let state = { tab:"hoy", entries:{}, date:todayKey(), rot:null, pos:null };

function load(){ try{ state.entries = JSON.parse(localStorage.getItem(STORE)) || {}; }catch{ state.entries = {}; } }
function persist(){ try{ localStorage.setItem(STORE, JSON.stringify(state.entries)); }catch{} }

function syncDraft(){ const e=state.entries[state.date]; state.rot=e?e.rotation:null; state.pos=e?e.position:null; }

function toast(msg){
  const t=document.createElement("div"); t.className="display";
  t.innerHTML = ico.check + " " + msg;
  Object.assign(t.style,{position:"fixed",bottom:"28px",left:"50%",transform:"translateX(-50%)",
    background:"var(--teal)",color:"#04201c",padding:"11px 20px",borderRadius:"999px",
    fontWeight:"600",fontSize:"14px",fontFamily:"Inter,sans-serif",display:"flex",alignItems:"center",gap:"8px",
    boxShadow:"0 10px 30px rgba(0,0,0,.4)",animation:"toast .3s ease both",zIndex:50});
  document.body.appendChild(t); setTimeout(()=>t.remove(),2200);
}

/* ---------------- Estadísticas ---------------- */
function computeStats(){
  const rotC=Object.fromEntries(ROTATIONS.map(r=>[r.id,0]));
  const posC=Object.fromEntries(POSITIONS.map(p=>[p.id,0]));
  const heat={}; ROTATIONS.forEach(r=>POSITIONS.forEach(p=>heat[r.id+"|"+p.id]=0));
  Object.values(state.entries).forEach(({rotation,position})=>{
    if(rotC[rotation]!=null) rotC[rotation]++;
    if(posC[position]!=null) posC[position]++;
    if(heat[rotation+"|"+position]!=null) heat[rotation+"|"+position]++;
  });
  return {rotC,posC,heat,maxHeat:Math.max(1,...Object.values(heat))};
}

/* Donut SVG */
function polar(cx,cy,r,deg){ const a=(deg-90)*Math.PI/180; return [cx+r*Math.cos(a), cy+r*Math.sin(a)]; }
function annular(cx,cy,rO,rI,a0,a1){
  const large=(a1-a0)>180?1:0;
  const[x0,y0]=polar(cx,cy,rO,a0),[x1,y1]=polar(cx,cy,rO,a1),[x2,y2]=polar(cx,cy,rI,a1),[x3,y3]=polar(cx,cy,rI,a0);
  return `M${x0} ${y0} A${rO} ${rO} 0 ${large} 1 ${x1} ${y1} L${x2} ${y2} A${rI} ${rI} 0 ${large} 0 ${x3} ${y3} Z`;
}
function donut(data,total){
  const cx=100,cy=100,rO=90,rI=58; const active=data.filter(d=>d.value>0);
  let svg=`<svg viewBox="0 0 200 200" width="190" height="190">`;
  if(active.length===1){
    svg+=`<circle cx="${cx}" cy="${cy}" r="${(rO+rI)/2}" fill="none" stroke="${active[0].color}" stroke-width="${rO-rI}"/>`;
  } else {
    let ang=0;
    active.forEach(d=>{ const span=d.value/total*360; svg+=`<path d="${annular(cx,cy,rO,rI,ang,ang+span)}" fill="${d.color}"/>`; ang+=span+2; });
  }
  svg+=`</svg>`;
  return `<div style="position:relative;display:grid;place-items:center;height:200px">${svg}
    <div style="position:absolute;inset:0;display:grid;place-items:center;pointer-events:none;text-align:center">
      <div><div class="display" style="font-size:26px;font-weight:600">${total}</div>
      <div style="font-size:10px;color:var(--dim);letter-spacing:.08em">DÍAS</div></div></div></div>`;
}

/* ---------------- Vistas ---------------- */
function header(){
  return `<header class="fade" style="padding:22px 0 14px">
    <div style="display:flex;align-items:center;gap:10px">
      <div style="width:38px;height:38px;border-radius:12px;background:${hexA('#2dd4bf',.14)};display:grid;place-items:center;color:var(--teal)">${ico.waves}</div>
      <div><div class="display" style="font-size:22px;font-weight:600;line-height:1">Rotaciones</div>
      <div style="font-size:12px;color:var(--dim);margin-top:3px">ovi · socorrista · verano 2026</div></div>
    </div></header>`;
}
function tabs(){
  const items=[["hoy","Hoy",ico.cal],["stats","Estadísticas",ico.chart],["hist","Historial",ico.waves]];
  return `<nav style="display:flex;gap:6px;background:var(--surface);padding:5px;border-radius:14px;border:1px solid var(--border)">`+
    items.map(([id,label,icon])=>{ const on=state.tab===id;
      return `<button class="tap" data-tab="${id}" style="flex:1;border:none;cursor:pointer;border-radius:10px;padding:9px 4px;font-size:13px;font-weight:600;display:flex;align-items:center;justify-content:center;gap:6px;background:${on?'var(--sun)':'transparent'};color:${on?'#1a0f08':'var(--dim)'}">${icon}<span>${label}</span></button>`;
    }).join("")+`</nav>`;
}

function viewHoy(){
  const isToday = state.date===todayKey();
  const existing = state.entries[state.date];
  const rotBtns = ROTATIONS.map(r=>{ const on=state.rot===r.id;
    return `<button class="tap" data-rot="${r.id}" style="cursor:pointer;border-radius:12px;padding:11px 6px;font-size:13px;font-weight:600;background:${on?hexA(r.color,.18):'var(--surface2)'};color:${on?'#fff':'var(--dim)'};border:1.5px solid ${on?r.color:'transparent'}"><span style="display:inline-block;width:9px;height:9px;border-radius:99px;background:${r.color};margin-right:6px;vertical-align:middle"></span>${r.label}</button>`;
  }).join("");
  const posBtns = POSITIONS.map(p=>{ const on=state.pos===p.id; const wide=p.id==="descanso";
    return `<button class="tap" data-pos="${p.id}" style="cursor:pointer;border-radius:11px;height:46px;flex:${wide?'1 1 100%':'1 1 0'};min-width:${wide?'auto':'40px'};font-size:15px;font-weight:600;background:${on?'var(--teal)':'var(--surface2)'};color:${on?'#04201c':'var(--dim)'};border:1.5px solid ${on?'var(--teal)':'transparent'}">${wide?'Descanso':p.short}</button>`;
  }).join("");
  const ready = state.rot && state.pos;
  return `<section class="fade" style="margin-top:16px">
    <div class="card">
      <div style="display:flex;align-items:center;justify-content:space-between;gap:8px">
        <button class="tap" data-shift="-1" style="background:var(--surface2);border:none;border-radius:10px;width:40px;height:40px;cursor:pointer;display:grid;place-items:center;color:var(--text)">${ico.left}</button>
        <div style="text-align:center">
          <div class="display" style="font-size:19px;font-weight:600;text-transform:capitalize">${fmtLong(state.date)}</div>
          ${isToday?'<div style="font-size:11px;color:var(--teal);margin-top:2px">HOY</div>':''}
        </div>
        <button class="tap" data-shift="1" style="background:var(--surface2);border:none;border-radius:10px;width:40px;height:40px;cursor:pointer;display:grid;place-items:center;color:var(--text)">${ico.right}</button>
      </div>
      <div style="display:flex;align-items:center;gap:8px;margin-top:12px">
        <span style="font-size:12px;color:var(--dim)">Ir a fecha</span>
        <input type="date" id="dateInput" value="${state.date}" style="flex:1;background:var(--surface2);border:1px solid var(--border);color:var(--text);border-radius:9px;padding:7px 10px;font-size:13px">
      </div>
    </div>

    <div class="card" style="margin-top:12px">
      <div class="label">Rotación</div>
      <div style="display:grid;grid-template-columns:1fr 1fr 1fr;gap:8px;margin-top:10px">${rotBtns}</div>
    </div>

    <div class="card" style="margin-top:12px">
      <div class="label">Posición</div>
      <div style="display:flex;flex-wrap:wrap;gap:8px;margin-top:10px">${posBtns}</div>
    </div>

    <button class="tap" id="saveBtn" ${ready?'':'disabled'} style="width:100%;margin-top:16px;border:none;border-radius:14px;padding:15px;font-size:16px;font-weight:700;cursor:${ready?'pointer':'not-allowed'};background:${ready?'var(--sun)':'var(--surface2)'};color:${ready?'#1a0f08':'var(--faint)'}">${existing?'Actualizar día':'Guardar día'}</button>
    ${existing?`<button id="delMain" style="width:100%;margin-top:8px;background:transparent;border:none;color:var(--dim);font-size:13px;cursor:pointer;padding:8px;display:flex;align-items:center;justify-content:center;gap:6px">${ico.trash} Borrar registro de este día</button>`:''}
  </section>`;
}

function viewStats(){
  const total=Object.keys(state.entries).length;
  if(total===0) return empty("Sin datos todavía","Registra tu primer día en la pestaña Hoy y aquí verás tus porcentajes.");
  const s=computeStats();
  const rotData=ROTATIONS.map(r=>({...r,value:s.rotC[r.id]}));

  const rotLegend = rotData.map(r=>{ const pct=total?r.value/total*100:0;
    return `<div style="display:flex;align-items:center;gap:10px">
      <span style="width:10px;height:10px;border-radius:99px;background:${r.color};flex-shrink:0"></span>
      <span style="font-size:13px;flex:1">${r.label}</span>
      <span class="tnum" style="font-size:12px;color:var(--dim)">${r.value}d</span>
      <span class="tnum" style="width:44px;text-align:right;font-size:13px;font-weight:600;color:${r.color}">${pct.toFixed(0)}%</span>
    </div>`;}).join("");

  const posBars = POSITIONS.map(p=>{ const v=s.posC[p.id]; const pct=total?v/total*100:0;
    return `<div style="display:flex;align-items:center;gap:10px">
      <span style="width:74px;font-size:13px;flex-shrink:0">${p.id==='descanso'?'Descanso':'Pos. '+p.id}</span>
      <div style="flex:1;height:10px;border-radius:99px;background:rgba(255,255,255,.06);overflow:hidden">
        <div style="width:${pct}%;height:100%;border-radius:99px;background:${p.id==='descanso'?'var(--dim)':'var(--teal)'}"></div></div>
      <span class="tnum" style="width:56px;text-align:right;font-size:13px;color:var(--dim)"><b style="color:var(--text)">${pct.toFixed(0)}%</b> · ${v}</span>
    </div>`;}).join("");

  const head = `<tr><th></th>${POSITIONS.map(p=>`<th style="font-size:11px;color:var(--dim);font-weight:600;width:30px">${p.short}</th>`).join("")}</tr>`;
  const rows = ROTATIONS.map(r=>`<tr><td style="font-size:12px;color:${r.color};font-weight:600;padding-right:8px;white-space:nowrap">${r.label}</td>`+
    POSITIONS.map(p=>{ const v=s.heat[r.id+"|"+p.id]; const a=v===0?0:0.18+0.82*(v/s.maxHeat);
      return `<td style="height:34px;border-radius:7px;text-align:center;vertical-align:middle;font-size:12px;font-weight:700;font-variant-numeric:tabular-nums;background:${v===0?'rgba(255,255,255,.03)':hexA(r.color,a)};color:${v===0?'var(--faint)':(a>0.55?'#06141a':'#fff')};border:${v===0?'1px dashed rgba(255,255,255,.07)':'none'}">${v===0?'·':v}</td>`;
    }).join("")+`</tr>`).join("");

  return `<section class="fade" style="margin-top:16px;display:flex;flex-direction:column;gap:12px">
    <div class="card" style="text-align:center">
      <div class="display" style="font-size:48px;font-weight:600;line-height:1">${total}</div>
      <div style="color:var(--dim);font-size:13px;margin-top:4px">${total===1?'día registrado':'días registrados'} · verano 2026</div>
    </div>
    <div class="card">
      <div class="label">Por rotación</div>
      ${donut(rotData,total)}
      <div style="display:flex;flex-direction:column;gap:9px;margin-top:6px">${rotLegend}</div>
    </div>
    <div class="card">
      <div class="label">Por posición</div>
      <div style="display:flex;flex-direction:column;gap:11px;margin-top:12px">${posBars}</div>
    </div>
    <div class="card">
      <div class="label">Tablón de rotaciones</div>
      <div style="font-size:12px;color:var(--dim);margin:4px 0 12px">Veces que has empezado en cada combinación. Más intenso = más repetido.</div>
      <div style="overflow-x:auto"><table><thead>${head}</thead><tbody>${rows}</tbody></table></div>
    </div>
  </section>`;
}

function viewHist(){
  const keys=Object.keys(state.entries).sort().reverse();
  if(keys.length===0) return empty("Historial vacío","Aquí aparecerán todos los días que registres, del más reciente al más antiguo.");
  return `<section class="fade" style="margin-top:16px;display:flex;flex-direction:column;gap:8px">`+
    keys.map(k=>{ const e=state.entries[k]; const r=ROT_BY_ID[e.rotation];
      return `<div class="card" style="padding:13px;display:flex;align-items:center;gap:12px">
        <div style="width:6px;align-self:stretch;border-radius:99px;background:${r?r.color:'var(--dim)'}"></div>
        <div style="flex:1;min-width:0">
          <div style="font-size:14px;font-weight:600;text-transform:capitalize">${fmtShort(k)}</div>
          <div style="font-size:12px;color:var(--dim);margin-top:2px"><span style="color:${r?r.color:''}">${r?r.label:e.rotation}</span> · ${posLabel(e.position)}</div>
        </div>
        <button class="tap" data-edit="${k}" style="background:var(--surface2);border:none;border-radius:9px;width:36px;height:36px;cursor:pointer;display:grid;place-items:center;color:var(--dim);flex-shrink:0">${ico.pencil}</button>
        <button class="tap" data-del="${k}" style="background:var(--surface2);border:none;border-radius:9px;width:36px;height:36px;cursor:pointer;display:grid;place-items:center;color:var(--dim);flex-shrink:0">${ico.trash}</button>
      </div>`;}).join("")+`</section>`;
}

function empty(title,text){
  return `<div class="card fade" style="margin-top:16px;text-align:center;padding:40px 24px">
    <div style="width:52px;height:52px;border-radius:16px;background:${hexA('#2dd4bf',.12)};display:grid;place-items:center;margin:0 auto 14px;color:var(--teal)">${ico.waves}</div>
    <div class="display" style="font-size:20px;font-weight:600">${title}</div>
    <div style="color:var(--dim);font-size:13px;margin-top:8px;line-height:1.5">${text}</div></div>`;
}

/* ---------------- Render + eventos ---------------- */
function render(){
  let view = state.tab==="hoy"?viewHoy():state.tab==="stats"?viewStats():viewHist();
  document.getElementById("app").innerHTML = header()+tabs()+view;
  bind();
}
function bind(){
  document.querySelectorAll("[data-tab]").forEach(b=>b.onclick=()=>{ state.tab=b.dataset.tab; render(); });
  document.querySelectorAll("[data-shift]").forEach(b=>b.onclick=()=>{ state.date=shiftKey(state.date,+b.dataset.shift); syncDraft(); render(); });
  const di=document.getElementById("dateInput"); if(di) di.onchange=e=>{ if(e.target.value){ state.date=e.target.value; syncDraft(); render(); } };
  document.querySelectorAll("[data-rot]").forEach(b=>b.onclick=()=>{ state.rot=b.dataset.rot; render(); });
  document.querySelectorAll("[data-pos]").forEach(b=>b.onclick=()=>{ state.pos=b.dataset.pos; render(); });
  const sb=document.getElementById("saveBtn"); if(sb) sb.onclick=()=>{
    if(!state.rot||!state.pos) return;
    const had=!!state.entries[state.date];
    state.entries[state.date]={rotation:state.rot,position:state.pos}; persist();
    toast(had?"Día actualizado":"Día guardado"); render();
  };
  const dm=document.getElementById("delMain"); if(dm) dm.onclick=()=>{ delete state.entries[state.date]; persist(); syncDraft(); toast("Día borrado"); render(); };
  document.querySelectorAll("[data-edit]").forEach(b=>b.onclick=()=>{ state.date=b.dataset.edit; state.tab="hoy"; syncDraft(); render(); });
  document.querySelectorAll("[data-del]").forEach(b=>b.onclick=()=>{ delete state.entries[b.dataset.del]; persist(); toast("Día borrado"); render(); });
}

/* ---------------- Init ---------------- */
load(); syncDraft(); render();
</script>
</body>
</html>
