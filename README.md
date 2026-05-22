# for-you-my-lovely-minji
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>민지에게 보내는 편지 💌</title>
  <link href="https://fonts.googleapis.com/css2?family=Gowun+Dodum&family=Nanum+Myeongjo:wght@400;700;800&family=Nanum+Pen+Script&display=swap" rel="stylesheet" />
  <style>
    :root {
      --blush:#FDE8EE; --rose:#F7A8BF; --deep:#E05C84;
      --petal:#FBBFD2; --cream:#FFFAF8; --text:#4A1A2C;
      --muted:#9B6578; --white:#FFFFFF; --shadow:rgba(224,92,132,.15);
    }
    *,*::before,*::after{box-sizing:border-box;margin:0;padding:0;}
    body{font-family:'Gowun Dodum',serif;background:var(--cream);color:var(--text);min-height:100vh;overflow-x:hidden;}
    .petals{position:fixed;inset:0;pointer-events:none;z-index:0;overflow:hidden;}
    .petal{position:absolute;opacity:0;animation:fall linear infinite;top:-60px;}
    @keyframes fall{0%{opacity:0;transform:translateY(0) rotate(0deg)}10%{opacity:.8}90%{opacity:.5}100%{opacity:0;transform:translateY(110vh) rotate(360deg)}}
    .hero{position:relative;z-index:1;text-align:center;padding:72px 24px 56px;background:linear-gradient(160deg,#FDE8EE 0%,#FFF5F9 55%,#FDE8EE 100%);border-bottom:2px dashed var(--petal);}
    .hero-badge{display:inline-block;background:var(--deep);color:#fff;font-size:.78rem;letter-spacing:2px;padding:6px 18px;border-radius:99px;margin-bottom:20px;}
    .hero h1{font-family:'Nanum Myeongjo',serif;font-size:clamp(2.2rem,5.5vw,3.8rem);font-weight:800;line-height:1.25;margin-bottom:16px;}
    .hero h1 span{color:var(--deep);}
    .hero-sub{font-size:1.05rem;color:var(--muted);line-height:1.85;max-width:480px;margin:0 auto 36px;}
    .hero-to{display:inline-flex;align-items:center;gap:10px;background:var(--white);border:2px solid var(--petal);border-radius:16px;padding:14px 28px;font-size:1rem;color:var(--muted);box-shadow:0 4px 20px var(--shadow);}
    .hero-to strong{color:var(--deep);font-family:'Nanum Myeongjo',serif;font-size:1.15rem;}
    .write-wrap{position:relative;z-index:1;text-align:center;padding:44px 24px 8px;}
    .btn-write{display:inline-flex;align-items:center;gap:10px;background:linear-gradient(135deg,var(--deep) 0%,#F77DAB 100%);color:#fff;border:none;border-radius:99px;padding:17px 44px;font-size:1.05rem;font-family:'Gowun Dodum',serif;cursor:pointer;box-shadow:0 6px 28px rgba(224,92,132,.35);transition:transform .2s,box-shadow .2s;}
    .btn-write:hover{transform:translateY(-3px);box-shadow:0 10px 32px rgba(224,92,132,.45);}
    .section{position:relative;z-index:1;max-width:1100px;margin:0 auto;padding:48px 24px 80px;}
    .section-title{font-family:'Nanum Myeongjo',serif;font-size:1.6rem;font-weight:700;margin-bottom:32px;text-align:center;display:flex;align-items:center;justify-content:center;gap:10px;}
    .count-badge{background:var(--blush);color:var(--deep);border-radius:99px;padding:3px 13px;font-size:.85rem;font-weight:700;}
    .state-msg{text-align:center;color:var(--muted);padding:60px 0;font-size:1rem;line-height:1.8;}
    .grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:24px;}
    .card{background:var(--white);border-radius:20px;padding:28px 26px 22px;box-shadow:0 4px 24px var(--shadow);border-top:4px solid var(--petal);position:relative;overflow:hidden;transition:transform .22s,box-shadow .22s;animation:cardIn .5s ease both;}
    .card:hover{transform:translateY(-4px);box-shadow:0 10px 36px var(--shadow);}
    @keyframes cardIn{from{opacity:0;transform:translateY(20px)}to{opacity:1;transform:translateY(0)}}
    .card::before{content:'💌';position:absolute;top:16px;right:18px;font-size:1.3rem;opacity:.3;}
    .card-from{font-size:.78rem;letter-spacing:1px;text-transform:uppercase;color:var(--deep);font-weight:700;margin-bottom:12px;display:flex;align-items:center;gap:6px;}
    .card-from::before{content:'✦';font-size:.6rem;}
    .card-msg{font-family:'Nanum Pen Script',cursive;font-size:1.22rem;color:var(--text);line-height:1.78;white-space:pre-wrap;word-break:keep-all;}
    .card-date{font-size:.72rem;color:var(--muted);margin-top:16px;text-align:right;}
    .overlay{position:fixed;inset:0;z-index:100;background:rgba(74,26,44,.38);backdrop-filter:blur(5px);display:flex;align-items:center;justify-content:center;padding:24px;opacity:0;pointer-events:none;transition:opacity .25s;}
    .overlay.open{opacity:1;pointer-events:all;}
    .modal{background:var(--white);border-radius:24px;padding:40px 36px 36px;width:100%;max-width:480px;box-shadow:0 24px 64px rgba(224,92,132,.3);transform:translateY(20px) scale(.97);transition:transform .28s cubic-bezier(.34,1.56,.64,1);position:relative;}
    .overlay.open .modal{transform:translateY(0) scale(1);}
    .modal h2{font-family:'Nanum Myeongjo',serif;font-size:1.6rem;font-weight:800;color:var(--text);margin-bottom:6px;}
    .modal-sub{font-size:.9rem;color:var(--muted);margin-bottom:28px;}
    .modal label{display:block;font-size:.82rem;font-weight:700;color:var(--muted);letter-spacing:1px;text-transform:uppercase;margin-bottom:8px;}
    .modal input,.modal textarea{width:100%;font-family:'Gowun Dodum',serif;font-size:1rem;color:var(--text);background:var(--blush);border:2px solid transparent;border-radius:12px;padding:12px 16px;outline:none;transition:border-color .2s;resize:none;}
    .modal input:focus,.modal textarea:focus{border-color:var(--petal);}
    .field{margin-bottom:20px;}
    .modal textarea{min-height:140px;}
    .modal-btns{display:flex;gap:12px;margin-top:4px;}
    .btn-cancel{flex:1;padding:14px;border:2px solid var(--petal);border-radius:12px;background:transparent;color:var(--muted);font-family:'Gowun Dodum',serif;font-size:1rem;cursor:pointer;transition:background .18s;}
    .btn-cancel:hover{background:var(--blush);}
    .btn-send{flex:2;padding:14px;border:none;border-radius:12px;background:linear-gradient(135deg,var(--deep),#F77DAB);color:#fff;font-family:'Gowun Dodum',serif;font-size:1rem;cursor:pointer;box-shadow:0 4px 16px rgba(224,92,132,.35);transition:transform .18s,box-shadow .18s;}
    .btn-send:hover{transform:translateY(-2px);}
    .btn-send:disabled{opacity:.6;cursor:not-allowed;transform:none;}
    .btn-close{position:absolute;top:16px;right:16px;background:var(--blush);border:none;width:32px;height:32px;border-radius:50%;font-size:1rem;cursor:pointer;color:var(--muted);display:flex;align-items:center;justify-content:center;}
    .btn-close:hover{background:var(--petal);}
    /* 설정 박스 */
    .setup-box{position:relative;z-index:2;background:#fff8e1;border:2px solid #ffc107;border-radius:14px;padding:22px 28px;margin:20px auto;max-width:680px;font-size:.88rem;color:#7c5310;line-height:1.8;}
    .setup-box h3{font-size:1rem;font-weight:700;margin-bottom:12px;}
    .setup-box .step{display:flex;gap:12px;margin-bottom:10px;align-items:flex-start;}
    .setup-box .num{background:var(--deep);color:#fff;border-radius:50%;width:22px;height:22px;display:flex;align-items:center;justify-content:center;font-size:.75rem;font-weight:700;flex-shrink:0;margin-top:1px;}
    .setup-box code{background:rgba(0,0,0,.1);border-radius:4px;padding:1px 6px;font-family:monospace;font-size:.85rem;}
    .setup-box .highlight{background:#fff3cd;border:1px solid #ffc107;border-radius:8px;padding:10px 14px;margin-top:8px;font-weight:700;color:#5d3a00;}
    .toast{position:fixed;bottom:32px;left:50%;transform:translateX(-50%) translateY(20px);background:var(--text);color:#fff;border-radius:12px;padding:12px 24px;font-size:.9rem;z-index:200;opacity:0;transition:opacity .3s,transform .3s;white-space:nowrap;}
    .toast.show{opacity:1;transform:translateX(-50%) translateY(0);}
    footer{position:relative;z-index:1;text-align:center;padding:32px;font-size:.8rem;color:var(--muted);border-top:2px dashed var(--petal);}
    @media(max-width:540px){.hero{padding:52px 20px 40px;}.modal{padding:30px 20px 26px;}}
  </style>
</head>
<body>

<div class="petals" id="petals"></div>

<!-- 설정 안내 — 완료 후 style="display:none" -->
<div class="setup-box" id="setupBox">
  <h3>🔧 JSONBin 설정 방법</h3>
  <div class="step"><div class="num">1</div><div><a href="https://jsonbin.io" target="_blank">jsonbin.io</a> 가입 → 로그인</div></div>
  <div class="step"><div class="num">2</div><div>대시보드 → <strong>+ New Bin</strong> 클릭</div></div>
  <div class="step"><div class="num">3</div>
    <div>
      JSON 입력칸에 아래 내용을 그대로 복사 붙여넣기 후 <strong>Create</strong><br/>
      <div class="highlight">{"letters":[]}</div>
      ⚠️ <code>[]</code> 단독은 안 되고, 반드시 <code>{"letters":[]}</code> 형태로!
    </div>
  </div>
  <div class="step"><div class="num">4</div><div>생성된 Bin URL에서 ID 복사 (예: <code>64f3abc...</code>)</div></div>
  <div class="step"><div class="num">5</div><div>우측 상단 프로필 → <strong>API Keys</strong> → <strong>Master Key</strong> 복사</div></div>
  <div class="step"><div class="num">6</div><div>아래 <code>CONFIG</code>의 <code>BIN_ID</code>, <code>API_KEY</code> 에 붙여넣기 후 저장</div></div>
  <div class="step"><div class="num">7</div><div>이 박스에 <code>style="display:none"</code> 추가해서 숨기기</div></div>
</div>

<header class="hero">
  <div class="hero-badge">💌 For Our Dear Friend</div>
  <h1>민지에게,<br/><span>우리의 마음을 전해요</span> 🌸</h1>
  <p class="hero-sub">케이타운포유 디자인 파트장으로<br/>매일 멋지게 빛나고 있는 우리 민지에게<br/>친구들이 쓴 편지들이 모였어요 💖</p>
  <div class="hero-to">🎀 &nbsp;To. <strong>이민지</strong>&nbsp; 님께, 사랑을 담아</div>
</header>

<div class="write-wrap">
  <button class="btn-write" onclick="openModal()">✍️ 민지에게 편지 쓰기</button>
</div>

<main class="section">
  <h2 class="section-title">💌 편지 모음 <span class="count-badge" id="countBadge">0</span></h2>
  <div id="grid" class="grid">
    <div class="state-msg" id="stateMsg">편지를 불러오는 중이에요... 🌸</div>
  </div>
</main>

<div class="overlay" id="overlay" onclick="overlayClick(event)">
  <div class="modal">
    <button class="btn-close" onclick="closeModal()">✕</button>
    <h2>민지에게 편지 쓰기 💌</h2>
    <p class="modal-sub">따뜻한 마음을 담아 편지를 남겨주세요 🌸</p>
    <div class="field">
      <label>보내는 사람</label>
      <input id="fromInput" type="text" placeholder="이름 또는 닉네임" maxlength="30"/>
    </div>
    <div class="field">
      <label>민지에게 전하는 말</label>
      <textarea id="msgInput" placeholder="민지야,&#10;나는..." maxlength="600"></textarea>
    </div>
    <div class="modal-btns">
      <button class="btn-cancel" onclick="closeModal()">취소</button>
      <button class="btn-send" id="sendBtn" onclick="sendLetter()">💌 편지 보내기</button>
    </div>
  </div>
</div>

<footer>Made with 💖 by 예리 &amp; Friends · For our beloved 민지 🌸</footer>
<div class="toast" id="toast"></div>

<script>
/* ══════════════════════════════════════
   ✅ CONFIG — 여기에 JSONBin 정보 입력!
══════════════════════════════════════ */
const CONFIG = {
  BIN_ID:  '6a1010e26610dd3ae887cf93',
  API_KEY: '$2a$10$doy3ZXd3kyC6D.R37m4DKeNfV1PBou1R8tXDGKUHJCsn4ZLut2A/a'
};
/* ════════════════════════════════════ */

const BASE = 'https://api.jsonbin.io/v3/b';
let letters = [];

const DEMO = [
  { from:'예리', date:'2026. 5. 22.', msg:'민지야 💌 매일 디자인 파트 이끌면서 얼마나 힘들었을지 나는 알아.\n근데 있잖아, 네가 그 자리에 있는 게 당연한 거야.\n너는 진짜 대단한 사람이거든 🌸 힘내고 우리 곧 밥 먹자!' },
  { from:'세림', date:'2026. 5. 22.', msg:'민지야 진짜 너 없으면 디자인 파트가 굴러가겠어??\n항상 맡은 일 완벽하게 해내는 너 너무 멋있다 🌺\n좀 쉬어줘 제발... 그리고 힘내!!' },
  { from:'율리', date:'2026. 5. 21.', msg:'민지야 오늘도 수고 많았어 🫧\n우리 항상 응원하고 있다는 거 알지? 사랑해 💕' },
];

const isDemo = () => CONFIG.BIN_ID === 'YOUR_BIN_ID_HERE';

window.addEventListener('DOMContentLoaded', () => { spawnPetals(); loadLetters(); });

function spawnPetals() {
  const emojis = ['🌸','🌷','💐','🌺','🌹','💮','✨','💕','🌸','🌸'];
  const wrap = document.getElementById('petals');
  for (let i = 0; i < 22; i++) {
    const el = document.createElement('div');
    el.className = 'petal';
    el.textContent = emojis[Math.floor(Math.random() * emojis.length)];
    el.style.cssText = `left:${Math.random()*100}vw;font-size:${0.9+Math.random()*1.1}rem;animation-duration:${7+Math.random()*10}s;animation-delay:${Math.random()*12}s;`;
    wrap.appendChild(el);
  }
}

async function loadLetters() {
  if (isDemo()) { letters = DEMO; renderLetters(); return; }
  try {
    const res = await fetch(`${BASE}/${CONFIG.BIN_ID}/latest`, {
      headers: { 'X-Master-Key': CONFIG.API_KEY }
    });
    if (!res.ok) throw new Error();
    const data = await res.json();
    // {"letters":[...]} 구조에서 꺼내기
    letters = data.record?.letters ?? data.record ?? [];
    renderLetters();
  } catch {
    document.getElementById('stateMsg').innerHTML = '불러오기 실패 😢<br/>BIN_ID / API_KEY를 다시 확인해주세요.';
  }
}

function renderLetters() {
  const grid = document.getElementById('grid');
  document.getElementById('countBadge').textContent = letters.length;
  document.getElementById('stateMsg')?.remove();
  if (!letters.length) {
    grid.innerHTML = '<div class="state-msg">아직 편지가 없어요.<br/>첫 번째로 민지에게 마음을 전해보세요 💌</div>';
    return;
  }
  grid.innerHTML = [...letters].reverse().map((l, i) => `
    <div class="card" style="animation-delay:${i*.07}s">
      <div class="card-from">From. ${esc(l.from)}</div>
      <div class="card-msg">${esc(l.msg)}</div>
      <div class="card-date">${esc(l.date)}</div>
    </div>`).join('');
}

function openModal()  { document.getElementById('overlay').classList.add('open'); }
function closeModal() { document.getElementById('overlay').classList.remove('open'); }
function overlayClick(e) { if (e.target===document.getElementById('overlay')) closeModal(); }

async function sendLetter() {
  const from = document.getElementById('fromInput').value.trim();
  const msg  = document.getElementById('msgInput').value.trim();
  if (!from) { showToast('보내는 사람 이름을 적어주세요 🌸'); return; }
  if (msg.length < 5) { showToast('편지 내용을 조금 더 길게 써주세요 ☺️'); return; }

  const btn = document.getElementById('sendBtn');
  btn.disabled = true; btn.textContent = '전송 중... 🕊️';

  const now = new Date();
  const date = `${now.getFullYear()}. ${now.getMonth()+1}. ${now.getDate()}.`;
  const newLetter = { from, msg, date };

  if (isDemo()) {
    letters.push(newLetter); renderLetters();
    closeModal(); clearForm();
    showToast('편지 전달됐어요 💌 (데모 모드)');
    btn.disabled = false; btn.textContent = '💌 편지 보내기';
    return;
  }

  try {
    const updated = { letters: [...letters, newLetter] };
    const res = await fetch(`${BASE}/${CONFIG.BIN_ID}`, {
      method: 'PUT',
      headers: { 'Content-Type': 'application/json', 'X-Master-Key': CONFIG.API_KEY },
      body: JSON.stringify(updated)
    });
    if (!res.ok) throw new Error();
    letters = updated.letters;
    renderLetters(); closeModal(); clearForm();
    showToast('민지에게 편지가 전달됐어요 💌');
  } catch {
    showToast('전송 실패 😢 설정을 확인해주세요.');
  } finally {
    btn.disabled = false; btn.textContent = '💌 편지 보내기';
  }
}

function clearForm() {
  document.getElementById('fromInput').value = '';
  document.getElementById('msgInput').value = '';
}
function showToast(msg) {
  const el = document.getElementById('toast');
  el.textContent = msg; el.classList.add('show');
  setTimeout(() => el.classList.remove('show'), 3000);
}
function esc(s) {
  return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;');
}
</script>
</body>
</html>
