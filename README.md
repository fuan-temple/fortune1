# <!DOCTYPE html>
<html lang="zh-TW">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <title>車城 財氣鑑定所</title>
  <meta name="theme-color" content="#6b0000">
  <meta name="apple-mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
  <meta name="apple-mobile-web-app-title" content="財氣鑑定所">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+TC:wght@400;700;900&display=swap" rel="stylesheet">
  <style>
    *{box-sizing:border-box;margin:0;padding:0;}
    body{font-family:'Noto Serif TC','Microsoft JhengHei',serif;background:linear-gradient(160deg,#6b0000 0%,#c62828 45%,#7b0000 100%);min-height:100vh;color:#fff;overflow-x:hidden;-webkit-tap-highlight-color:transparent;}
    @keyframes float{0%,100%{transform:translateY(0)scale(1);opacity:.7}50%{transform:translateY(-16px)scale(1.2);opacity:1}}
    @keyframes pulse-gold{0%,100%{text-shadow:0 0 10px #ffd700,0 0 28px #ff8f00}50%{text-shadow:0 0 24px #fff176,0 0 55px #ffd700}}
    @keyframes blink{0%,100%{opacity:1}50%{opacity:.55}}
    @keyframes reveal{from{opacity:0;transform:translateY(20px)scale(.96)}to{opacity:1;transform:translateY(0)scale(1)}}
    @keyframes card-pop{0%{transform:scale(1)}40%{transform:scale(1.18)}70%{transform:scale(.97)}100%{transform:scale(1.07)}}
    @keyframes spin-sym{0%{transform:rotate(0)scale(1)}50%{transform:rotate(200deg)scale(1.4)}100%{transform:rotate(360deg)scale(1)}}
    @keyframes glow-beat{0%,100%{opacity:.85}50%{opacity:1}}
    @keyframes btn-breathe{0%,100%{box-shadow:var(--b0)}50%{box-shadow:var(--b1)}}
    @keyframes sticker-pulse{0%,100%{box-shadow:0 0 0 0 rgba(255,215,0,.5),0 -4px 20px rgba(0,0,0,.5)}50%{box-shadow:0 0 0 10px rgba(255,215,0,0),0 -4px 20px rgba(0,0,0,.5)}}
    @keyframes handoff-glow{0%,100%{box-shadow:0 0 20px rgba(105,240,174,.3)}50%{box-shadow:0 0 40px rgba(105,240,174,.6)}}
    #watermark{position:fixed;inset:0;pointer-events:none;z-index:0;display:flex;flex-wrap:wrap;opacity:.05;font-size:28px;overflow:hidden;align-content:flex-start;}
    #watermark span{width:12.5%;text-align:center;line-height:1.85;display:inline-block;}
    .particle{position:fixed;border-radius:50%;background:radial-gradient(circle,#fffde7,#ffd700);pointer-events:none;z-index:0;animation:float 3s ease-in-out infinite;}
    #app{position:relative;z-index:1;max-width:430px;margin:0 auto;padding:28px 16px 140px;display:flex;flex-direction:column;align-items:center;}
    #title-area{text-align:center;margin-bottom:6px;cursor:default;user-select:none;}
    .sub-label{color:#ffecb3;font-size:.82em;letter-spacing:6px;margin-bottom:4px;}
    h1{font-size:2.2em;font-weight:900;color:#ffd700;letter-spacing:3px;margin-bottom:4px;animation:pulse-gold 2.5s ease-in-out infinite;}
    .sub-loc{color:#ffecb3;font-size:.82em;letter-spacing:4px;}
    .divider{display:flex;align-items:center;gap:10px;width:100%;}
    .dl{flex:1;height:2px;}.dl.gr{background:linear-gradient(to right,transparent,#ffd700);}.dl.gl{background:linear-gradient(to left,transparent,#ffd700);}
    .dl.thin{height:1px;}.dl.dr{background:linear-gradient(to right,transparent,rgba(255,215,0,.25));}.dl.dl2{background:linear-gradient(to left,transparent,rgba(255,215,0,.25));}
    #guide-banner{width:100%;background:rgba(0,0,0,.32);border:2px solid rgba(255,215,0,.5);border-radius:18px;padding:18px 20px;margin-bottom:26px;box-shadow:0 4px 20px rgba(0,0,0,.25),inset 0 1px 0 rgba(255,255,255,.08);}
    .guide-title{color:#ffd700;font-size:1.05em;font-weight:900;letter-spacing:2px;margin-bottom:12px;text-align:center;}
    .guide-rows{display:flex;flex-direction:column;gap:8px;}
    .guide-row{display:flex;align-items:center;gap:12px;}
    .guide-num{width:32px;height:32px;border-radius:50%;flex-shrink:0;background:linear-gradient(135deg,#ffd700,#ff8f00);display:flex;align-items:center;justify-content:center;color:#7b0000;font-size:1.05em;font-weight:900;box-shadow:0 2px 8px rgba(0,0,0,.3);}
    .guide-desc{color:#fff9c4;font-size:1em;font-weight:700;letter-spacing:1px;line-height:1.3;}
    .guide-fin{margin-top:12px;padding-top:12px;border-top:1px solid rgba(255,215,0,.25);color:#69f0ae;font-size:.92em;font-weight:700;text-align:center;letter-spacing:2px;}
    .step-hdr{display:flex;align-items:center;gap:12px;width:100%;margin-bottom:12px;}
    .step-badge{width:40px;height:40px;border-radius:50%;flex-shrink:0;background:linear-gradient(135deg,#ffd700,#ff8f00);display:flex;align-items:center;justify-content:center;color:#7b0000;font-size:1.25em;font-weight:900;box-shadow:0 3px 12px rgba(0,0,0,.35);}
    .step-text{color:#ffd700;font-size:1.05em;font-weight:700;letter-spacing:2px;white-space:nowrap;}
    .step-line{flex:1;height:1px;background:rgba(255,215,0,.28);}
    #name-card{width:100%;margin-bottom:24px;background:rgba(0,0,0,.26);backdrop-filter:blur(6px);border:1.5px solid rgba(255,215,0,.38);border-radius:18px;padding:18px 16px;box-shadow:0 6px 24px rgba(0,0,0,.28),inset 0 1px 0 rgba(255,255,255,.1);}
    #name-input{width:100%;padding:16px 16px;font-size:1.22em;font-family:inherit;border-radius:12px;border:2px solid rgba(255,215,0,.45);background:rgba(255,255,255,.97);color:#222;outline:none;transition:border-color .2s,box-shadow .2s;letter-spacing:.5px;}
    #name-input:focus{border-color:#fff176;box-shadow:0 0 0 3px rgba(255,214,0,.3);}
    #name-input::placeholder{color:#aaa;font-size:.9em;}
    #zodiac-status{text-align:center;margin-top:6px;font-size:1.05em;font-weight:700;letter-spacing:2px;animation:blink 1.4s ease-in-out infinite;display:none;margin-bottom:8px;padding:8px 12px;background:rgba(0,0,0,.2);border-radius:10px;width:100%;}
    #zodiac-grid{width:100%;display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin-bottom:24px;}
    .zcard{background:rgba(0,0,0,.22);border:2px solid rgba(255,215,0,.22);border-radius:15px;padding:14px 6px 12px;cursor:pointer;display:flex;flex-direction:column;align-items:center;gap:5px;backdrop-filter:blur(4px);transition:transform .2s,border-color .2s,box-shadow .2s,background .2s;-webkit-tap-highlight-color:transparent;min-height:90px;justify-content:center;}
    .zcard:active{transform:scale(.88)!important;}
    .zcard.selected{transform:scale(1.06);}
    .zcard .ze{font-size:2.1em;line-height:1;transition:filter .25s;}
    .zcard .zs{font-size:1em;line-height:1;display:inline-block;}
    .zcard .zs.spin{animation:spin-sym .9s ease forwards;}
    .zcard .zn{font-size:.85em;line-height:1.2;text-align:center;color:#ffecb3;font-weight:700;letter-spacing:1px;transition:all .25s;}
    .zcard .zslogan{font-size:.68em;color:rgba(255,236,179,.6);letter-spacing:.5px;text-align:center;line-height:1.2;}
    .zcard.pop{animation:card-pop .9s ease forwards;}
    #draw-btn{width:100%;padding:22px 0;background:linear-gradient(180deg,#fff9c4 0%,#ffd700 50%,#ff8f00 100%);color:#7b0000;font-size:1.48em;font-weight:900;letter-spacing:2px;border-radius:50px;border:3px solid #ffd700;cursor:pointer;font-family:inherit;transition:border .3s,box-shadow .3s;box-shadow:0 6px 24px rgba(0,0,0,.4),0 0 16px rgba(255,215,0,.4),0 2px 0 rgba(255,255,255,.3) inset;--b0:0 6px 24px rgba(0,0,0,.4),0 0 16px #ffd70066,0 2px 0 rgba(255,255,255,.3) inset;--b1:0 6px 28px rgba(0,0,0,.4),0 0 36px #ffd700,0 2px 0 rgba(255,255,255,.3) inset;line-height:1.3;}
    #draw-btn:active{transform:scale(.93);}
    #draw-btn.breathing{animation:btn-breathe 1.6s ease-in-out infinite;}
    #draw-btn:disabled{opacity:.75;cursor:not-allowed;}
    #result-area{width:100%;display:none;animation:reveal .5s ease-out;margin-top:28px;}
    #result-area.visible{display:block;}
    #fortune-card{background:rgba(0,0,0,.32);backdrop-filter:blur(8px);border:2px solid #ffd700;border-radius:20px;padding:24px 20px;margin-bottom:14px;position:relative;overflow:hidden;}
    .cc{position:absolute;color:#ffd700;font-size:15px;opacity:.5;}
    .fl{font-size:.78em;color:#ffecb3;letter-spacing:4px;margin-bottom:14px;text-align:center;}
    #fortune-text{font-size:1.18em;line-height:1.82;color:#fff9c4;font-weight:700;text-align:center;margin-bottom:16px;}
    #fortune-meta{text-align:right;font-size:.8em;opacity:.75;color:#ffd700;}
    #handoff-card{background:linear-gradient(135deg,#1a4d1a,#2e7d32);border:2.5px solid #69f0ae;border-radius:20px;padding:22px 20px;text-align:center;margin-bottom:0;animation:handoff-glow 2s ease-in-out infinite;box-shadow:0 0 30px rgba(105,240,174,.2);}
    .hf-arrow{font-size:2.4em;margin-bottom:8px;animation:blink 1.2s ease-in-out infinite;}
    .hf-title{font-size:1.5em;font-weight:900;color:#fff;letter-spacing:3px;margin-bottom:8px;}
    .hf-sub{font-size:.95em;color:#a5d6a7;line-height:1.7;letter-spacing:1px;}
    .hf-sub strong{color:#69f0ae;font-size:1.05em;}
    #sticker-bar{position:fixed;bottom:0;left:0;right:0;z-index:100;background:linear-gradient(180deg,rgba(80,0,0,0) 0%,rgba(30,0,0,.97) 15%,#140000 100%);padding:10px 16px 26px;display:flex;flex-direction:column;align-items:center;gap:7px;}
    .sb-div{display:flex;align-items:center;gap:8px;width:100%;max-width:430px;}
    .sb-dl{flex:1;height:1px;background:rgba(255,215,0,.22);}
    .sb-lbl{color:rgba(255,215,0,.5);font-size:.68em;letter-spacing:2px;white-space:nowrap;}
    #sticker-btn{width:100%;max-width:430px;padding:17px 0;background:linear-gradient(180deg,#3a1a00,#1a0000);color:#ffd700;font-size:1.14em;font-weight:900;letter-spacing:2px;border-radius:16px;border:2px solid rgba(255,215,0,.52);cursor:pointer;font-family:inherit;transition:all .3s;box-shadow:0 -4px 20px rgba(0,0,0,.5);display:flex;align-items:center;justify-content:center;gap:10px;-webkit-tap-highlight-color:transparent;}
    #sticker-btn:active{transform:scale(.96);}
    #sticker-btn.ready{animation:sticker-pulse 2s ease-in-out infinite;}
    #sticker-btn.copied{background:linear-gradient(180deg,#a5d6a7,#388e3c);color:#fff;border-color:#69f0ae;box-shadow:0 0 22px rgba(105,240,174,.5),0 -4px 20px rgba(0,0,0,.5);animation:none;}
    #sticker-status{color:rgba(255,215,0,.38);font-size:.65em;letter-spacing:1px;text-align:center;line-height:1.5;}
  </style>
</head>
<body>
<div id="watermark"></div>
<div id="app">
  <div class="divider" style="margin-bottom:8px">
    <div class="dl gr"></div><span style="color:#ffd700;font-size:18px">❋</span><div class="dl gl"></div>
  </div>
  <div id="title-area">
    <div class="sub-label">── 土地公加持 ──</div>
    <h1>財氣鑑定所</h1>
    <div class="sub-loc">車城・専屬求財服務</div>
  </div>
  <div class="divider" style="margin:8px 0 20px">
    <div class="dl thin dr"></div><span style="color:#ffd700;font-size:13px">🪙</span><div class="dl thin dl2"></div>
  </div>
  <div id="guide-banner">
    <div class="guide-title">🙏 請依照以下三步驟操作</div>
    <div class="guide-rows">
      <div class="guide-row"><div class="guide-num">①</div><div class="guide-desc">在下方輸入您的姓名</div></div>
      <div class="guide-row"><div class="guide-num">②</div><div class="guide-desc">點選您的生肖圖案</div></div>
      <div class="guide-row"><div class="guide-num">③</div><div class="guide-desc">按下金色大按鈕</div></div>
    </div>
    <div class="guide-fin">✅ 完成後請將手機交給老闆</div>
  </div>
  <div class="step-hdr">
    <div class="step-badge">①</div><div class="step-text">輸入您的姓名</div><div class="step-line"></div>
  </div>
  <div id="name-card">
    <input id="name-input" type="text" placeholder="請輸入您的姓名，例：王大明" autocomplete="off" inputmode="text">
  </div>
  <div class="step-hdr">
    <div class="step-badge">②</div><div class="step-text">點選您的生肖</div><div class="step-line"></div>
  </div>
  <div id="zodiac-status"></div>
  <div id="zodiac-grid"></div>
  <div class="step-hdr">
    <div class="step-badge">③</div><div class="step-text">按下金色大按鈕</div><div class="step-line"></div>
  </div>
  <button id="draw-btn" onclick="draw()">按我！領取今日財氣指南</button>
  <div id="result-area">
    <div id="fortune-card">
      <span class="cc" style="top:8px;left:8px">◈</span><span class="cc" style="top:8px;right:8px">◈</span>
      <span class="cc" style="bottom:8px;left:8px">◈</span><span class="cc" style="bottom:8px;right:8px">◈</span>
      <div class="fl">── 您的專屬財氣籤詩 ──</div>
      <div id="fortune-text"></div>
      <div id="fortune-meta"></div>
    </div>
    <div id="handoff-card">
      <div class="hf-arrow">👇</div>
      <div class="hf-title">請將手機交給老闆</div>
      <div class="hf-sub">老闆將為您印製<br><strong>專屬財氣封印貼紙</strong><br>貼在您的 188元求財禮盒上</div>
    </div>
  </div>
</div>
<div id="sticker-bar">
  <div class="sb-div">
    <div class="sb-dl"></div><span class="sb-lbl">老闆快捷列印</span><div class="sb-dl"></div>
  </div>
  <button id="sticker-btn" onclick="copySticker()">
    <span id="s-icon">🏷️</span><span id="s-label">一鍵生成求財貼紙</span>
  </button>
  <div id="sticker-status">請先讓客人完成三步驟操作</div>
</div>
<script>
const ZODIACS=[
  {id:"鼠",name:"子鼠",slogan:"財源滾滾",emoji:"🐭",symbol:"🪙",color:"#c8960c",glow:"#ffe57f",bg:"rgba(212,160,23,0.22)"},
  {id:"牛",name:"丑牛",slogan:"牛轉乾坤",emoji:"🐮",symbol:"☯️",color:"#6d4c41",glow:"#d4a017",bg:"rgba(141,110,99,0.22)"},
  {id:"虎",name:"寅虎",slogan:"虎虎生風",emoji:"🐯",symbol:"✨",color:"#e65100",glow:"#ffb300",bg:"rgba(255,111,0,0.22)"},
  {id:"兔",name:"卯兔",slogan:"大展鴻兔",emoji:"🐰",symbol:"🌸",color:"#c2185b",glow:"#f48fb1",bg:"rgba(233,30,140,0.20)"},
  {id:"龍",name:"辰龍",slogan:"飛龍在天",emoji:"🐲",symbol:"💎",color:"#b8860b",glow:"#fff176",bg:"rgba(200,150,12,0.26)"},
  {id:"蛇",name:"巳蛇",slogan:"靈蛇獻瑞",emoji:"🐍",symbol:"🔮",color:"#2e7d32",glow:"#69f0ae",bg:"rgba(46,125,50,0.22)"},
  {id:"馬",name:"午馬",slogan:"馬到成功",emoji:"🐴",symbol:"🏆",color:"#b71c1c",glow:"#ff5252",bg:"rgba(183,28,28,0.22)"},
  {id:"羊",name:"未羊",slogan:"三羊開泰",emoji:"🐑",symbol:"🌈",color:"#6a1b9a",glow:"#ea80fc",bg:"rgba(106,27,154,0.22)"},
  {id:"猴",name:"申猴",slogan:"猴賽雷",emoji:"🐵",symbol:"🍑",color:"#bf360c",glow:"#ffb74d",bg:"rgba(230,81,0,0.22)"},
  {id:"雞",name:"酉雞",slogan:"大吉大利",emoji:"🐓",symbol:"🏮",color:"#f57f17",glow:"#ffee58",bg:"rgba(245,127,23,0.22)"},
  {id:"狗",name:"戌狗",slogan:"旺旺來",emoji:"🐕",symbol:"🍍",color:"#0d47a1",glow:"#82b1ff",bg:"rgba(13,71,161,0.24)"},
  {id:"豬",name:"亥豬",slogan:"諸事順利",emoji:"🐷",symbol:"🎀",color:"#880e4f",glow:"#ff80ab",bg:"rgba(173,20,87,0.22)"},
];
const FORTUNES=[
  "財神爺剛發限動：你今天偏財運爆表！你就是整條街最吸金的仔。",
  "你的錢包正在深呼吸，它準備好變胖了！今天跟著直覺走就對了。",
  "神明剛給你按了個讚！今天財氣護體，出門連走路都會撿到錢。",
  "你的財運正坐高鐵趕來！今天宜大膽行動，把錢錢變成喜歡的樣子。",
  "算命說你骨骼精奇，絕對是發財料！今天磁場極佳，自帶鈔能力。",
  "土地公說你今天顏值與財氣雙修！買什麼都增值，連呼吸都在賺錢。",
  "財運指數衝破天花板！今天你不是在花錢，是在為未來的暴富做投資。",
  "武財神已將你加入VIP名單！今天起小人退散，金主爸爸排隊來敲門。",
  "今日宜裝闊！因為你的正財偏財都在狂飆，擋都擋不住，準備數錢到手軟。",
  "財神爺剛幫你點了光明燈！今天幸運女神狂親你，走到哪裡都是你的主場。",
  "你的財富自由進度條突然快轉！今天直覺神準，連買個茶葉蛋都可能中特獎。",
  "天庭銀行已撥款！今天你自帶招財貓體質，身邊的人都會跟著你一起旺。",
];
let sel=null,fortune="",cpTimer=null;
const today=new Date();
const ds=`${today.getFullYear()}-${String(today.getMonth()+1).padStart(2,"0")}-${String(today.getDate()).padStart(2,"0")}`;
const wm=document.getElementById("watermark");
const rot=[-15,-8,0,8,15,-12,5,-5];
for(let i=0;i<96;i++){const s=document.createElement("span");s.textContent=ZODIACS[i%12].emoji;s.style.transform=`rotate(${rot[i%8]}deg)`;wm.appendChild(s);}
[[8,4,7],[20,88,9],[50,92,5],[75,7,8],[85,80,6],[12,48,7],[65,96,5]].forEach(([t,l,w],i)=>{
  const d=document.createElement("div");d.className="particle";
  d.style.cssText=`top:${t}%;left:${l}%;width:${w}px;height:${w}px;animation-duration:${2.5+i*.35}s;animation-delay:${i*.5}s`;
  document.body.appendChild(d);
});
const grid=document.getElementById("zodiac-grid");
ZODIACS.forEach(z=>{
  const c=document.createElement("div");c.className="zcard";c.id="z"+z.id;
  c.innerHTML=`<span class="ze">${z.emoji}</span><span class="zs" id="zs${z.id}">${z.symbol}</span><span class="zn">${z.name}</span><span class="zslogan">${z.slogan}</span>`;
  c.addEventListener("click",()=>pick(z));grid.appendChild(c);
});
function pick(z){
  if(sel){const p=document.getElementById("z"+sel.id);p.classList.remove("selected");p.style.cssText="";p.querySelector(".ze").style.filter="none";p.querySelector(".zn").style.cssText="";p.querySelector(".zslogan").style.color="";}
  sel=z;
  const c=document.getElementById("z"+z.id);
  c.classList.add("selected","pop");c.style.borderColor=z.glow;c.style.boxShadow=`0 0 18px ${z.glow}88,inset 0 0 8px ${z.glow}22`;c.style.background=`linear-gradient(145deg,${z.bg},rgba(0,0,0,.38))`;
  c.querySelector(".ze").style.filter=`drop-shadow(0 0 8px ${z.glow})`;
  const zn=c.querySelector(".zn");zn.style.color=z.glow;zn.style.textShadow=`0 0 8px ${z.glow}`;zn.style.fontWeight="900";
  c.querySelector(".zslogan").style.color=z.glow+"aa";
  const sym=document.getElementById("zs"+z.id);sym.classList.remove("spin");void sym.offsetWidth;sym.classList.add("spin");
  setTimeout(()=>{c.classList.remove("pop");sym.classList.remove("spin");},900);
  const st=document.getElementById("zodiac-status");st.style.display="block";st.style.color=z.glow;st.style.textShadow=`0 0 12px ${z.glow}99`;st.textContent=`✅ 已選擇：${z.emoji} ${z.name}（${z.slogan}）`;
  const db=document.getElementById("draw-btn");db.style.borderColor=z.glow;db.style.setProperty("--b0",`0 6px 24px rgba(0,0,0,.4),0 0 16px ${z.glow}66,0 2px 0 rgba(255,255,255,.3) inset`);db.style.setProperty("--b1",`0 6px 28px rgba(0,0,0,.4),0 0 36px ${z.glow}cc,0 2px 0 rgba(255,255,255,.3) inset`);db.classList.add("breathing");
  document.getElementById("fortune-card").style.borderColor=z.glow;document.getElementById("fortune-meta").style.color=z.glow;
}
function draw(){
  const name=document.getElementById("name-input").value.trim();
  if(!name){alert("請先在步驟①輸入您的姓名！");document.getElementById("name-input").focus();return;}
  if(!sel){alert("請先在步驟②點選您的生肖！");return;}
  const ra=document.getElementById("result-area");ra.classList.remove("visible");
  const db=document.getElementById("draw-btn");db.disabled=true;db.textContent="🔮 神明連線中，請稍候…";
  setTimeout(()=>{
    fortune=FORTUNES[Math.floor(Math.random()*FORTUNES.length)];
    document.getElementById("fortune-text").textContent=fortune;
    document.getElementById("fortune-meta").textContent=`${sel.emoji} ${name}（${sel.name}）· ${ds}`;
    ra.classList.add("visible");db.disabled=false;db.textContent="按我！領取今日財氣指南";
    document.getElementById("sticker-btn").classList.add("ready");
    updateStatus();
    setTimeout(()=>ra.scrollIntoView({behavior:"smooth",block:"start"}),100);
  },1400);
}
function updateStatus(){
  const name=document.getElementById("name-input").value.trim();
  document.getElementById("sticker-status").textContent=(name&&fortune&&sel)?`信眾：${name}・${sel.name}・${ds}`:"請先讓客人完成三步驟操作";
}
async function crossCopy(text){
  if(navigator.clipboard&&window.isSecureContext){try{await navigator.clipboard.writeText(text);return true;}catch(_){}}
  const el=document.createElement("textarea");el.value=text;el.setAttribute("readonly","");
  Object.assign(el.style,{position:"fixed",left:"-9999px",top:"50%",fontSize:"16px",opacity:"0",pointerEvents:"none"});
  document.body.appendChild(el);el.focus();el.select();
  let ok=false;try{ok=document.execCommand("copy");}catch(_){}
  document.body.removeChild(el);return ok;
}
async function copySticker(){
  const name=document.getElementById("name-input").value.trim();
  if(!name||!fortune||!sel){alert("請先讓客人完成三步驟操作！");return;}
  const text=`【車城 財氣封印】\n信眾：${name}　生肖：${sel.name}\n日期：${ds}\n${fortune}`;
  const ok=await crossCopy(text);
  const btn=document.getElementById("sticker-btn"),icon=document.getElementById("s-icon"),lbl=document.getElementById("s-label");
  if(ok){
    btn.classList.add("copied");btn.classList.remove("ready");icon.textContent="✅";lbl.textContent="已複製！切換至精臣 APP 貼上";
    clearTimeout(cpTimer);cpTimer=setTimeout(()=>{btn.classList.remove("copied");btn.classList.add("ready");icon.textContent="🏷️";lbl.textContent="一鍵生成求財貼紙";},3500);
  }else{window.prompt("請手動長按全選複製：",text);}
}
if("serviceWorker"in navigator){const sw=`const C='fq-v3';self.addEventListener('install',e=>self.skipWaiting());self.addEventListener('activate',e=>e.waitUntil(clients.claim()));self.addEventListener('fetch',e=>{e.respondWith(caches.match(e.request).then(c=>{if(c)return c;return fetch(e.request).then(r=>{if(e.request.method==='GET'&&e.request.url.startsWith('http'))caches.open(C).then(ca=>ca.put(e.request,r.clone()));return r;}).catch(()=>caches.match(e.request));}));});`;navigator.serviceWorker.register(URL.createObjectURL(new Blob([sw],{type:"application/javascript"}))).catch(()=>{});}
</script>
</body>
</html>
