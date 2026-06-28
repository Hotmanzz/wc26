<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>WC2026 Fantasy</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Bebas+Neue&display=swap" rel="stylesheet">
<style>
:root {
  --green-dark:#155724;--green:#1a7a30;--green-mid:#2d9142;--green-lite:#e8f5eb;
  --gold:#c8960c;--silver:#6b7280;--bronze:#7c5028;
  --tier-a:#0d47a1;--tier-a-bg:#e3f0ff;
  --tier-b:#1b5e20;--tier-b-bg:#e8f5eb;
  --tier-c:#7f5000;--tier-c-bg:#fff8e1;
  --red:#c62828;--red-bg:#ffebee;
  --text:#1a2e1c;--muted:#6b8f6e;
  --border:rgba(0,0,0,.1);--border2:rgba(0,0,0,.16);
  --radius:10px;--radius-lg:16px;
  --shadow:0 2px 12px rgba(0,0,0,.09);
}
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:'Inter',sans-serif;background:#f0f7f1;color:var(--text);font-size:14px;line-height:1.6;min-height:100vh;overflow-x:hidden}

/* ── PITCH BG ── */
body::before{
  content:'';position:fixed;inset:0;z-index:-1;
  background:
    radial-gradient(circle 90px at 50% 50%,transparent 88%,rgba(255,255,255,.18) 89%,rgba(255,255,255,.18) 91%,transparent 92%),
    linear-gradient(transparent calc(50%-.5px),rgba(255,255,255,.18) calc(50%-.5px),rgba(255,255,255,.18) calc(50%+.5px),transparent calc(50%+.5px)),
    repeating-linear-gradient(180deg,#3aaa48 0,#3aaa48 72px,#35a042 72px,#35a042 144px);
}

/* ── COUNTDOWN ── */
#cd-bar{
  background:var(--green-dark);color:#fff;text-align:center;
  padding:7px 16px;font-size:12px;font-weight:500;
  display:flex;align-items:center;justify-content:center;gap:8px;flex-wrap:wrap;
  position:sticky;top:0;z-index:200;
}
#cd-bar.locked{background:var(--red)}
.cdn{background:rgba(255,255,255,.2);padding:1px 8px;border-radius:5px;font-weight:700;font-size:14px;font-family:'Bebas Neue',sans-serif;letter-spacing:.05em}

/* ── HEADER ── */
header{background:rgba(26,100,48,.97);border-bottom:3px solid var(--gold);box-shadow:0 2px 16px rgba(0,0,0,.25);position:sticky;top:33px;z-index:100}
.hdr-inner{max-width:1000px;margin:0 auto;display:flex;align-items:center;gap:14px;height:60px;padding:0 20px}
.logo{font-family:'Bebas Neue',sans-serif;font-size:26px;letter-spacing:.06em;color:#fff;white-space:nowrap;display:flex;flex-direction:column;line-height:1}
.logo span{color:var(--gold)}
.logo-sub{font-family:'Inter',sans-serif;font-size:10px;font-weight:600;color:rgba(255,255,255,.65);letter-spacing:.12em;text-transform:uppercase}
nav{display:flex;gap:2px;margin-left:auto;flex-wrap:wrap}
.nb{padding:7px 14px;border:none;background:transparent;color:rgba(255,255,255,.75);font-size:12px;font-family:'Inter',sans-serif;cursor:pointer;border-radius:var(--radius);transition:all .15s;font-weight:500;white-space:nowrap}
.nb:hover{background:rgba(255,255,255,.15);color:#fff}
.nb.active{background:rgba(255,255,255,.22);color:#fff;font-weight:700}

/* ── SYNC STATUS ── */
#sync-bar{display:flex;align-items:center;gap:8px;font-size:11px;color:var(--muted);padding:6px 12px;background:rgba(255,255,255,.85);border-radius:var(--radius);margin-bottom:14px;border:0.5px solid var(--border)}
.sd{width:7px;height:7px;border-radius:50%;background:var(--green);flex-shrink:0;transition:background .3s}
.sd.syncing{background:#e8a900;animation:pulse 1s infinite}
.sd.err{background:var(--red)}
@keyframes pulse{0%,100%{opacity:1}50%{opacity:.35}}

/* ── LAYOUT ── */
.main{max-width:1000px;margin:0 auto;padding:22px 18px 60px}
.sec{display:none}.sec.active{display:block}

/* ── CARD ── */
.card{background:rgba(255,255,255,.93);border:0.5px solid var(--border);border-radius:var(--radius-lg);padding:18px;margin-bottom:14px;box-shadow:var(--shadow);backdrop-filter:blur(6px)}
.ct{font-size:11px;font-weight:700;color:var(--muted);text-transform:uppercase;letter-spacing:.07em;margin-bottom:12px}

/* ── HERO PODIUM ── */
.hero{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-bottom:14px}
.podium{border-radius:var(--radius-lg);padding:18px 14px;text-align:center;position:relative;overflow:hidden;border:0.5px solid var(--border)}
.podium::before{content:'';position:absolute;inset:0;opacity:.05;background:repeating-linear-gradient(45deg,#000 0,#000 2px,transparent 2px,transparent 10px)}
.p1{background:rgba(200,150,12,.08);border-color:rgba(200,150,12,.4)}
.p2{background:rgba(107,114,128,.06);border-color:rgba(107,114,128,.3)}
.p3{background:rgba(124,80,40,.06);border-color:rgba(124,80,40,.3)}
.pm{font-size:28px;margin-bottom:4px}
.pn{font-size:15px;font-weight:600}
.ps{font-size:26px;font-weight:700;margin-top:2px}
.p1 .ps{color:var(--gold)}.p2 .ps{color:var(--silver)}.p3 .ps{color:var(--bronze)}
.pt{font-size:11px;color:var(--muted);margin-top:5px;line-height:1.9}

/* ── TABLE ── */
table{width:100%;border-collapse:collapse}
th{text-align:left;padding:8px 10px;font-size:11px;font-weight:700;color:var(--muted);text-transform:uppercase;letter-spacing:.05em;border-bottom:0.5px solid var(--border);background:rgba(0,0,0,.02)}
td{padding:9px 10px;border-bottom:0.5px solid var(--border);vertical-align:middle}
tr:last-child td{border-bottom:none}
tr:hover td{background:rgba(26,122,48,.04)}
.rn{font-weight:700;font-size:13px}
.rn1{color:var(--gold)}.rn2{color:var(--silver)}.rn3{color:var(--bronze)}
.ts{font-size:16px;font-weight:700;color:var(--green)}
.ss{font-size:11px;color:var(--muted)}

/* ── BADGES ── */
.badge{display:inline-flex;align-items:center;gap:3px;padding:1px 7px;border-radius:5px;font-size:11px;font-weight:700;white-space:nowrap}
.ba{background:var(--tier-a-bg);color:var(--tier-a);border:0.5px solid rgba(13,71,161,.2)}
.bb{background:var(--tier-b-bg);color:var(--tier-b);border:0.5px solid rgba(27,94,32,.2)}
.bc{background:var(--tier-c-bg);color:var(--tier-c);border:0.5px solid rgba(127,80,0,.2)}
.bg{background:rgba(26,122,48,.1);color:var(--green);border:0.5px solid rgba(26,122,48,.2);font-size:10px;padding:1px 6px}
.br{background:var(--tier-a-bg);color:var(--tier-a);border:0.5px solid rgba(13,71,161,.2);font-size:10px;padding:1px 6px}

/* ── FORM ── */
.fl{display:block;font-size:12px;color:var(--muted);margin-bottom:4px;font-weight:600}
.fr{margin-bottom:10px}
input[type=text],input[type=number],input[type=password],select{width:100%;background:#fff;border:1.5px solid #c8dcc9;border-radius:var(--radius);padding:8px 11px;color:var(--text);font-size:13px;font-family:'Inter',sans-serif;outline:none;transition:border-color .15s,box-shadow .15s}
input:focus,select:focus{border-color:var(--green);box-shadow:0 0 0 3px rgba(26,122,48,.1)}
select option{background:#fff}

/* ── BUTTONS ── */
.btn{display:inline-flex;align-items:center;gap:5px;padding:8px 16px;border-radius:var(--radius);font-size:13px;font-weight:700;font-family:'Inter',sans-serif;cursor:pointer;border:none;transition:all .14s}
.bp{background:var(--green);color:#fff;box-shadow:0 2px 8px rgba(26,122,48,.3)}
.bp:hover{background:#166b2a}
.bp:disabled,.bp[disabled]{background:#9dbfa1;cursor:not-allowed;box-shadow:none}
.bg2{background:transparent;color:var(--muted);border:1.5px solid #c8dcc9}
.bg2:hover{background:var(--tier-b-bg);color:var(--text)}
.bd{background:transparent;color:var(--red);border:1.5px solid rgba(198,40,40,.25)}
.bd:hover{background:var(--red-bg)}
.bs{padding:4px 9px;font-size:11px}

/* ── ALERTS ── */
.al{padding:9px 12px;border-radius:var(--radius);font-size:12px;font-weight:500;margin-top:8px}
.al-ok{background:#e8f5eb;color:var(--tier-b);border:0.5px solid rgba(27,94,32,.2)}
.al-info{background:var(--tier-a-bg);color:var(--tier-a);border:0.5px solid rgba(13,71,161,.18)}
.al-warn{background:var(--tier-c-bg);color:var(--tier-c);border:0.5px solid rgba(127,80,0,.2)}
.al-err{background:var(--red-bg);color:var(--red);border:0.5px solid rgba(198,40,40,.2)}

/* ── LOCK BOX ── */
.lock-box{background:var(--red-bg);border:0.5px solid rgba(198,40,40,.3);border-radius:var(--radius-lg);padding:24px;text-align:center;margin-bottom:14px}
.lock-box h3{color:var(--red);font-size:18px;font-weight:600;margin-bottom:6px}
.lock-box p{color:var(--red);font-size:12px;opacity:.8}

/* ── TEAMS GRID ── */
.tier-hdr{display:flex;align-items:center;gap:8px;margin-bottom:8px;padding-bottom:7px;border-bottom:1.5px solid var(--border)}
.ts-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(136px,1fr));gap:5px}
.tc{display:flex;align-items:center;gap:6px;padding:7px 10px;border:1.5px solid #c8dcc9;border-radius:var(--radius);cursor:pointer;font-size:12px;color:var(--muted);background:#fff;font-family:'Inter',sans-serif;width:100%;transition:all .12s;font-weight:500}
.tc:hover:not(:disabled){border-color:var(--green);background:var(--tier-b-bg);color:var(--text)}
.tc:disabled{opacity:.5;cursor:not-allowed}
.tc.sa{border-color:var(--tier-a);background:var(--tier-a-bg);color:var(--tier-a);font-weight:700}
.tc.sb{border-color:var(--green);background:var(--tier-b-bg);color:var(--tier-b);font-weight:700}
.tc.sc{border-color:var(--tier-c);background:var(--tier-c-bg);color:var(--tier-c);font-weight:700}
.tf{font-size:18px;flex-shrink:0}
.tr{font-size:10px;color:var(--muted);margin-left:auto;flex-shrink:0}

/* ── PLAYER LIST ── */
.pi{display:flex;align-items:center;gap:10px;padding:8px 0;border-bottom:0.5px solid var(--border)}
.pi:last-child{border-bottom:none}
.av{width:34px;height:34px;border-radius:50%;background:var(--green);color:#fff;display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:700;flex-shrink:0}

/* ── FIXTURE ── */
.fb{display:flex;gap:8px;margin-bottom:14px;flex-wrap:wrap}
.fb>div{flex:1;min-width:110px}
.dl{font-size:11px;font-weight:700;color:var(--green);padding:10px 0 6px;border-bottom:0.5px solid var(--border);margin-bottom:2px;text-transform:uppercase;letter-spacing:.06em}
.fx{display:flex;align-items:center;gap:8px;padding:9px 4px;border-bottom:0.5px solid var(--border);transition:background .1s}
.fx:hover{background:rgba(26,122,48,.04);border-radius:var(--radius)}
.fx:last-child{border-bottom:none}
.ft{flex:1;display:flex;align-items:center;gap:6px;font-size:12px;font-weight:600;min-width:0}
.ft.r{flex-direction:row-reverse}
.ft span{white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.ff{font-size:19px;flex-shrink:0}
.fc{min-width:78px;text-align:center;flex-shrink:0}
.fsc{display:inline-block;background:var(--green);color:#fff;border-radius:6px;padding:2px 10px;font-size:14px;font-weight:700}
.ftm{font-size:10px;color:var(--muted);margin-top:2px}
.ftbd{display:inline-block;font-size:11px;color:var(--muted);background:rgba(0,0,0,.04);border:1.5px dashed #c8dcc9;padding:2px 10px;border-radius:5px;font-weight:600}

/* ── RULES ── */
.rg{display:grid;grid-template-columns:1fr 1fr;gap:14px}
.ri{display:flex;align-items:center;justify-content:space-between;padding:8px 0;border-bottom:0.5px solid var(--border)}
.ri:last-child{border-bottom:none}
.rp{font-size:14px;font-weight:700}
.rp.pos{color:var(--green)}.rp.neg{color:var(--red)}

/* ── ADMIN ── */
.ag{display:grid;grid-template-columns:1fr 1fr;gap:10px}

/* ── EMPTY ── */
.empty{text-align:center;padding:28px 0;color:var(--muted);font-size:13px}
.empty span{font-size:28px;display:block;margin-bottom:8px}

@media(max-width:600px){
  .hero{grid-template-columns:1fr}
  .rg{grid-template-columns:1fr}
  .ag{grid-template-columns:1fr}
  .nb{font-size:11px;padding:5px 9px}
  .logo-sub{display:none}
  #cd-bar{font-size:11px}
}
</style>
</head>
<body>

<!-- COUNTDOWN -->
<div id="cd-bar">
  <span>⏰ ปิดรับเลือกทีม:</span>
  <span class="cdn" id="cd-d">00</span><span>วัน</span>
  <span class="cdn" id="cd-h">00</span><span>ชม.</span>
  <span class="cdn" id="cd-m">00</span><span>นาที</span>
  <span class="cdn" id="cd-s">00</span><span>วิ</span>
</div>

<header>
  <div class="hdr-inner">
    <div class="logo">
      ⚽ WC2026<span>.</span>FANTASY
      <div class="logo-sub">FIFA World Cup 2026 · Fantasy League</div>
    </div>
    <nav>
      <button class="nb active" onclick="sw('lb',this)">🏆 คะแนน</button>
      <button class="nb" onclick="sw('draft',this)">👥 เลือกทีม</button>
      <button class="nb" onclick="sw('fx',this)">📅 Fixture</button>
      <button class="nb" onclick="sw('adm',this)">⚙️ Admin</button>
      <button class="nb" onclick="sw('rl',this)">📋 กฎ</button>
    </nav>
  </div>
</header>

<div class="main">

<!-- LEADERBOARD -->
<div class="sec active" id="tab-lb">
  <div id="sync-bar"><div class="sd syncing" id="sd"></div><span id="st">กำลังโหลด...</span><button onclick="loadAll()" style="margin-left:auto;padding:3px 9px;font-size:11px;border:0.5px solid #c8dcc9;background:transparent;border-radius:6px;cursor:pointer;font-family:inherit">↺ รีเฟรช</button></div>
  <div id="podium-area"></div>
  <div class="card"><div class="ct">ตารางคะแนนรวม — ทุกเครื่องเห็นพร้อมกัน 🔴 Live</div><div id="lb-table"></div></div>
</div>

<!-- DRAFT -->
<div class="sec" id="tab-draft">
  <div id="draft-lock"></div>
  <div id="draft-form">
    <div class="card">
      <div class="ct">ลงทะเบียนผู้เล่น</div>
      <div class="fr"><label class="fl">ชื่อผู้เล่น</label><input type="text" id="pname" placeholder="กรอกชื่อ..."></div>
      <p style="font-size:12px;color:var(--muted);margin-bottom:12px">เลือกทีม <strong style="color:var(--text)">Tier ละ 1 ทีม</strong> — สามารถเลือกซ้ำกับคนอื่นได้</p>
      <div id="draft-tiers"></div>
      <div style="display:flex;gap:8px;margin-top:14px">
        <button class="btn bp" id="reg-btn" onclick="regPlayer()">+ ลงทะเบียน</button>
        <button class="btn bg2" onclick="clrDraft()">ล้าง</button>
      </div>
      <div id="draft-msg"></div>
    </div>
  </div>
  <div class="card"><div class="ct">ผู้เล่นทั้งหมด (<span id="player-count">0</span> คน)</div><div id="reg-list"></div></div>
</div>

<!-- FIXTURES -->
<div class="sec" id="tab-fx">
  <div class="card">
    <div class="fb">
      <div><label class="fl">รอบ</label>
        <select id="rf" onchange="renderFx()">
          <option value="all">ทุกรอบ</option>
          <option value="group">รอบแบ่งกลุ่ม</option>
          <option value="r32">Round of 32</option>
          <option value="r16">Round of 16</option>
          <option value="qf">QF</option><option value="sf">SF</option><option value="final">รอบชิง</option>
        </select>
      </div>
      <div><label class="fl">กลุ่ม</label>
        <select id="gf" onchange="renderFx()">
          <option value="all">ทุกกลุ่ม</option>
          <option value="A">A</option><option value="B">B</option><option value="C">C</option>
          <option value="D">D</option><option value="E">E</option><option value="F">F</option>
          <option value="G">G</option><option value="H">H</option><option value="I">I</option>
          <option value="J">J</option><option value="K">K</option><option value="L">L</option>
        </select>
      </div>
      <div><label class="fl">ค้นหาทีม</label><input type="text" id="sq" placeholder="ชื่อทีม..." oninput="renderFx()"></div>
    </div>
    <div id="fx-list"></div>
  </div>
</div>

<!-- ADMIN -->
<div class="sec" id="tab-adm">
  <div class="card" id="adm-login">
    <div class="ct">🔒 Admin Login</div>
    <div class="fr" style="max-width:300px">
      <label class="fl">รหัสผ่าน Admin</label>
      <input type="password" id="adm-pw" placeholder="กรอกรหัสผ่าน..." onkeydown="if(event.key==='Enter')chkAdmin()">
    </div>
    <button class="btn bp" onclick="chkAdmin()">เข้าสู่ระบบ</button>
  </div>
  <div id="adm-panel" style="display:none">
    <div class="card">
      <div class="ct">⚙️ บันทึกผลการแข่งขัน</div>
      <div class="fr"><label class="fl">เลือก Fixture</label><select id="adm-sel" onchange="loadAdmFx()"></select></div>
      <div id="adm-form"></div>
      <div id="adm-msg"></div>
    </div>
  </div>
</div>

<!-- RULES -->
<div class="sec" id="tab-rl">
  <div class="rg">
    <div class="card">
      <div class="ct">ระบบคะแนน</div>
      <div class="ri"><span>ทีมชนะ (90/120 นาที)</span><span class="rp pos">+3</span></div>
      <div class="ri"><span>ทีมเสมอ</span><span class="rp pos">+1</span></div>
      <div class="ri"><span>ทีมแพ้</span><span class="rp" style="color:var(--muted)">0</span></div>
      <div class="ri"><span>ยิงประตู (ต่อลูก)</span><span class="rp pos">+1</span></div>
      <div class="ri"><span>คลีนชีต</span><span class="rp pos">+1</span></div>
      <div class="ri"><span>ชนะจุดโทษ (น็อคเอาท์)</span><span class="rp pos">+2</span></div>
      <div class="ri"><span>ใบแดง (ต่อใบ)</span><span class="rp neg">−1</span></div>
    </div>
    <div class="card">
      <div class="ct">ตัวคูณ Tier (FIFA Apr 2026)</div>
      <div style="display:flex;flex-direction:column;gap:8px">
        <div style="padding:12px;border-radius:var(--radius);background:var(--tier-a-bg);border:0.5px solid rgba(13,71,161,.2)"><div style="display:flex;justify-content:space-between;align-items:center"><div><span class="badge ba">Tier A</span><div style="font-size:12px;margin-top:4px;color:var(--tier-a)">อันดับ 1–10 (10 ทีม)</div></div><div style="font-size:24px;font-weight:700;color:var(--tier-a)">×1.0</div></div></div>
        <div style="padding:12px;border-radius:var(--radius);background:var(--tier-b-bg);border:0.5px solid rgba(27,94,32,.2)"><div style="display:flex;justify-content:space-between;align-items:center"><div><span class="badge bb">Tier B</span><div style="font-size:12px;margin-top:4px;color:var(--tier-b)">อันดับ 11–25 (15 ทีม)</div></div><div style="font-size:24px;font-weight:700;color:var(--tier-b)">×1.5</div></div></div>
        <div style="padding:12px;border-radius:var(--radius);background:var(--tier-c-bg);border:0.5px solid rgba(127,80,0,.2)"><div style="display:flex;justify-content:space-between;align-items:center"><div><span class="badge bc">Tier C</span><div style="font-size:12px;margin-top:4px;color:var(--tier-c)">อันดับ 26–48 (23 ทีม)</div></div><div style="font-size:24px;font-weight:700;color:var(--tier-c)">×2.0</div></div></div>
      </div>
    </div>
  </div>
  <div class="card">
    <div class="ct">ทีมในแต่ละ Tier — FIFA Ranking เม.ย. 2026</div>
    <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:14px">
      <div><div style="font-size:11px;font-weight:700;color:var(--tier-a);margin-bottom:7px;border-bottom:2px solid var(--tier-a-bg);padding-bottom:4px">TIER A — ×1.0</div><div id="tl-a" style="font-size:12px;line-height:2.1"></div></div>
      <div><div style="font-size:11px;font-weight:700;color:var(--tier-b);margin-bottom:7px;border-bottom:2px solid var(--tier-b-bg);padding-bottom:4px">TIER B — ×1.5</div><div id="tl-b" style="font-size:12px;line-height:2.1"></div></div>
      <div><div style="font-size:11px;font-weight:700;color:var(--tier-c);margin-bottom:7px;border-bottom:2px solid var(--tier-c-bg);padding-bottom:4px">TIER C — ×2.0</div><div id="tl-c" style="font-size:12px;line-height:2.1"></div></div>
    </div>
  </div>
</div>

</div><!-- end .main -->

<!-- Firebase SDK -->
<script type="module">
import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.2/firebase-app.js";
import { getDatabase, ref, set, get, onValue } from "https://www.gstatic.com/firebasejs/10.12.2/firebase-database.js";

// ══════════════════════════════════════════════
// 🔧 แก้ค่านี้ให้ตรงกับ Firebase Project ของคุณ
// ══════════════════════════════════════════════
const firebaseConfig = {
  apiKey: "AIzaSyCTFfeTwNCqskeQmqSDY66LVZr16sy4dkk",
  authDomain: "wc2026-fantasy-d7b29.firebaseapp.com",
  databaseURL: "https://wc2026-fantasy-d7b29-default-rtdb.asia-southeast1.firebasedatabase.app",
  projectId: "wc2026-fantasy-d7b29",
  storageBucket: "wc2026-fantasy-d7b29.firebasestorage.app",
  messagingSenderId: "49633501943",
  appId: "1:49633501943:web:46d48c7c7d2364a1ab29f2",
  measurementId: "G-Y4LGKP9DC2"
};
// ══════════════════════════════════════════════

const app = initializeApp(firebaseConfig);
const db = getDatabase(app);

const ADMIN_PASS = "admin2026";  // เปลี่ยนรหัสได้ที่นี่
const DEADLINE = new Date('2026-06-10T20:00:00Z');
const MULT = {A:1,B:1.5,C:2};

const FLAGS = {
  "France":"🇫🇷","Spain":"🇪🇸","Argentina":"🇦🇷","England":"🏴󠁧󠁢󠁥󠁮󠁧󠁿","Portugal":"🇵🇹",
  "Brazil":"🇧🇷","Netherlands":"🇳🇱","Morocco":"🇲🇦","Belgium":"🇧🇪","Germany":"🇩🇪",
  "Croatia":"🇭🇷","Colombia":"🇨🇴","Senegal":"🇸🇳","Mexico":"🇲🇽","USA":"🇺🇸",
  "Uruguay":"🇺🇾","Japan":"🇯🇵","Switzerland":"🇨🇭","Iran":"🇮🇷","Austria":"🇦🇹",
  "Ecuador":"🇪🇨","South Korea":"🇰🇷","Australia":"🇦🇺","Egypt":"🇪🇬","Canada":"🇨🇦",
  "Ivory Coast":"🇨🇮","Qatar":"🇶🇦","Algeria":"🇩🇿","Sweden":"🇸🇪","Tunisia":"🇹🇳",
  "Czechia":"🇨🇿","Türkiye":"🇹🇷","Norway":"🇳🇴","Scotland":"🏴󠁧󠁢󠁳󠁣󠁴󠁿","DR Congo":"🇨🇩",
  "Bosnia and Herzegovina":"🇧🇦","Panama":"🇵🇦","Saudi Arabia":"🇸🇦","South Africa":"🇿🇦",
  "Iraq":"🇮🇶","Paraguay":"🇵🇾","Cape Verde":"🇨🇻","New Zealand":"🇳🇿","Ghana":"🇬🇭",
  "Jordan":"🇯🇴","Uzbekistan":"🇺🇿","Haiti":"🇭🇹","Curaçao":"🇨🇼"
};
const F = t => FLAGS[t] || '🏳️';

const TEAMS = [
  {n:"France",r:1,t:"A"},{n:"Spain",r:2,t:"A"},{n:"Argentina",r:3,t:"A"},{n:"England",r:4,t:"A"},{n:"Portugal",r:5,t:"A"},
  {n:"Brazil",r:6,t:"A"},{n:"Netherlands",r:7,t:"A"},{n:"Morocco",r:8,t:"A"},{n:"Belgium",r:9,t:"A"},{n:"Germany",r:10,t:"A"},
  {n:"Croatia",r:11,t:"B"},{n:"Colombia",r:13,t:"B"},{n:"Senegal",r:14,t:"B"},{n:"Mexico",r:15,t:"B"},{n:"USA",r:16,t:"B"},
  {n:"Uruguay",r:17,t:"B"},{n:"Japan",r:18,t:"B"},{n:"Switzerland",r:19,t:"B"},{n:"Iran",r:21,t:"B"},{n:"Austria",r:23,t:"B"},
  {n:"Ecuador",r:24,t:"B"},{n:"South Korea",r:25,t:"B"},{n:"Australia",r:26,t:"B"},{n:"Egypt",r:29,t:"B"},{n:"Canada",r:30,t:"B"},
  {n:"Ivory Coast",r:33,t:"C"},{n:"Qatar",r:35,t:"C"},{n:"Algeria",r:36,t:"C"},{n:"Sweden",r:39,t:"C"},{n:"Tunisia",r:40,t:"C"},
  {n:"Czechia",r:41,t:"C"},{n:"Türkiye",r:42,t:"C"},{n:"Norway",r:44,t:"C"},{n:"Scotland",r:47,t:"C"},{n:"DR Congo",r:51,t:"C"},
  {n:"Bosnia and Herzegovina",r:52,t:"C"},{n:"Panama",r:53,t:"C"},{n:"Saudi Arabia",r:57,t:"C"},{n:"South Africa",r:60,t:"C"},
  {n:"Iraq",r:61,t:"C"},{n:"Paraguay",r:64,t:"C"},{n:"Cape Verde",r:68,t:"C"},{n:"Ghana",r:68,t:"C"},{n:"Jordan",r:75,t:"C"},
  {n:"Uzbekistan",r:79,t:"C"},{n:"Haiti",r:83,t:"C"},{n:"Curaçao",r:90,t:"C"},{n:"New Zealand",r:97,t:"C"}
];
const TT = {A:TEAMS.filter(t=>t.t==='A'),B:TEAMS.filter(t=>t.t==='B'),C:TEAMS.filter(t=>t.t==='C')};

const FIXTURES = [
  {id:"g1",round:"group",group:"A",home:"Mexico",away:"South Africa",date:"2026-06-11",time:"03:00"},
  {id:"g2",round:"group",group:"A",home:"South Korea",away:"Czechia",date:"2026-06-11",time:"10:00"},
  {id:"g3",round:"group",group:"B",home:"Canada",away:"Bosnia and Herzegovina",date:"2026-06-12",time:"03:00"},
  {id:"g4",round:"group",group:"D",home:"USA",away:"Paraguay",date:"2026-06-12",time:"09:00"},
  {id:"g5",round:"group",group:"B",home:"Qatar",away:"Switzerland",date:"2026-06-13",time:"03:00"},
  {id:"g6",round:"group",group:"C",home:"Brazil",away:"Morocco",date:"2026-06-13",time:"06:00"},
  {id:"g7",round:"group",group:"C",home:"Haiti",away:"Scotland",date:"2026-06-13",time:"09:00"},
  {id:"g8",round:"group",group:"D",home:"Australia",away:"Türkiye",date:"2026-06-14",time:"00:00"},
  {id:"g9",round:"group",group:"E",home:"Germany",away:"Curaçao",date:"2026-06-14",time:"01:00"},
  {id:"g10",round:"group",group:"F",home:"Netherlands",away:"Japan",date:"2026-06-14",time:"04:00"},
  {id:"g11",round:"group",group:"E",home:"Ivory Coast",away:"Ecuador",date:"2026-06-14",time:"07:00"},
  {id:"g12",round:"group",group:"F",home:"Sweden",away:"Tunisia",date:"2026-06-14",time:"10:00"},
  {id:"g13",round:"group",group:"H",home:"Spain",away:"Cape Verde",date:"2026-06-15",time:"00:00"},
  {id:"g14",round:"group",group:"G",home:"Belgium",away:"Egypt",date:"2026-06-15",time:"03:00"},
  {id:"g15",round:"group",group:"H",home:"Saudi Arabia",away:"Uruguay",date:"2026-06-15",time:"06:00"},
  {id:"g16",round:"group",group:"G",home:"Iran",away:"New Zealand",date:"2026-06-15",time:"09:00"},
  {id:"g17",round:"group",group:"I",home:"France",away:"Senegal",date:"2026-06-16",time:"03:00"},
  {id:"g18",round:"group",group:"I",home:"Iraq",away:"Norway",date:"2026-06-16",time:"06:00"},
  {id:"g19",round:"group",group:"J",home:"Argentina",away:"Algeria",date:"2026-06-16",time:"09:00"},
  {id:"g20",round:"group",group:"J",home:"Austria",away:"Jordan",date:"2026-06-17",time:"00:00"},
  {id:"g21",round:"group",group:"K",home:"Portugal",away:"DR Congo",date:"2026-06-17",time:"01:00"},
  {id:"g22",round:"group",group:"L",home:"England",away:"Croatia",date:"2026-06-17",time:"04:00"},
  {id:"g23",round:"group",group:"L",home:"Ghana",away:"Panama",date:"2026-06-17",time:"07:00"},
  {id:"g24",round:"group",group:"K",home:"Uzbekistan",away:"Colombia",date:"2026-06-17",time:"10:00"},
  {id:"g25",round:"group",group:"A",home:"Czechia",away:"South Africa",date:"2026-06-18",time:"00:00"},
  {id:"g26",round:"group",group:"B",home:"Switzerland",away:"Bosnia and Herzegovina",date:"2026-06-18",time:"03:00"},
  {id:"g27",round:"group",group:"B",home:"Canada",away:"Qatar",date:"2026-06-18",time:"06:00"},
  {id:"g28",round:"group",group:"A",home:"Mexico",away:"South Korea",date:"2026-06-18",time:"09:00"},
  {id:"g29",round:"group",group:"D",home:"USA",away:"Australia",date:"2026-06-19",time:"03:00"},
  {id:"g30",round:"group",group:"C",home:"Scotland",away:"Morocco",date:"2026-06-19",time:"06:00"},
  {id:"g31",round:"group",group:"C",home:"Brazil",away:"Haiti",date:"2026-06-19",time:"08:30"},
  {id:"g32",round:"group",group:"D",home:"Türkiye",away:"Paraguay",date:"2026-06-19",time:"11:00"},
  {id:"g33",round:"group",group:"F",home:"Netherlands",away:"Sweden",date:"2026-06-20",time:"01:00"},
  {id:"g34",round:"group",group:"E",home:"Germany",away:"Ivory Coast",date:"2026-06-20",time:"04:00"},
  {id:"g35",round:"group",group:"E",home:"Ecuador",away:"Curaçao",date:"2026-06-20",time:"08:00"},
  {id:"g36",round:"group",group:"F",home:"Tunisia",away:"Japan",date:"2026-06-21",time:"00:00"},
  {id:"g37",round:"group",group:"H",home:"Spain",away:"Saudi Arabia",date:"2026-06-21",time:"00:00"},
  {id:"g38",round:"group",group:"G",home:"Belgium",away:"Iran",date:"2026-06-21",time:"03:00"},
  {id:"g39",round:"group",group:"H",home:"Uruguay",away:"Cape Verde",date:"2026-06-21",time:"06:00"},
  {id:"g40",round:"group",group:"G",home:"New Zealand",away:"Egypt",date:"2026-06-21",time:"09:00"},
  {id:"g41",round:"group",group:"J",home:"Argentina",away:"Austria",date:"2026-06-22",time:"01:00"},
  {id:"g42",round:"group",group:"I",home:"France",away:"Iraq",date:"2026-06-22",time:"05:00"},
  {id:"g43",round:"group",group:"I",home:"Norway",away:"Senegal",date:"2026-06-22",time:"08:00"},
  {id:"g44",round:"group",group:"J",home:"Jordan",away:"Algeria",date:"2026-06-22",time:"11:00"},
  {id:"g45",round:"group",group:"K",home:"Portugal",away:"Uzbekistan",date:"2026-06-23",time:"01:00"},
  {id:"g46",round:"group",group:"L",home:"England",away:"Ghana",date:"2026-06-23",time:"04:00"},
  {id:"g47",round:"group",group:"L",home:"Panama",away:"Croatia",date:"2026-06-23",time:"07:00"},
  {id:"g48",round:"group",group:"K",home:"Colombia",away:"DR Congo",date:"2026-06-23",time:"10:00"},
  {id:"g49",round:"group",group:"B",home:"Switzerland",away:"Canada",date:"2026-06-24",time:"03:00"},
  {id:"g50",round:"group",group:"B",home:"Bosnia and Herzegovina",away:"Qatar",date:"2026-06-24",time:"03:00"},
  {id:"g51",round:"group",group:"C",home:"Scotland",away:"Brazil",date:"2026-06-24",time:"06:00"},
  {id:"g52",round:"group",group:"C",home:"Morocco",away:"Haiti",date:"2026-06-24",time:"06:00"},
  {id:"g53",round:"group",group:"A",home:"Czechia",away:"Mexico",date:"2026-06-24",time:"09:00"},
  {id:"g54",round:"group",group:"A",home:"South Africa",away:"South Korea",date:"2026-06-24",time:"09:00"},
  {id:"g55",round:"group",group:"E",home:"Curaçao",away:"Ivory Coast",date:"2026-06-25",time:"04:00"},
  {id:"g56",round:"group",group:"E",home:"Ecuador",away:"Germany",date:"2026-06-25",time:"04:00"},
  {id:"g57",round:"group",group:"F",home:"Japan",away:"Sweden",date:"2026-06-25",time:"07:00"},
  {id:"g58",round:"group",group:"F",home:"Tunisia",away:"Netherlands",date:"2026-06-25",time:"07:00"},
  {id:"g59",round:"group",group:"D",home:"Türkiye",away:"USA",date:"2026-06-25",time:"10:00"},
  {id:"g60",round:"group",group:"D",home:"Paraguay",away:"Australia",date:"2026-06-25",time:"10:00"},
  {id:"g61",round:"group",group:"I",home:"Norway",away:"France",date:"2026-06-26",time:"03:00"},
  {id:"g62",round:"group",group:"I",home:"Senegal",away:"Iraq",date:"2026-06-26",time:"03:00"},
  {id:"g63",round:"group",group:"H",home:"Cape Verde",away:"Saudi Arabia",date:"2026-06-26",time:"08:00"},
  {id:"g64",round:"group",group:"H",home:"Uruguay",away:"Spain",date:"2026-06-26",time:"08:00"},
  {id:"g65",round:"group",group:"G",home:"Egypt",away:"Iran",date:"2026-06-26",time:"11:00"},
  {id:"g66",round:"group",group:"G",home:"New Zealand",away:"Belgium",date:"2026-06-26",time:"11:00"},
  {id:"g67",round:"group",group:"L",home:"Panama",away:"England",date:"2026-06-27",time:"05:00"},
  {id:"g68",round:"group",group:"L",home:"Croatia",away:"Ghana",date:"2026-06-27",time:"05:00"},
  {id:"g69",round:"group",group:"K",home:"Colombia",away:"Portugal",date:"2026-06-27",time:"07:30"},
  {id:"g70",round:"group",group:"K",home:"DR Congo",away:"Uzbekistan",date:"2026-06-27",time:"07:30"},
  {id:"g71",round:"group",group:"J",home:"Algeria",away:"Austria",date:"2026-06-27",time:"10:00"},
  {id:"g72",round:"group",group:"J",home:"Jordan",away:"Argentina",date:"2026-06-27",time:"10:00"},
  {id:"r32_1",round:"r32",home:"Runner-up A",away:"Runner-up B",date:"2026-06-28",time:"03:00"},
  {id:"r32_2",round:"r32",home:"Winner C",away:"Runner-up F",date:"2026-06-29",time:"01:00"},
  {id:"r32_3",round:"r32",home:"Winner E",away:"Best 3rd",date:"2026-06-29",time:"04:30"},
  {id:"r32_4",round:"r32",home:"Winner F",away:"Runner-up C",date:"2026-06-29",time:"09:00"},
  {id:"r32_5",round:"r32",home:"Runner-up E",away:"Runner-up I",date:"2026-06-30",time:"01:00"},
  {id:"r32_6",round:"r32",home:"Winner I",away:"Best 3rd",date:"2026-06-30",time:"05:00"},
  {id:"r32_7",round:"r32",home:"Winner A",away:"Best 3rd",date:"2026-06-30",time:"09:00"},
  {id:"r32_8",round:"r32",home:"Winner L",away:"Best 3rd",date:"2026-07-01",time:"00:00"},
  {id:"r32_9",round:"r32",home:"Winner G",away:"Best 3rd",date:"2026-07-01",time:"04:00"},
  {id:"r32_10",round:"r32",home:"Winner D",away:"Best 3rd",date:"2026-07-01",time:"08:00"},
  {id:"r32_11",round:"r32",home:"Winner H",away:"Runner-up J",date:"2026-07-02",time:"03:00"},
  {id:"r32_12",round:"r32",home:"Runner-up K",away:"Runner-up L",date:"2026-07-02",time:"07:00"},
  {id:"r32_13",round:"r32",home:"Winner B",away:"Best 3rd",date:"2026-07-02",time:"11:00"},
  {id:"r32_14",round:"r32",home:"Runner-up D",away:"Runner-up G",date:"2026-07-03",time:"02:00"},
  {id:"r32_15",round:"r32",home:"Winner J",away:"Runner-up H",date:"2026-07-03",time:"06:00"},
  {id:"r32_16",round:"r32",home:"Winner K",away:"Best 3rd",date:"2026-07-03",time:"09:30"},
  {id:"r16_1",round:"r16",home:"R32 Winner",away:"R32 Winner",date:"2026-07-04",time:"01:00"},
  {id:"r16_2",round:"r16",home:"R32 Winner",away:"R32 Winner",date:"2026-07-04",time:"05:00"},
  {id:"r16_3",round:"r16",home:"R32 Winner",away:"R32 Winner",date:"2026-07-05",time:"04:00"},
  {id:"r16_4",round:"r16",home:"R32 Winner",away:"R32 Winner",date:"2026-07-05",time:"08:00"},
  {id:"r16_5",round:"r16",home:"R32 Winner",away:"R32 Winner",date:"2026-07-06",time:"03:00"},
  {id:"r16_6",round:"r16",home:"R32 Winner",away:"R32 Winner",date:"2026-07-06",time:"08:00"},
  {id:"r16_7",round:"r16",home:"R32 Winner",away:"R32 Winner",date:"2026-07-07",time:"00:00"},
  {id:"r16_8",round:"r16",home:"R32 Winner",away:"R32 Winner",date:"2026-07-07",time:"04:00"},
  {id:"qf_1",round:"qf",home:"R16 Winner",away:"R16 Winner",date:"2026-07-10",time:"03:00"},
  {id:"qf_2",round:"qf",home:"R16 Winner",away:"R16 Winner",date:"2026-07-10",time:"07:00"},
  {id:"qf_3",round:"qf",home:"R16 Winner",away:"R16 Winner",date:"2026-07-11",time:"03:00"},
  {id:"qf_4",round:"qf",home:"R16 Winner",away:"R16 Winner",date:"2026-07-11",time:"07:00"},
  {id:"sf_1",round:"sf",home:"QF Winner",away:"QF Winner",date:"2026-07-14",time:"03:00"},
  {id:"sf_2",round:"sf",home:"QF Winner",away:"QF Winner",date:"2026-07-15",time:"03:00"},
  {id:"final_1",round:"final",home:"SF Winner 1",away:"SF Winner 2",date:"2026-07-19",time:"03:00"}
].sort((a,b)=>a.date.localeCompare(b.date)||a.time.localeCompare(b.time));

const RN={group:'รอบแบ่งกลุ่ม',r32:'Round of 32',r16:'Round of 16',qf:'QF',sf:'SF',final:'รอบชิง'};
const DAYS=['อาทิตย์','จันทร์','อังคาร','พุธ','พฤหัสบดี','ศุกร์','เสาร์'];
const MO=['ม.ค.','ก.พ.','มี.ค.','เม.ย.','พ.ค.','มิ.ย.','ก.ค.','ส.ค.','ก.ย.','ต.ค.','พ.ย.','ธ.ค.'];
const fmtD = d => { const dt=new Date(d+'T12:00:00'); return `${DAYS[dt.getDay()]} ${dt.getDate()} ${MO[dt.getMonth()]} ${dt.getFullYear()+543}`; };

let players=[], results={}, overrides={};

// ── ชื่อทีมรอบน็อคเอาท์ (แก้ผ่าน Admin ได้ ไม่ต้องแก้โค้ด) ──
// overrides เก็บใน Firebase ที่ fixtureOverrides/{fixtureId} = {home, away}
function resolveFx(f) {
  const o = overrides[f.id];
  return o ? {...f, home:o.home||f.home, away:o.away||f.away} : f;
}

// ── FIREBASE SYNC ──
function setSS(state, txt) {
  const d=document.getElementById('sd'), t=document.getElementById('st');
  if(!d||!t) return;
  d.className='sd'+(state==='syncing'?' syncing':state==='err'?' err':'');
  t.textContent=txt;
}

async function loadAll() {
  setSS('syncing','กำลังโหลด...');
  try {
    const [ps, rs, os] = await Promise.all([
      get(ref(db,'players')),
      get(ref(db,'results')),
      get(ref(db,'fixtureOverrides'))
    ]);
    players = ps.exists() ? Object.values(ps.val()) : [];
    results = rs.exists() ? rs.val() : {};
    overrides = os.exists() ? os.val() : {};
    const now = new Date().toLocaleTimeString('th-TH',{hour:'2-digit',minute:'2-digit'});
    setSS('ok',`อัปเดต ${now} น. — ข้อมูลเดียวกันทุกเครื่อง 🔴 Live`);
  } catch(e) {
    setSS('err','โหลดไม่ได้ — ตรวจสอบ Firebase Config');
    console.error(e);
  }
  renderLB(); renderFx(); renderRegList();
}

// Real-time listener
onValue(ref(db,'players'), snap => {
  players = snap.exists() ? Object.values(snap.val()) : [];
  renderLB(); renderRegList();
  document.getElementById('player-count').textContent=players.length;
});
onValue(ref(db,'results'), snap => {
  results = snap.exists() ? snap.val() : {};
  renderLB(); renderFx();
  if(document.getElementById('adm-panel').style.display!=='none') loadAdmFxList();
});
onValue(ref(db,'fixtureOverrides'), snap => {
  overrides = snap.exists() ? snap.val() : {};
  renderFx();
  if(document.getElementById('adm-panel').style.display!=='none') loadAdmFxList();
});

// ── SCORING ──
function calcRaw(team) {
  let s=0;
  Object.values(results).forEach(r=>{
    if(!r.done)return;
    const isH=r.home===team, isA=r.away===team;
    if(!isH&&!isA)return;
    const hg=+r.hg||0,ag=+r.ag||0,hr=+r.hr||0,ar=+r.ar||0;
    if(isH){
      if(r.round==='group'){if(hg>ag)s+=3;else if(hg===ag)s+=1;}
      else if(hg>ag)s+=3;
      else if(hg===ag){if(r.pens==='home'){s+=3;s+=2;}else if(r.pens!=='away')s+=1;}
      s+=hg;if(ag===0)s+=1;s-=hr;
    }
    if(isA){
      if(r.round==='group'){if(ag>hg)s+=3;else if(ag===hg)s+=1;}
      else if(ag>hg)s+=3;
      else if(ag===hg){if(r.pens==='away'){s+=3;s+=2;}else if(r.pens!=='home')s+=1;}
      s+=ag;if(hg===0)s+=1;s-=ar;
    }
  });
  return s;
}
const calcP = p => { let t=0; ['A','B','C'].forEach(tier=>{ if(p.teams[tier]) t+=calcRaw(p.teams[tier])*MULT[tier]; }); return Math.round(t*10)/10; };

// ── LEADERBOARD ──
function renderLB() {
  const sc = players.map(p=>({...p,score:calcP(p)})).sort((a,b)=>b.score-a.score);
  const pa = document.getElementById('podium-area');
  if(!sc.length){ pa.innerHTML=''; document.getElementById('lb-table').innerHTML='<div class="empty"><span>🏆</span>ยังไม่มีผู้เล่น</div>'; return; }
  const md=['🥇','🥈','🥉'];
  let pod='<div class="hero">';
  [0,1,2].forEach(i=>{
    const p=sc[i];
    if(!p){pod+=`<div class="podium p${i+1}"><div class="pm">${md[i]}</div><div class="pn" style="color:var(--muted)">—</div></div>`;return;}
    const sa=(calcRaw(p.teams.A)*1).toFixed(1),sb=(calcRaw(p.teams.B)*1.5).toFixed(1),sc2=(calcRaw(p.teams.C)*2).toFixed(1);
    pod+=`<div class="podium p${i+1}"><div class="pm">${md[i]}</div><div class="pn">${p.name}</div><div class="ps">${p.score.toFixed(1)}</div><div class="pt">${F(p.teams.A)} ${p.teams.A} ${sa}pt<br>${F(p.teams.B)} ${p.teams.B} ${sb}pt<br>${F(p.teams.C)} ${p.teams.C} ${sc2}pt</div></div>`;
  });
  pod+='</div>';
  pa.innerHTML=pod;
  let html='<table><thead><tr><th>#</th><th>ผู้เล่น</th><th>Tier A ×1</th><th>Tier B ×1.5</th><th>Tier C ×2</th><th style="text-align:right">คะแนนรวม</th></tr></thead><tbody>';
  sc.forEach((p,i)=>{
    const rc=i<3?`rn${i+1}`:'';
    const sa=(calcRaw(p.teams.A)*1).toFixed(1),sb=(calcRaw(p.teams.B)*1.5).toFixed(1),sc2=(calcRaw(p.teams.C)*2).toFixed(1);
    html+=`<tr><td class="rn ${rc}">${i+1}</td><td style="font-weight:600">${p.name}</td><td>${F(p.teams.A)} <span class="badge ba">${p.teams.A||'—'}</span> <span class="ss">${sa}pt</span></td><td>${F(p.teams.B)} <span class="badge bb">${p.teams.B||'—'}</span> <span class="ss">${sb}pt</span></td><td>${F(p.teams.C)} <span class="badge bc">${p.teams.C||'—'}</span> <span class="ss">${sc2}pt</span></td><td style="text-align:right"><span class="ts">${p.score.toFixed(1)}</span></td></tr>`;
  });
  html+='</tbody></table>';
  document.getElementById('lb-table').innerHTML=html;
}

// ── DRAFT ──
let sel={A:null,B:null,C:null};
const isLocked = () => new Date()>=DEADLINE;

function renderDraft() {
  const locked=isLocked();
  const lb=document.getElementById('draft-lock'), df=document.getElementById('draft-form');
  if(locked){
    lb.innerHTML='<div class="lock-box"><h3>🔒 ระบบล็อคแล้ว</h3><p>หมดเวลาเลือกทีม 11 มิ.ย. 2569 เวลา 03:00 น.<br>ไม่สามารถลงทะเบียนหรือแก้ไขได้อีก</p></div>';
    df.style.display='none';
  } else {
    lb.innerHTML='<div class="al al-warn" style="margin-bottom:12px">⏰ ปิดรับ: <strong>11 มิ.ย. 2569 เวลา 03:00 น.</strong> — ก่อนคู่แรก Mexico vs South Africa</div>';
    df.style.display='block';
    renderDraftTiers();
  }
  renderRegList();
}

function renderDraftTiers() {
  const locked=isLocked();
  let html='';
  ['A','B','C'].forEach(tier=>{
    const bc=tier==='A'?'ba':tier==='B'?'bb':'bc';
    const sc2=tier==='A'?'sa':tier==='B'?'sb':'sc';
    const rr={A:'FIFA #1–10',B:'FIFA #11–25',C:'FIFA #26–48'}[tier];
    html+=`<div style="margin-bottom:18px"><div class="tier-hdr"><span class="badge ${bc}">Tier ${tier}</span><span style="font-size:12px;color:var(--muted)">×${MULT[tier]} — เลือก 1 ทีม</span><span style="font-size:11px;color:var(--muted);margin-left:auto">${rr}</span></div><div class="ts-grid">`;
    TT[tier].forEach(t=>{
      const s=sel[tier]===t.n;
      html+=`<button class="tc${s?' '+sc2:''}" onclick="selT('${tier}','${t.n}')" ${locked?'disabled':''}><span class="tf">${F(t.n)}</span><span>${t.n}</span><span class="tr">#${t.r}</span>${s?'<span style="font-size:11px">✓</span>':''}</button>`;
    });
    html+='</div></div>';
  });
  document.getElementById('draft-tiers').innerHTML=html;
  const rb=document.getElementById('reg-btn'); if(rb) rb.disabled=locked;
}

window.selT = (tier,name) => { if(isLocked())return; sel[tier]=sel[tier]===name?null:name; renderDraftTiers(); };
window.clrDraft = () => { if(isLocked())return; sel={A:null,B:null,C:null}; document.getElementById('pname').value=''; document.getElementById('draft-msg').innerHTML=''; renderDraftTiers(); };

window.regPlayer = async () => {
  if(isLocked()){ document.getElementById('draft-msg').innerHTML='<div class="al al-err">🔒 ระบบล็อคแล้ว</div>'; return; }
  const name=document.getElementById('pname').value.trim();
  const msg=document.getElementById('draft-msg');
  if(!name){msg.innerHTML='<div class="al al-info">กรุณากรอกชื่อผู้เล่น</div>';return;}
  if(!sel.A||!sel.B||!sel.C){msg.innerHTML='<div class="al al-info">กรุณาเลือกทีมให้ครบทุก Tier</div>';return;}
  setSS('syncing','กำลังบันทึก...');
  try {
    const id='p_'+Date.now();
    await set(ref(db,`players/${id}`),{id,name,teams:{A:sel.A,B:sel.B,C:sel.C},ts:Date.now()});
    msg.innerHTML=`<div class="al al-ok">✓ ลงทะเบียน <strong>${name}</strong> สำเร็จ! ทุกเครื่องเห็นแล้ว</div>`;
    clrDraft();
    setSS('ok','บันทึกสำเร็จ');
  } catch(e) { msg.innerHTML='<div class="al al-err">เกิดข้อผิดพลาด กรุณาลองใหม่</div>'; setSS('err','บันทึกไม่สำเร็จ'); }
};

function renderRegList() {
  const locked=isLocked();
  const c=document.getElementById('reg-list');
  document.getElementById('player-count').textContent=players.length;
  if(!players.length){c.innerHTML='<div class="empty">ยังไม่มีผู้เล่นลงทะเบียน</div>';return;}
  let html='';
  players.forEach((p,i)=>{
    const del=locked?'':`<button class="btn bd bs" onclick="delPlayer('${p.id||i}')">✕</button>`;
    html+=`<div class="pi"><div class="av">${p.name.slice(0,2).toUpperCase()}</div><div style="flex:1"><div style="font-weight:600;font-size:13px">${p.name}</div><div style="font-size:11px;color:var(--muted);margin-top:2px">${F(p.teams.A)} <span class="badge ba" style="margin-right:3px">${p.teams.A}</span>${F(p.teams.B)} <span class="badge bb" style="margin-right:3px">${p.teams.B}</span>${F(p.teams.C)} <span class="badge bc">${p.teams.C}</span></div></div>${del}</div>`;
  });
  c.innerHTML=html;
}

window.delPlayer = async (id) => {
  if(isLocked())return;
  try { await set(ref(db,`players/${id}`),null); } catch(e){}
};

// ── FIXTURES ──
function renderFx() {
  const rf=document.getElementById('rf').value, gf=document.getElementById('gf').value;
  const sq=(document.getElementById('sq').value||'').toLowerCase();
  const c=document.getElementById('fx-list');
  let fil=FIXTURES.map(resolveFx).filter(f=>{
    if(rf!=='all'&&f.round!==rf)return false;
    if(gf!=='all'&&f.group!==gf)return false;
    if(sq&&!f.home.toLowerCase().includes(sq)&&!f.away.toLowerCase().includes(sq))return false;
    return true;
  });
  if(!fil.length){c.innerHTML='<div class="empty">ไม่พบ fixture</div>';return;}
  const bd={};
  fil.forEach(f=>{if(!bd[f.date])bd[f.date]=[];bd[f.date].push(f);});
  let html='';
  Object.entries(bd).sort((a,b)=>a[0].localeCompare(b[0])).forEach(([date,fxs])=>{
    html+=`<div class="dl">📅 ${fmtD(date)}</div>`;
    fxs.forEach(f=>{
      const r=results[f.id];
      const gb=f.group?`<span class="badge bg">กลุ่ม ${f.group}</span>`:`<span class="badge br">${RN[f.round]||f.round}</span>`;
      let mid='';
      if(r&&r.done){
        const pens=r.pens?`<div class="ftm">${r.pens==='home'?f.home:f.away} ชนะ PK</div>`:'';
        const reds=(r.hr||r.ar)?`<div class="ftm" style="color:var(--red)">🟥 ${r.hr||0}–${r.ar||0}</div>`:'';
        mid=`<div class="fc"><span class="fsc">${r.hg}–${r.ag}</span><div class="ftm">${f.time} น. (ไทย)</div>${pens}${reds}</div>`;
      } else {
        mid=`<div class="fc"><div class="ftbd">vs</div><div class="ftm">${f.time} น. (ไทย)</div></div>`;
      }
      html+=`<div class="fx">${gb}<div class="ft r"><span>${f.home}</span><span class="ff">${F(f.home)}</span></div>${mid}<div class="ft"><span class="ff">${F(f.away)}</span><span>${f.away}</span></div></div>`;
    });
  });
  c.innerHTML=html;
}
window.renderFx = renderFx;

// ── ADMIN ──
window.chkAdmin = () => {
  if(document.getElementById('adm-pw').value===ADMIN_PASS){
    document.getElementById('adm-login').style.display='none';
    document.getElementById('adm-panel').style.display='block';
    loadAdmFxList();
  } else alert('รหัสผ่านไม่ถูกต้อง');
};

function loadAdmFxList() {
  const sel2=document.getElementById('adm-sel'); sel2.innerHTML='';
  FIXTURES.forEach(f=>{
    const rf=resolveFx(f);
    const o=document.createElement('option'); o.value=f.id;
    const r=results[f.id];
    o.textContent=`[${f.date}] ${RN[f.round]||f.round}${f.group?' '+f.group:''}: ${F(rf.home)} ${rf.home} vs ${F(rf.away)} ${rf.away}${r&&r.done?' ✓':''}`;
    sel2.appendChild(o);
  });
  loadAdmFx();
}
window.loadAdmFxList = loadAdmFxList;

window.loadAdmFx = function() {
  const fid=document.getElementById('adm-sel').value;
  const f0=FIXTURES.find(x=>x.id===fid); if(!f0)return;
  const f=resolveFx(f0);
  const r=results[fid]||{};
  const isKO=f.round!=='group';
  let html='';
  if(isKO){
    html+=`<div class="card" style="background:var(--tier-a-bg);border:0.5px solid rgba(13,71,161,.2);box-shadow:none;padding:12px;margin-bottom:12px">
      <div class="fl" style="color:var(--tier-a)">✏️ แก้ชื่อทีม (รอบน็อคเอาท์) — ใส่ทีมจริงที่เข้ารอบแทน placeholder</div>
      <div class="ag">
        <div class="fr"><label class="fl">ทีมเจ้าบ้าน (เดิม: ${f0.home})</label><input type="text" id="tname-h" value="${f.home.replace(/"/g,'&quot;')}" placeholder="เช่น France"></div>
        <div class="fr"><label class="fl">ทีมเยือน (เดิม: ${f0.away})</label><input type="text" id="tname-a" value="${f.away.replace(/"/g,'&quot;')}" placeholder="เช่น Spain"></div>
      </div>
      <div style="display:flex;gap:8px"><button class="btn bp bs" onclick="saveTeams('${fid}')">💾 บันทึกชื่อทีม</button><button class="btn bg2 bs" onclick="resetTeams('${fid}')">↺ รีเซ็ตเป็น placeholder</button></div>
    </div>`;
  }
  html+=`<div style="background:var(--tier-b-bg);border:0.5px solid rgba(27,94,32,.2);border-radius:var(--radius);padding:12px;margin-bottom:10px;font-size:12px"><strong style="color:var(--green)">${fmtD(f.date)} · ${f.time} น. (ไทย)</strong><br>${F(f.home)} ${f.home} <span style="color:var(--muted)">vs</span> ${F(f.away)} ${f.away}</div>
  <div class="ag">
    <div class="fr"><label class="fl">⚽ ประตู ${f.home}</label><input type="number" id="hg" min="0" value="${r.hg??''}"></div>
    <div class="fr"><label class="fl">⚽ ประตู ${f.away}</label><input type="number" id="ag" min="0" value="${r.ag??''}"></div>
    <div class="fr"><label class="fl">🟥 ใบแดง ${f.home}</label><input type="number" id="hr" min="0" value="${r.hr??0}"></div>
    <div class="fr"><label class="fl">🟥 ใบแดง ${f.away}</label><input type="number" id="ar" min="0" value="${r.ar??0}"></div>
  </div>`;
  if(isKO)html+=`<div class="fr"><label class="fl">จุดโทษ (กรณีเสมอ)</label><select id="pens"><option value="">— ไม่มี —</option><option value="home"${r.pens==='home'?' selected':''}>${f.home} ชนะ</option><option value="away"${r.pens==='away'?' selected':''}>${f.away} ชนะ</option></select></div>`;
  html+=`<div style="display:flex;gap:8px"><button class="btn bp" onclick="saveRes('${fid}')">💾 บันทึกผล</button><button class="btn bg2" onclick="clearRes('${fid}')">↺ ล้างผล</button></div>`;
  document.getElementById('adm-form').innerHTML=html;
  document.getElementById('adm-msg').innerHTML='';
};

window.saveTeams = async (fid) => {
  const h=document.getElementById('tname-h').value.trim();
  const a=document.getElementById('tname-a').value.trim();
  if(!h||!a){document.getElementById('adm-msg').innerHTML='<div class="al al-info">กรุณากรอกชื่อทีมทั้งสองฝั่ง</div>';return;}
  setSS('syncing','กำลังบันทึก...');
  try {
    await set(ref(db,`fixtureOverrides/${fid}`),{home:h,away:a});
    document.getElementById('adm-msg').innerHTML='<div class="al al-ok">✓ บันทึกชื่อทีมแล้ว — ทุกเครื่องเห็นทันที</div>';
    setSS('ok','บันทึกสำเร็จ — Live อัปเดตแล้ว');
    loadAdmFxList();
  } catch(e) { document.getElementById('adm-msg').innerHTML='<div class="al al-err">เกิดข้อผิดพลาด</div>'; setSS('err','บันทึกไม่สำเร็จ'); }
};

window.resetTeams = async (fid) => {
  try {
    await set(ref(db,`fixtureOverrides/${fid}`),null);
    document.getElementById('adm-msg').innerHTML='<div class="al al-info">รีเซ็ตชื่อทีมเป็น placeholder แล้ว</div>';
    loadAdmFxList();
  } catch(e){}
};

window.saveRes = async (fid) => {
  const f0=FIXTURES.find(x=>x.id===fid);
  const f=resolveFx(f0);
  const hg=document.getElementById('hg').value, ag=document.getElementById('ag').value;
  if(hg===''||ag===''){document.getElementById('adm-msg').innerHTML='<div class="al al-info">กรุณากรอกจำนวนประตู</div>';return;}
  setSS('syncing','กำลังบันทึก...');
  try {
    const pens=document.getElementById('pens')?document.getElementById('pens').value:'';
    const data={home:f.home,away:f.away,round:f.round,hg:parseInt(hg),ag:parseInt(ag),hr:parseInt(document.getElementById('hr').value)||0,ar:parseInt(document.getElementById('ar').value)||0,pens,done:true};
    await set(ref(db,`results/${fid}`),data);
    document.getElementById('adm-msg').innerHTML=`<div class="al al-ok">✓ บันทึกแล้ว — ทุกเครื่องเห็นผลทันที</div>`;
    setSS('ok','บันทึกสำเร็จ — Live อัปเดตแล้ว');
  } catch(e) { document.getElementById('adm-msg').innerHTML='<div class="al al-err">เกิดข้อผิดพลาด</div>'; setSS('err','บันทึกไม่สำเร็จ'); }
};

window.clearRes = async (fid) => {
  try { await set(ref(db,`results/${fid}`),null); document.getElementById('adm-msg').innerHTML='<div class="al al-info">ล้างผลสำเร็จ</div>'; } catch(e){}
};

// ── COUNTDOWN ──
function updCD() {
  const now=new Date(), bar=document.getElementById('cd-bar');
  if(now>=DEADLINE){
    bar.className='locked';
    bar.innerHTML='🔒 ระบบล็อคแล้ว — หมดเวลาเลือกทีม 11 มิ.ย. 2569 เวลา 03:00 น.';
    return;
  }
  const diff=DEADLINE-now;
  document.getElementById('cd-d').textContent=String(Math.floor(diff/86400000)).padStart(2,'0');
  document.getElementById('cd-h').textContent=String(Math.floor((diff%86400000)/3600000)).padStart(2,'0');
  document.getElementById('cd-m').textContent=String(Math.floor((diff%3600000)/60000)).padStart(2,'0');
  document.getElementById('cd-s').textContent=String(Math.floor((diff%60000)/1000)).padStart(2,'0');
}
setInterval(updCD,1000); updCD();

// ── NAV ──
window.sw = (name,btn) => {
  document.querySelectorAll('.nb').forEach(b=>b.classList.remove('active'));
  document.querySelectorAll('.sec').forEach(s=>s.classList.remove('active'));
  if(btn)btn.classList.add('active');
  document.getElementById('tab-'+name).classList.add('active');
  if(name==='draft')renderDraft();
  if(name==='fx')renderFx();
};
window.loadAll = loadAll;

// ── TIER LISTS ──
document.getElementById('tl-a').innerHTML=TT.A.map(t=>`${F(t.n)} ${t.n} <span style="color:var(--muted);font-size:10px">#${t.r}</span>`).join('<br>');
document.getElementById('tl-b').innerHTML=TT.B.map(t=>`${F(t.n)} ${t.n} <span style="color:var(--muted);font-size:10px">#${t.r}</span>`).join('<br>');
document.getElementById('tl-c').innerHTML=TT.C.map(t=>`${F(t.n)} ${t.n} <span style="color:var(--muted);font-size:10px">#${t.r}</span>`).join('<br>');

// Init
loadAll();
renderDraft();
renderFx();
</script>
</body>
</html>
