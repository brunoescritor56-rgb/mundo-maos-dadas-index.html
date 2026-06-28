# mundo-maos-dadas-index.html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<title>Brunno Rammos — Portal de Projetos</title>
<meta name="description" content="Portal de projetos de Brunno Rammos: política, cultura, esporte, energia, economia, direito, saúde e solidariedade — ideias que atravessam fronteiras.">
<meta name="theme-color" content="#040408">
<link rel="manifest" href="manifest.webmanifest">
<link rel="icon" href="icons/favicon.png" type="image/png">
<link rel="apple-touch-icon" href="icons/icon-192.png">
<meta name="mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-title" content="Mãos Dadas">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,600;0,9..144,700;1,9..144,500&family=Archivo:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --void:#040408;
    --ink:#EAF2FA;
    --muted:#8A98AB;
    --line:rgba(255,255,255,.10);
    --card:rgba(255,255,255,.035);

    --globe-pale:#EAF6FF;
    --globe-blue:#4FA3E3;
    --globe-deep:#1A4E83;
    --corona-core:#FFE8AA;
    --corona-warm:#FFB347;

    --accent:#E2574D; /* atualizado por aba ativa */

    --globe: clamp(208px, 56vw, 320px);
    --stage: clamp(320px, 86vw, 500px);

    --display:'Fraunces', Georgia, 'Times New Roman', serif;
    --body:'Archivo', system-ui, -apple-system, 'Segoe UI', sans-serif;
  }

  *{box-sizing:border-box;}
  html{ -webkit-text-size-adjust:100%; }
  body{
    margin:0;
    background:var(--void);
    color:var(--ink);
    font-family:var(--body);
    line-height:1.55;
    overflow-x:hidden;
    -webkit-font-smoothing:antialiased;
  }

  /* ---------- estrelas de fundo ---------- */
  .sky{ position:fixed; inset:0; z-index:0; pointer-events:none; }
  .star{ position:absolute; width:2px; height:2px; border-radius:50%;
    background:#fff; opacity:.5; animation:twinkle 4s ease-in-out infinite; }
  @keyframes twinkle{ 0%,100%{opacity:.18} 50%{opacity:.85} }

  .wrap{ position:relative; z-index:1; max-width:1040px; margin:0 auto;
    padding:calc(env(safe-area-inset-top,0px) + clamp(28px,7vw,64px)) clamp(18px,5vw,40px) calc(env(safe-area-inset-bottom,0px) + 60px); text-align:center; }

  /* ---------- topo ---------- */
  .eyebrow{ font-size:12px; letter-spacing:.34em; text-transform:uppercase;
    color:var(--muted); font-weight:600; margin:0 0 6px; }

  /* ---------- palco / globo ---------- */
  .stage{ position:relative; width:var(--stage); height:var(--stage);
    margin:clamp(8px,3vw,22px) auto clamp(6px,2vw,18px); }
  .stage > *{ position:absolute; top:50%; left:50%; transform:translate(-50%,-50%); }

  .rays{ width:calc(var(--globe)*1.95); aspect-ratio:1; border-radius:50%;
    background:conic-gradient(from 0deg,
      rgba(255,224,150,.0) 0deg, rgba(255,224,150,.16) 12deg, rgba(255,224,150,0) 24deg);
    -webkit-mask:radial-gradient(circle, #000 32%, transparent 70%);
            mask:radial-gradient(circle, #000 32%, transparent 70%);
    opacity:.55; animation:spin 90s linear infinite; }

  .corona{ width:calc(var(--globe)*2.05); aspect-ratio:1; border-radius:50%;
    background:radial-gradient(circle,
      rgba(255,232,170,.55) 0%,
      rgba(255,179,71,.30) 26%,
      rgba(120,190,255,.18) 46%,
      rgba(80,150,230,.06) 60%,
      transparent 72%);
    filter:blur(4px); animation:breathe 7.5s ease-in-out infinite; }

  .globe{ width:var(--globe); height:var(--globe); border-radius:50%;
    overflow:hidden;
    background:
      radial-gradient(circle at 36% 30%,
        var(--globe-pale) 0%, #B4DEF8 12%, var(--globe-blue) 44%, #2E78BE 70%, var(--globe-deep) 100%);
    box-shadow:
      0 0 64px 12px rgba(150,205,255,.45),
      0 0 120px 30px rgba(255,200,120,.18);
  }
  .globe::after{ content:""; position:absolute; inset:0; border-radius:50%; z-index:3;
    box-shadow:
      inset -22px -28px 60px rgba(8,36,70,.70),
      inset 20px 16px 46px rgba(255,255,255,.30);
    pointer-events:none; }
  .equator{ position:absolute; left:6%; right:6%; top:50%; height:0; z-index:2;
    border-top:1px dashed rgba(230,245,255,.30); transform:translateY(-50%); }
  .flag{ position:absolute; z-index:2; transform:translate(-50%,-50%);
    font-size:clamp(12px,3.4vw,17px); line-height:1;
    filter:drop-shadow(0 1px 2px rgba(0,0,0,.45)); opacity:.94; }

  .people{ width:calc(var(--globe)*1.62); aspect-ratio:1; overflow:visible;
    animation:spin 110s linear infinite; }
  .people .arm{ stroke:rgba(255,255,255,.55); stroke-width:1.5; stroke-linecap:round; }
  .people .chain{ fill:none; stroke:rgba(255,255,255,.16); stroke-width:1; }

  /* ---------- título ---------- */
  .title{ font-family:var(--display); font-weight:600;
    font-size:clamp(36px,9vw,76px); line-height:.98; letter-spacing:-.015em;
    margin:clamp(6px,2vw,14px) 0 10px;
    background:linear-gradient(180deg,#fff 0%, #cfe0f0 100%);
    -webkit-background-clip:text; background-clip:text; color:transparent; }
  .tagline{ color:var(--muted); font-size:clamp(15px,2.4vw,18px);
    max-width:34ch; margin:0 auto; }

  /* ---------- abas ---------- */
  .tabs{ display:flex; flex-wrap:wrap; justify-content:center; gap:9px;
    margin:clamp(26px,5vw,40px) auto clamp(22px,4vw,32px); }
  .tab{ font-family:var(--body); font-size:12.5px; font-weight:600;
    letter-spacing:.12em; text-transform:uppercase; cursor:pointer;
    color:var(--muted); background:transparent;
    border:1px solid var(--line); border-radius:999px;
    padding:9px 16px; transition:.25s ease; }
  .tab:hover{ color:var(--ink); border-color:rgba(255,255,255,.28); transform:translateY(-2px); }
  .tab[aria-selected="true"]{
    color:#06080c; border-color:transparent;
    background:var(--tab-accent); box-shadow:0 6px 22px -8px var(--tab-accent); }
  .tab:focus-visible{ outline:2px solid var(--ink); outline-offset:3px; }

  /* ---------- painel ---------- */
  .panel{ text-align:left; }
  .panel-head{ display:flex; align-items:baseline; gap:14px; flex-wrap:wrap;
    border-bottom:1px solid var(--line); padding-bottom:16px; margin-bottom:24px; }
  .panel-name{ font-family:var(--display); font-weight:600;
    font-size:clamp(24px,5vw,38px); letter-spacing:-.01em; margin:0;
    position:relative; padding-left:18px; }
  .panel-name::before{ content:""; position:absolute; left:0; top:.18em; bottom:.18em;
    width:5px; border-radius:3px; background:var(--accent); }
  .panel-intro{ color:var(--muted); font-size:15.5px; max-width:52ch; margin:0; }

  .cards{ display:grid; gap:16px; grid-template-columns:repeat(3,1fr); }
  .ccard{ background:var(--card); border:1px solid var(--line); border-radius:16px;
    padding:22px 22px 24px; position:relative; overflow:hidden; transition:.28s ease; }
  .ccard::before{ content:""; position:absolute; left:0; top:0; right:0; height:3px;
    background:var(--accent); opacity:.8; transform:scaleX(.0); transform-origin:left;
    transition:transform .35s ease; }
  .ccard:hover{ transform:translateY(-4px); border-color:rgba(255,255,255,.20);
    box-shadow:0 18px 40px -22px var(--accent); }
  .ccard:hover::before{ transform:scaleX(1); }
  .ccard h3{ font-family:var(--display); font-weight:600; font-size:18.5px;
    margin:0 0 8px; letter-spacing:-.005em; }
  .ccard p{ color:var(--muted); font-size:14.5px; margin:0; }

  /* ---------- rodapé ---------- */
  .foot{ margin-top:clamp(48px,8vw,72px); padding-top:24px;
    border-top:1px solid var(--line); display:flex; justify-content:space-between;
    flex-wrap:wrap; gap:8px; color:var(--muted); font-size:13px; }
  .foot strong{ color:var(--ink); font-weight:600; }

  /* ---------- animações ---------- */
  @keyframes spin{ to{ transform:translate(-50%,-50%) rotate(360deg); } }
  @keyframes breathe{ 0%,100%{ transform:translate(-50%,-50%) scale(1); opacity:.9 }
                      50%{ transform:translate(-50%,-50%) scale(1.05); opacity:1 } }

  .panel[data-anim]{ animation:rise .45s ease both; }
  @keyframes rise{ from{ opacity:0; transform:translateY(10px); } to{ opacity:1; transform:none; } }

  @media (max-width:760px){ .cards{ grid-template-columns:1fr; } }
  @media (max-width:520px){ .tab{ padding:8px 13px; font-size:11.5px; letter-spacing:.08em; } }

  @media (prefers-reduced-motion:reduce){
    .people,.rays,.corona,.star,.panel[data-anim]{ animation:none !important; }
    .corona{ transform:translate(-50%,-50%) scale(1.02); }
  }
</style>
</head>
<body>
  <div class="sky" id="sky" aria-hidden="true"></div>

  <main class="wrap">
    <p class="eyebrow">Brunno Rammos · Portal de Projetos</p>

    <div class="stage" aria-hidden="true">
      <div class="rays"></div>
      <div class="corona"></div>
      <div class="globe">
        <div class="equator"></div>
        <div id="flags"></div>
      </div>
      <svg class="people" id="people" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg"></svg>
    </div>

    <h1 class="title">O mundo de<br>mãos dadas</h1>
    <p class="tagline">Sete frentes, um só horizonte: ideias que atravessam fronteiras.</p>

    <nav class="tabs" id="tabs" role="tablist" aria-label="Áreas de projetos"></nav>

    <section class="panel" id="panel" role="tabpanel" tabindex="0" aria-live="polite"></section>

    <footer class="foot">
      <span><strong>Brunno Rammos</strong> — Minas Gerais, Brasil</span>
      <span>Um globo, muitas mãos.</span>
    </footer>
  </main>

<script>
/* ===== dados das áreas ===== */
const THEMES = [
  { id:'politica', label:'Política', accent:'#E2574D',
    intro:'Propostas legislativas e desenho institucional para um Estado mais soberano e responsável.',
    cards:[
      {t:'PEC do Fundo Soberano de Defesa', d:'Financiamento permanente para a proteção das fronteiras e da soberania nacional.'},
      {t:'Lei da Responsabilidade Democrática', d:'Prestação de contas e freios institucionais contra rupturas do Estado de Direito.'},
      {t:'PLC de Defesa da Democracia', d:'Perda de registro partidário e inelegibilidade por atos atentatórios à ordem democrática.'},
    ]},
  { id:'cultura', label:'Cultura', accent:'#C77DFF',
    intro:'Literatura, narrativa e a marca autoral Brunno Rammos.',
    cards:[
      {t:'Marietta Cata-Cruz', d:'Romance do catálogo autoral de Brunno Rammos.'},
      {t:'Tema de Aila', d:'Obra literária que integra o catálogo do autor.'},
      {t:'Candelária', d:'Narrativa que entrelaça fé, memória e esperança.'},
      {t:'A Relíquia da Justiça', d:'Ficção que une narrativa e reflexão sobre o Direito.'},
      {t:'Campanha Brunno Rammos', d:'Reels e ações de marketing para aproximar leitores das obras.'},
      {t:'AD | 360 | BR', d:'Portal de notícias brasileiro com curadoria e integração de IA.'},
    ]},
  { id:'esporte', label:'Esporte', accent:'#4ADE80',
    intro:'Scouting, mercado, governança e inclusão no desporto.',
    cards:[
      {t:'Inteligência de Mercado do Cruzeiro', d:'Relatórios de scout e monitoramento da janela de transferências.'},
      {t:'Liga Mundial de Clubes (CMIC)', d:'Competição global de 64 clubes com elegibilidade e fair play financeiro.'},
      {t:'Reforma das Regras da FIFA', d:'Propostas sobre delegações, impedimento e proteção do atleta.'},
      {t:'Reintegração do Futebol Russo', d:'Requerimentos à FIFA e à UEFA pela revogação da suspensão de seleções e clubes.'},
      {t:'PNID — Programa Nacional de Inclusão Desportiva', d:'PPP para modernizar arenas públicas e impulsionar o desenvolvimento regional.'},
    ]},
  { id:'energia', label:'Energia', accent:'#FFC65C',
    intro:'Soberania energética, infraestrutura e transição sustentável.',
    cards:[
      {t:'Soberania Marítima e Energética', d:'Marco para os recursos do mar e da costa brasileira.'},
      {t:'Holding de Engenharia (HEBIE)', d:'Reconstrução da capacidade nacional de grandes obras.'},
      {t:'Transição Verde', d:'Regulação ambiental e o debate sobre o fim do glifosato.'},
    ]},
  { id:'economia', label:'Economia', accent:'#46C9C9',
    intro:'Política fiscal, moeda, soberania monetária, inovação e desenvolvimento regional.',
    cards:[
      {t:'Diagnóstico Fiscal do Governo', d:'Análise das contas públicas em planilha de múltiplas abas.'},
      {t:'PEC da Soberania Monetária do BC', d:'Mandato dual e vedação à subordinação externa da política monetária.'},
      {t:'Decreto do Pix Soberano', d:'Diretrizes e comitê interministerial para a infraestrutura de pagamentos.'},
      {t:'SAAC — Sistema de Âncora Aurífera Certificada', d:'Instrumento monetário lastreado em ouro certificado contra a inflação e o garimpo ilegal.'},
      {t:'PNPIA — Propriedade Intelectual Acadêmica', d:'Subsídio e patenteamento acelerado de pesquisas com recursos públicos.'},
      {t:'Investimento Nórdico no Sul', d:'Atração de capital para o desenvolvimento regional.'},
    ]},
  { id:'direito', label:'Direito', accent:'#6FA8FF',
    intro:'Direitos fundamentais, povos tradicionais e desenho constitucional.',
    cards:[
      {t:'Regularização Fundiária', d:'Lei de terras para povos e comunidades tradicionais (CNPCT).'},
      {t:'Direitos da Neurodivergência', d:'Documentos de proteção e inclusão de pessoas neurodivergentes.'},
      {t:'Proteção ao Descanso e ao Silêncio', d:'Marco legal pelo direito ao sossego e à saúde pública.'},
    ]},
  { id:'saude', label:'Saúde', accent:'#2FBF9E',
    intro:'Soberania farmacêutica, cuidado e políticas públicas de saúde.',
    cards:[
      {t:'BIOFAR-BR — Estatal de Bioativos Farmacêuticos', d:'Cultivo de canabidiol e fármacos da floresta para abastecer o SUS.'},
      {t:'FNAPE — Psicologia na Enfermagem', d:'Quadro de psicologia nas escolas e na formação em enfermagem.'},
      {t:'Banimento do Glifosato', d:'Medida pela saúde pública e proteção ambiental.'},
    ]},
  { id:'fe', label:'Fé e Solidariedade', accent:'#FF8FA3',
    intro:'Cuidado, comunidade e a dimensão espiritual da vida pública.',
    cards:[
      {t:'Fundo FUNACTER', d:'Financiamento de comunidades terapêuticas e acolhimento.'},
      {t:'Cuba, Encruzilhada do Mundo', d:'Polo internacional de eventos com ações afirmativas sociais, econômicas e desportivas.'},
      {t:'Teologia e Pensamento', d:'Reflexões sobre fé, história e expressão da doutrina.'},
      {t:'Iconografia e Devoção', d:'Pesquisa sobre fé, cultura e expressão popular.'},
    ]},
];

/* ===== estrelas ===== */
(function(){
  const sky = document.getElementById('sky');
  let html = '';
  for(let i=0;i<74;i++){
    const x=(Math.random()*100).toFixed(2), y=(Math.random()*100).toFixed(2);
    const s=(Math.random()*1.6+0.6).toFixed(2);
    const o=(Math.random()*0.5+0.2).toFixed(2);
    const d=(Math.random()*4).toFixed(2);
    html += `<span class="star" style="left:${x}%;top:${y}%;width:${s}px;height:${s}px;opacity:${o};animation-delay:${d}s"></span>`;
  }
  sky.innerHTML = html;
})();

/* ===== bandeiras por hemisfério ===== */
(function(){
  const north = [
    {f:'🇺🇸',x:30,y:24},{f:'🇨🇦',x:53,y:18},{f:'🇩🇪',x:66,y:30},
    {f:'🇯🇵',x:78,y:39},{f:'🇫🇷',x:44,y:35},{f:'🇨🇳',x:21,y:40}
  ];
  const south = [
    {f:'🇧🇷',x:38,y:64},{f:'🇿🇦',x:60,y:70},{f:'🇦🇷',x:30,y:76},
    {f:'🇦🇺',x:72,y:61},{f:'🇮🇩',x:50,y:80},{f:'🇨🇱',x:22,y:58}
  ];
  const box = document.getElementById('flags');
  box.innerHTML = north.concat(south)
    .map(o=>`<span class="flag" style="left:${o.x}%;top:${o.y}%">${o.f}</span>`).join('');
})();

/* ===== pessoas de mãos dadas ===== */
(function(){
  const N=20, R=80, cx=100, cy=100;
  const colors=['#E54D4D','#E5824D','#E5B84D','#C8E54D','#7CD64D','#4DD679',
                '#4DD6C8','#4DAFE5','#4D7CE5','#6B4DE5','#9C4DE5','#C84DE5',
                '#E54DBE','#E54D8A','#E5704D','#D6B84D','#8AD64D','#4DC8B0',
                '#4D94E5','#A04DE5'];
  const reach = (Math.PI*R/N) - 1.0;
  let svg = `<circle class="chain" cx="${cx}" cy="${cy}" r="${R+2.6}"/>`;
  for(let i=0;i<N;i++){
    const a=(i/N)*Math.PI*2 - Math.PI/2;
    const x=(cx+R*Math.cos(a)).toFixed(2);
    const y=(cy+R*Math.sin(a)).toFixed(2);
    const deg=(a*180/Math.PI+90).toFixed(2);
    const c=colors[i%colors.length];
    svg += `<g transform="translate(${x},${y}) rotate(${deg})">
      <line class="arm" x1="2.2" y1="-2.6" x2="${reach.toFixed(2)}" y2="-2.6"/>
      <line class="arm" x1="-2.2" y1="-2.6" x2="${(-reach).toFixed(2)}" y2="-2.6"/>
      <path d="M-2.5,-3 L2.5,-3 L1.7,4.3 L-1.7,4.3 Z" fill="${c}"/>
      <circle cx="0" cy="-6.4" r="2.7" fill="${c}"/>
    </g>`;
  }
  document.getElementById('people').innerHTML = svg;
})();

/* ===== abas + painel ===== */
(function(){
  const tabsEl = document.getElementById('tabs');
  const panel = document.getElementById('panel');
  const root = document.documentElement;

  THEMES.forEach((t,i)=>{
    const b=document.createElement('button');
    b.className='tab'; b.textContent=t.label; b.role='tab';
    b.id='tab-'+t.id; b.setAttribute('aria-selected', i===0?'true':'false');
    b.style.setProperty('--tab-accent', t.accent);
    b.addEventListener('click', ()=>select(i));
    b.addEventListener('keydown', e=>{
      if(e.key==='ArrowRight'){ e.preventDefault(); select((i+1)%THEMES.length, true); }
      if(e.key==='ArrowLeft'){ e.preventDefault(); select((i-1+THEMES.length)%THEMES.length, true); }
    });
    tabsEl.appendChild(b);
  });

  function select(i, focus){
    const t=THEMES[i];
    root.style.setProperty('--accent', t.accent);
    [...tabsEl.children].forEach((b,j)=>b.setAttribute('aria-selected', j===i?'true':'false'));
    if(focus) tabsEl.children[i].focus();

    panel.removeAttribute('data-anim');
    void panel.offsetWidth; /* reinicia animação */
    panel.setAttribute('data-anim','1');
    panel.innerHTML = `
      <div class="panel-head">
        <h2 class="panel-name">${t.label}</h2>
        <p class="panel-intro">${t.intro}</p>
      </div>
      <div class="cards">
        ${t.cards.map(c=>`<article class="ccard"><h3>${c.t}</h3><p>${c.d}</p></article>`).join('')}
      </div>`;
  }

  select(0);
})();
</script>
<script>
/* ===== registro do service worker (PWA / offline) ===== */
if ('serviceWorker' in navigator) {
  window.addEventListener('load', function () {
    navigator.serviceWorker.register('service-worker.js').catch(function(){});
  });
}
</script>
</body>
</html>