<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>🤍 なゆん NaYun | Shrine</title>
<meta name="theme-color" content="#6a1b9a" />
<style>
  :root{ --bg1:#14081a; --bg2:#1e0f2a; --accent:#6a1b9a; --accent-deep:#4a148c; --paper:#fffdf6; --ink:#2c2c2c; }
  *{box-sizing:border-box}
  html,body{height:100%}
  body{margin:0; font-family: ui-sans-serif, system-ui, "Noto Sans KR","Noto Sans JP", AppleSDGothicNeo, "Segoe UI", Roboto, Helvetica, Arial, sans-serif; color:#eee; background:
      radial-gradient(1200px 600px at 10% -10%, rgba(106,27,154,0.35), transparent 60%),
      radial-gradient(1200px 600px at 90% -10%, rgba(74,20,140,0.35), transparent 60%),
      linear-gradient(180deg, var(--bg1), var(--bg2)); display:flex; align-items:center; justify-content:center; padding:24px;}
  .card{width:min(980px, 100%); background:rgba(0,0,0,0.35); border:1px solid rgba(255,255,255,0.08); border-radius:16px; box-shadow:0 20px 60px rgba(0,0,0,0.55); overflow:hidden}
  header{padding:18px 20px; display:flex; gap:14px; align-items:center; justify-content:space-between; background:linear-gradient(90deg, rgba(106,27,154,0.25), rgba(74,20,140,0.25)); border-bottom:1px solid rgba(255,255,255,0.08)}
  .brand{display:flex; gap:12px; align-items:center}
  .torii{font-size:28px}
  h1{margin:0; font-size:20px; letter-spacing:.4px; font-weight:700}
  .nav{display:flex; gap:8px; align-items:center; flex-wrap:wrap}
  .tab{padding:8px 10px; border:1px solid rgba(255,255,255,.2); color:#eee; background:transparent; border-radius:999px; font-weight:700; font-size:13px; cursor:pointer; text-decoration:none}
  .tab.active{background:var(--accent); border-color:transparent}
  .langs{display:flex; gap:8px; margin-left:6px}
  .chip{padding:8px 10px; border:1px solid rgba(255,255,255,.2); color:#eee; background:transparent; border-radius:999px; cursor:pointer; font-weight:600; font-size:13px}
  .chip.active{background:var(--accent); border-color:transparent}
  .go-live{padding:8px 12px; border:none; border-radius:999px; background:linear-gradient(180deg, var(--accent), var(--accent-deep)); color:#fff; font-weight:800; letter-spacing:.2px; cursor:pointer; text-decoration:none}
  main{padding:26px}
  .view{display:none}
  .view.active{display:block}
  .section{border:1px solid rgba(255,255,255,0.08); border-radius:16px; padding:20px; background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0)); margin-bottom:20px}
  h2{margin:0 0 10px; font-size:18px; font-weight:800}
  p{margin:8px 0; line-height:1.7}
  .pill{display:inline-block; padding:6px 10px; border:1px solid rgba(255,255,255,.2); border-radius:999px; margin:4px 6px 0 0; font-size:12px}
  .muted{opacity:.8; font-size:13px}
  .about-grid{display:grid; grid-template-columns:.9fr 1.1fr; gap:26px; border:1px solid rgba(255,255,255,0.08); border-radius:16px; padding:20px; background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0))}
  @media (max-width:880px){ .about-grid{grid-template-columns:1fr} }
  .grid-omi{ display:grid; grid-template-columns: 1.1fr .9fr; gap:26px; }
  @media (max-width:880px){ .grid-omi{grid-template-columns:1fr} }
  .shrine{border:1px solid rgba(255,255,255,0.08); border-radius:16px; padding:20px; position:relative; background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0))}
  .shrine .title{font-weight:800; font-size:18px; margin:0 0 10px}
  .subtitle{opacity:.85; font-size:14px; margin-bottom:16px}
  .god{display:flex; gap:14px; align-items:center; padding:12px; border:1px dashed rgba(255,255,255,.18); border-radius:12px; background:rgba(106,27,154,.12)}
  .god .icon{font-size:24px}
  .god .lines{font-size:14px; line-height:1.5}
  .form{margin-top:18px; display:grid; gap:12px}
  label{font-size:13px; opacity:.9}
  input, select, textarea{width:100%; padding:12px 14px; border:1px solid rgba(255,255,255,0.18); border-radius:12px; background:rgba(0,0,0,.25); color:#eee; outline:none}
  .row{display:grid; grid-template-columns:1fr 1fr; gap:12px}
  @media (max-width:560px){ .row{grid-template-columns:1fr} }
  .btn{appearance:none; border:none; cursor:pointer; padding:12px 14px; border-radius:12px; color:#fff; background:linear-gradient(180deg, var(--accent), var(--accent-deep)); font-weight:800; letter-spacing:.3px; box-shadow:0 10px 24px rgba(106,27,154,.35)}
  .btn.secondary{background:transparent; border:1px solid rgba(255,255,255,.2)}
  .help{font-size:12px; opacity:.8}
  .omikuji{border:1px solid rgba(255,255,255,0.08); border-radius:16px; padding:20px; display:grid; gap:14px; background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0))}
  .paper{background:var(--paper); color:var(--ink); border-radius:14px; padding:18px 16px; position:relative; box-shadow:0 8px 30px rgba(0,0,0,0.35), inset 0 0 0 2px rgba(0,0,0,.06)}
  .slip-head{display:flex; align-items:center; justify-content:space-between}
  .slip-seal{border:2px solid #c62828; color:#c62828; padding:6px 10px; border-radius:999px; font-weight:900; font-size:12px; letter-spacing:.1em}
  .slip-grade{font-size:28px; font-weight:900; letter-spacing:.1em}
  .slip-title{margin:6px 0 10px; font-size:16px; font-weight:800}
  .slip-body{font-size:14px; line-height:1.6; white-space:pre-wrap}
  .actions{display:flex; gap:10px; flex-wrap:wrap}
  .mono{font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, "Liberation Mono", monospace; font-size:12px; opacity:.85}
  .lucky{ margin-top:12px; padding-top:10px; border-top:1px dashed rgba(0,0,0,.25); color:#333; font-size:13px }
  .lucky b{ display:inline-block; min-width:9.5em }
  footer{padding:14px 20px; border-top:1px solid rgba(255,255,255,0.08); font-size:12px; opacity:.85}
  .social{display:flex;gap:10px;flex-wrap:wrap;margin-top:8px}
  .social a{display:inline-flex;gap:6px;align-items:center;padding:6px 10px;border:1px solid rgba(255,255,255,.2); border-radius:999px;color:#fff;text-decoration:none;font-weight:700;font-size:12px;opacity:.95}
  .social a:hover{background:rgba(255,255,255,.08)}
  .event-list{display:grid; gap:10px}
  .event{border:1px solid rgba(255,255,255,.12); border-radius:12px; padding:12px 14px; background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0)); display:grid; gap:6px}
  .event .top{display:flex; flex-wrap:wrap; align-items:center; gap:10px; justify-content:space-between}
  .badge{display:inline-flex; align-items:center; gap:6px; padding:4px 8px; border-radius:999px; border:1px solid rgba(255,255,255,.2); font-size:12px}
  .event .title{font-weight:800}
  .event .desc{opacity:.9}
  .event .link{font-weight:700; color:#fff}
</style>
</head>
<body>
  <div class="card">
    <header>
      <div class="brand"><div class="torii">⛩️</div><h1>🤍 なゆん NaYun</h1></div>
      <div class="nav">
        <button class="tab active" data-view="about" id="tab-about">🏮 <span data-i="tabAbout">紹介</span></button>
        <button class="tab" data-view="omikuji" id="tab-omikuji">🎐 <span data-i="tabOmikuji">おみくじ</span></button>
        <button class="tab" data-view="events" id="tab-events">🗓️ <span data-i="tabEvents">イベント</span></button>
        <a class="go-live" id="goLiveBtn" target="_blank" rel="noopener">🔴 <span data-i="goLive">ライブを視聴</span></a>
        <div class="langs">
          <button class="chip active" data-lang="ja">日本語</button>
          <button class="chip" data-lang="en">English</button>
          <button class="chip" data-lang="ko">한국어</button>
        </div>
      </div>
    </header>

    <main>
      <!-- 소개 View -->
      <div class="view active" id="view-about">
        <div class="about-grid">
          <section class="section">
            <h2 data-i="aboutTitle">なゆんについて</h2>
            <p class="muted" data-i="aboutLead">なゆんは神です。永遠の時を見守り、訪れる者の声に耳を傾けます。</p>
            <p data-i="aboutP1">山影の小さな社に宿り、日々、参道を行き交う人の想いを静かに受け取ります。配信では日本の神社文化・怪談・ゲーム・雑談を届けます。</p>
            <div>
              <span class="pill">#神社配信</span><span class="pill">#怪談</span><span class="pill">#게임</span><span class="pill">#雑談</span>
            </div>
            <p data-i="aboutP2">合図は鈴の音。⛩️ 参拝は自由、願いはいつでもどうぞ。</p>
          </section>
          <!-- 에마(소원) 벽 -->
          <section class="section">
            <h2 data-i="emaTitle">絵馬掛所</h2>
            <p class="muted" id="emaInfo"></p>
            <div class="actions" id="authBar" style="gap:8px; margin-bottom:8px">
              <input id="authNick" placeholder="ニックネーム / Nickname / 닉네임" style="max-width:260px"/>
              <button class="btn" id="btnSign"><span data-i="btnSign">登録・ログイン</span></button>
              <button class="btn secondary" id="btnSignOut" style="display:none"><span data-i="btnSignOut">ログアウト</span></button>
              <span class="help mono" id="meTag"></span>
            </div>
            <div style="display:grid; gap:10px; grid-template-columns:1fr 1fr; margin-bottom:10px">
              <input id="emaWish" placeholder="願い事 / Wish / 소원" />
              <button class="btn" id="emaAdd" data-i="btnEmaAdd">掛ける</button>
            </div>
            <div class="actions" id="emaShareBar" style="gap:8px">
              <button class="btn secondary" id="emaPublic"><span data-i="emaPublic">公開リンクをコピー</span></button>
              <span class="help" id="emaPublicHint"></span>
            </div>
            <ul id="emaList" style="margin-top:10px; padding-left:18px;"></ul>
          </section>
        </div>
      </div>

      <!-- 오미쿠지 View -->
      <div class="view" id="view-omikuji">
        <div class="grid-omi">
          <section class="shrine">
            <p class="title" data-i="shrineTitle">神社参道</p>
            <p class="subtitle" data-i="shrineSub">なゆんは神です。永遠の時を見守り、訪れる者の声に耳を傾けます。</p>
            <div class="god"><div class="icon">🕯️</div><div class="lines"><div class="i" data-i="godLine1">静かに鈴を一打—今日の御神籤を受け取りましょう。</div><div class="i help" data-i="godLine2">※ 同じ名前/IDなら毎回同じ結果が出ます。（사람마다 결과 고정）</div></div></div>
            <div class="form">
              <div class="row">
                <div><label class="i" data-i="labelName">お名前（ニックネーム）</label><input id="seed" placeholder="例：NaYun / @DiscordUser / ゲーム名" /></div>
                <div><label class="i" data-i="labelScope">判定（固定キー）</label>
                  <select id="scope">
                    <option value="global">グローバル</option>
                    <option value="discord">Discord</option>
                    <option value="youtube">YouTube</option>
                    <option value="game">Game</option>
                  </select>
                </div>
              </div>
              <div class="actions">
                <button class="btn" id="drawBtn" data-i="btnDraw">おみくじを引く</button>
                <button class="btn secondary" id="shareBtn" data-i="btnShare">リンクをコピー</button>
                <button class="btn secondary" id="saveBtn" data-i="btnSave">画像で保存</button>
                <span class="help mono" id="shareHint"></span>
              </div>
            </div>
          </section>
          <section class="omikuji">
            <p class="title" data-i="resultTitle">本日の御神籤</p>
            <div class="paper" id="paper">
              <div class="slip-head"><div class="slip-seal">NAYUN SHRINE</div><div class="slip-grade" id="grade">—</div></div>
              <div class="slip-title" id="fortuneTitle">—</div>
              <div class="slip-body" id="fortuneBody">⛩️ 入力して「おみくじを引く」を押してください。</div>
              <div class="lucky" id="luckyBox" style="display:none"></div>
              <div class="muted mono" id="sig">ID: —</div>
            </div>
          </section>
        </div>
      </div>

      <!-- 이벤트 View -->
      <div class="view" id="view-events">
        <section class="section">
          <h2>🗓️ <span data-i="eventsTitle">イベント / Events / 이벤트</span></h2>
          <p class="muted" id="eventsInfo"></p>
          <div id="ownerBar" class="actions" style="margin:10px 0; display:none">
            <button class="btn" id="ownerLogin"><span data-i="ownerLogin">オーナーモード</span></button>
            <button class="btn secondary" id="ownerLogout" style="display:none"><span data-i="ownerLogout">ログアウト</span></button>
            <button class="btn secondary" id="publishBtn" style="display:none"><span data-i="publishBtn">公開リンクをコピー</span></button>
          </div>
          <div id="eventFormWrap" class="section" style="display:none">
            <h3 style="margin-top:0" data-i="newEvent">新規イベント</h3>
            <div class="row">
              <input id="evTitle" placeholder="タイトル / Title / 제목" />
              <div class="row" style="grid-template-columns:1fr 1fr; gap:10px">
                <input id="evDate" type="date" />
                <input id="evTime" type="time" />
              </div>
            </div>
            <textarea id="evDesc" placeholder="説明 / Description / 설명" rows="3"></textarea>
            <input id="evLink" placeholder="リンク（任意） / Optional Link" />
            <div class="actions"><button class="btn" id="addEvent"><span data-i="addEvent">追加</span></button><button class="btn secondary" id="clearEvents"><span data-i="clearAll">全削除</span></button></div>
            <p class="help" data-i="ownerHint">※ 追加/削除はあなたのみ。公開リンクにスナップショットが埋め込まれ、他の人は閲覧のみ。</p>
          </div>
          <div class="event-list" id="eventList"></div>
        </section>
      </div>
    </main>

    <footer>
      © 2025 NaYun Shrine — Colors kept (accent #6a1b9a / #4a148c) • JP/EN/KR
      <div class="social">
        <a href="https://www.twitch.tv/nayun_0110" target="_blank" rel="noopener">🟣 Twitch</a>
        <a href="https://www.youtube.com/@%E3%81%AA%E3%82%86%E3%82%93NaYun" target="_blank" rel="noopener">▶️ YouTube</a>
        <a href="https://toon.at/donate/welcomenayun" target="_blank" rel="noopener">💝 Toonation</a>
        <a href="https://x.com/NaYun350759" target="_blank" rel="noopener">𝕏 Twitter</a>
        <a href="https://discord.com/invite/RgfgRWGf8P" target="_blank" rel="noopener">💬 Discord</a>
      </div>
    </footer>
  </div>

  <audio id="bell" src="https://upload.wikimedia.org/wikipedia/commons/1/1f/Small-bell-ring-01.ogg" preload="auto"></audio>
<script>
/* ====== Config ====== */
const LIVE_URL = "https://www.youtube.com/channel/UCzeZjbPawq_9LWHZQfxy16Q/live";
const OWNER_KEY = "NayunSecret"; // 🔐 오너 모드 비밀키 (꼭 바꾸세요!)

// ✅ 아래 2개 채우면 에마가 "전세계 공유" 모드로 동작합니다. 비워두면 내 기기 전용(로컬 저장).
const SUPABASE_URL  = "";  // 예: https://xxxx.supabase.co
const SUPABASE_ANON = "";  // 예: eyJhbGciOiJI... (anon public key)

/* ====== i18n ====== */
const I18N = { ja:{
  tabAbout:"紹介", tabOmikuji:"おみくじ", tabEvents:"イベント",
  goLive:"ライブを視聴",
  aboutTitle:"なゆんについて", aboutLead:"なゆんは神です。永遠の時を見守り、訪れる者の声に耳を傾けます。",
  aboutP1:"山影の小さな社に宿り、日々、参道を行き交う人の想いを静かに受け取ります。配信では日本の神社文化・怪談・ゲーム・雑談を届けます。",
  aboutP2:"合図は鈴の音。⛩️ 参拝は自由、願いはいつでもどうぞ。",
  emaTitle:"絵馬掛所", btnEmaAdd:"掛ける", btnEmaClear:"全削除", btnSign:"登録・ログイン", btnSignOut:"ログアウト", emaPublic:"公開リンクをコピー",
  shrineTitle:"神社参道", shrineSub:"なゆんは神です。永遠の時を見守り、訪れる者の声に耳を傾けます。", godLine1:"静かに鈴を一打—今日の御神籤を受け取りましょう。", godLine2:"※ 同じ名前/IDなら毎回同じ結果が出ます。（사람마다 결과 고정）",
  labelName:"お名前（ニックネーム）", labelScope:"判定（固定キー）", btnDraw:"おみくじを引く", btnShare:"リンクをコピー", btnSave:"画像で保存", resultTitle:"本日の御神籤", inputHint:"⛩️ 入力して「おみくじを引く」を押してください。", shareCopied:"リンクをコピーしました。", luckyHead:"— 追記 / Extra —", luckyColor:"ラッキーカラー", luckyNumber:"ラッキーナンバー", luckyDirection:"方角", luckyItem:"お守り",
  eventsTitle:"イベント / Events / 이벤트", ownerLogin:"オーナーモード", ownerLogout:"ログアウト", publishBtn:"公開リンクをコピー", newEvent:"新規イベント", addEvent:"追加", clearAll:"全削除", ownerHint:"※ 追加/削除はあなたのみ。公開リンクにスナップショットが埋め込まれ、他の人は閲覧のみ。",
}, en:{
  tabAbout:"About", tabOmikuji:"Omikuji", tabEvents:"Events",
  goLive:"Watch Live",
  aboutTitle:"About NaYun", aboutLead:"NaYun is a god—watching over eternity and listening to those who come.", aboutP1:"Dwelling at a small shrine in the mountain’s shadow, NaYun quietly receives the wishes of travelers. Streams include shrine culture, ghost stories, games, and casual chats.", aboutP2:"The cue is the bell’s chime. ⛩️ Visit anytime; wishes are always welcome.",
  emaTitle:"Ema Wall", btnEmaAdd:"Hang", btnEmaClear:"Clear All", btnSign:"Register / Sign in", btnSignOut:"Sign out", emaPublic:"Copy Public Link",
  shrineTitle:"Shrine Approach", shrineSub:"NaYun is a god. Watching over eternity, listening to those who come.", godLine1:"Ring the bell—receive today’s fortune.", godLine2:"*The same name/ID always yields the same result.*",
  labelName:"Name (Nickname / ID)", labelScope:"Scope (Lock Key)", btnDraw:"Draw Omikuji", btnShare:"Copy Link", btnSave:"Save as Image", resultTitle:"Today’s Fortune", inputHint:"⛩️ Enter your name and tap “Draw Omikuji”.", shareCopied:"Link copied.", luckyHead:"— Extra —", luckyColor:"Lucky Color", luckyNumber:"Lucky Number", luckyDirection:"Direction", luckyItem:"Item",
  eventsTitle:"Events / イベント / 이벤트", ownerLogin:"Owner Mode", ownerLogout:"Log out", publishBtn:"Copy Public Link", newEvent:"New Event", addEvent:"Add", clearAll:"Clear All", ownerHint:"*Only you can add/delete. The public link embeds a snapshot so others can only view.*",
}, ko:{
  tabAbout:"소개", tabOmikuji:"오미쿠지", tabEvents:"이벤트",
  goLive:"라이브 보러가기",
  aboutTitle:"나융 소개", aboutLead:"나융은 신입니다. 영원을 지켜보며 찾아오는 이들의 목소리에 귀 기울입니다.", aboutP1:"산그늘 작은 신사에 깃들어 참배길을 오가는 이들의 마음을 조용히 받습니다. 방송은 신사 문화, 괴담, 게임, 잡담을 중심으로 진행합니다.", aboutP2:"신호는 방울소리. ⛩️ 언제든 참배 가능, 소원은 늘 환영입니다.",
  emaTitle:"에마掛所", btnEmaAdd:"걸기", btnEmaClear:"전체 삭제", btnSign:"등록 / 로그인", btnSignOut:"로그아웃", emaPublic:"공개 링크 복사",
  shrineTitle:"신사 참배길", shrineSub:"나융은 신입니다. 영원을 지켜보며 찾아오는 이의 목소리에 귀 기울입니다.", godLine1:"조용히 방울을 한 번—오늘의 점괘를 받아가세요.", godLine2:"※ 같은 이름/ID는 항상 같은 결과가 나옵니다.",
  labelName:"이름(닉네임/ID)", labelScope:"판정 범위(고정 키)", btnDraw:"오미쿠지 뽑기", btnShare:"링크 복사", btnSave:"이미지로 저장", resultTitle:"오늘의 점괘", inputHint:"⛩️ 이름을 입력하고 ‘오미쿠지 뽑기’를 눌러주세요.", shareCopied:"링크를 복사했어요.", luckyHead:"— 추가 운세 —", luckyColor:"행운의 색", luckyNumber:"행운의 숫자", luckyDirection:"방향", luckyItem:"아이템",
  eventsTitle:"이벤트 / Events / イベント", ownerLogin:"오너 모드", ownerLogout:"로그아웃", publishBtn:"공개 링크 복사", newEvent:"이벤트 추가", addEvent:"추가", clearAll:"전체 삭제", ownerHint:"※ 추가/삭제는 본인만. 공개 링크에는 스냅샷이 포함되어 다른 사람은 열람만 가능합니다.",
}};
let currentLang = "ja"; // default

function applyI18N(){
  document.querySelectorAll("[data-i]").forEach(el=>{ const key = el.getAttribute("data-i"); if(I18N[currentLang][key]) el.textContent = I18N[currentLang][key]; });
  document.querySelector("#tab-about span").textContent = I18N[currentLang].tabAbout;
  document.querySelector("#tab-omikuji span").textContent = I18N[currentLang].tabOmikuji;
  document.querySelector("#tab-events span").textContent = I18N[currentLang].tabEvents;
  document.querySelector("#goLiveBtn span").textContent = I18N[currentLang].goLive;
  const info = { ja: EMA_BACKEND()? 'みんなの絵馬は公開で閲覧できます。削除は本人のみ／オーナーは全件削除可。' : 'この端末に保存。公開は「公開リンクをコピー」。削除は本人のみ／オーナーは全件削除可。',
                 en: EMA_BACKEND()? 'All ema are publicly viewable. Authors can delete their own; owner can delete any.' : 'Saved on this device. Share via “Copy Public Link”. Authors can delete their own; owner can delete any.',
                 ko: EMA_BACKEND()? '에마는 모두가 볼 수 있어요. 작성자는 본인 것만 삭제, 오너는 전체 삭제 가능.' : '이 기기에 저장됩니다. “공개 링크 복사”로 공유. 작성자는 본인만 삭제, 오너는 전체 삭제 가능.' }[currentLang];
  const el = document.getElementById("eventsInfo"); if(el) el.textContent = info;
  document.getElementById("emaPublic").style.display = EMA_BACKEND()? 'none':'inline-block';
}

/* ====== Tabs & Lang ====== */
document.getElementById("goLiveBtn").href = LIVE_URL;
function setLang(lang){ if(!I18N[lang]) return; currentLang = lang;
  document.querySelectorAll('.chip').forEach(b=>b.classList.toggle('active', b.dataset.lang===lang));
  document.documentElement.setAttribute('lang', lang);
  try{ localStorage.setItem('nayun.lang', lang); }catch(e){}
  applyI18N();
  if(!hasDrawn) setHint(I18N[currentLang].inputHint);
  renderEmaInfo(); renderEma(); renderEvents();
}
document.querySelectorAll('.chip').forEach(btn=>{ btn.addEventListener('click', ()=> setLang(btn.dataset.lang)); });
function switchView(which){ document.querySelectorAll(".view").forEach(v=>v.classList.remove("active")); document.getElementById(`view-${which}`).classList.add("active"); document.querySelectorAll(".tab").forEach(t=>t.classList.remove("active")); document.querySelector(`[data-view="${which}"]`).classList.add("active"); }
document.querySelectorAll(".tab").forEach(t=>t.addEventListener("click", ()=>switchView(t.dataset.view)));

/* ====== Omikuji ====== */
function fnv1a(str){ let h=0x811c9dc5; for(let i=0;i<str.length;i++){ h^=str.charCodeAt(i); h=(h+((h<<1)+(h<<4)+(h<<7)+(h<<8)+(h<<24)))>>>0; } return h>>>0; }
const GRADES=[{key:"大吉",en:"Daikichi (Great Blessing)",ko:"대길",weight:10},{key:"中吉",en:"Chūkichi (Middle Blessing)",ko:"중길",weight:18},{key:"小吉",en:"Shōkichi (Small Blessing)",ko:"소길",weight:22},{key:"吉",en:"Kichi (Good Luck)",ko:"길",weight:20},{key:"末吉",en:"Suekichi (Late Luck)",ko:"말길",weight:18},{key:"凶",en:"Kyō (Misfortune)",ko:"흉",weight:12},];
const THEMES={ja:[{t:"はじまり",b:"新しい縁に恵まれる兆し。小さな決断が大きな道をひらきます."},{t:"静けさ",b:"焦りを手放し、呼吸を整えれば、必要なものが現れます."},{t:"灯り",b:"暗がりでこそ灯は目立つもの。あなたの一言が誰かを照らします."},{t:"守り",b:"約束を大切に。古い絆が思わぬ助けとなるでしょう."},{t:"余白",b:"詰め込みすぎず、余白を残すと運が入り込みます."},{t:"祓い",b:"不要なものを祓えば、良きものが入る。掃除は最良の御祓."}], en:[{t:"Beginning",b:"A new connection approaches. Small choices open a wide road."},{t:"Stillness",b:"Let go of haste; with steady breath, what you need will appear."},{t:"Lantern",b:"In the dark, light stands out. Your words may guide someone."},{t:"Guard",b:"Honor your promises. Old ties bring unexpected aid."},{t:"Margin",b:"Leave room—fortune flows into open spaces."},{t:"Purify",b:"Remove the needless; good enters. Cleaning is the finest rite."}], ko:[{t:"시작",b:"새 인연의 조짐. 작은 결정이 큰 길을 엽니다."},{t:"고요",b:"초조함을 놓고 호흡을 가다듬으면 필요한 것이 나타납니다."},{t:"등불",b:"어둠 속에서 빛은 더 선명합니다. 당신의 한마디가 누군가를 비춥니다."},{t:"수호",b:"약속을 소중히. 오래된 인연이 의외의 도움을 줍니다."},{t:"여백",b:"너무 채우지 말고 여백을 남기면 운이 스며듭니다."},{t:"정화",b:"불필요를 비우면 좋은 것이 들어옵니다. 청소는 최고의 의식."}]};
function pickGrade(h){const total=GRADES.reduce((a,g)=>a+g.weight,0); const r=h%total; let acc=0; for(const g of GRADES){acc+=g.weight; if(r<acc) return g;} return GRADES[0];}
function pickTheme(h){const idx=h%6; return { ja:THEMES.ja[idx], en:THEMES.en[idx], ko:THEMES.ko[idx] };}
function buildSeed(){ const name=(document.getElementById("seed").value||"").trim(); const scope=document.getElementById("scope").value; const seed=`${scope}:${name}`.toLowerCase(); return {name,scope,seed}; }
function setHint(msg){ document.getElementById("fortuneBody").textContent=msg; }
let hasDrawn=false;
function pickFrom(arr,h,s){ return arr[(h+s)%arr.length]; }
function luckySet(h,lang){ const colors={ja:["茜","白金","墨","菜の花","藍","琥珀"],en:["Crimson","Platinum","Charcoal","Canola","Indigo","Amber"],ko:["주홍","백금","먹","유채","남색","호박"]}[lang]; const numbers=[3,4,6,7,8,9]; const dirs={ja:["東","西","南","北","南東","北西"],en:["East","West","South","North","SE","NW"],ko:["동","서","남","북","남동","북서"]}[lang]; const items={ja:["御札","鈴","五円","灯","鏡","御守"],en:["Ofuda","Bell","5-yen","Candle","Mirror","Omamori"],ko:["부적","방울","5엔","촛불","거울","오마모리"]}[lang]; return { color:pickFrom(colors,h,7), number:pickFrom(numbers,h,11), direction:pickFrom(dirs,h,19), item:pickFrom(items,h,23) }; }
function draw(force=false){ const bell=document.getElementById("bell"); const {name,scope,seed}=buildSeed(); if(!seed||seed.endsWith(":")){ setHint(I18N[currentLang].inputHint); return; } try{ bell.currentTime=0; bell.play(); }catch(e){}
  const h=fnv1a(seed); const grade=pickGrade(h); const theme=pickTheme(h); const slips={ja:theme.ja, en:theme.en, ko:theme.ko}; const gradeLabel=(lang)=> lang==="ja"?grade.key:(lang==="en"?grade.en.split(" ")[0]:grade.ko); const slip=slips[currentLang];
  document.getElementById("grade").textContent=gradeLabel(currentLang);
  document.getElementById("fortuneTitle").textContent=slip.t;
  document.getElementById("fortuneBody").textContent=slip.b;
  const L=luckySet(h,currentLang); const luckyBox=document.getElementById("luckyBox"); luckyBox.style.display="block"; luckyBox.innerHTML=`<b>${I18N[currentLang].luckyHead}</b><br>🎨 <b>${I18N[currentLang].luckyColor}</b>: ${L.color} &nbsp;&nbsp;#️⃣ <b>${I18N[currentLang].luckyNumber}</b>: ${L.number} &nbsp;&nbsp;🧭 <b>${I18N[currentLang].luckyDirection}</b>: ${L.direction} &nbsp;&nbsp;🧿 <b>${I18N[currentLang].luckyItem}</b>: ${L.item}`;
  document.getElementById("sig").textContent=`ID: ${scope}/${name||"—"} • HASH:${h.toString(16)}`; localStorage.setItem("nayun.omikuji.last", JSON.stringify({name,scope,lang:currentLang})); hasDrawn=true; bell?.play().catch(()=>{}); if(navigator.vibrate) navigator.vibrate(30); if(force) return; }
function share(){ const {name,scope}=buildSeed(); if(!name){ setHint(I18N[currentLang].inputHint); return; } const url=new URL(location.href); url.searchParams.set("n",name); url.searchParams.set("s",scope); url.searchParams.set("l",currentLang); navigator.clipboard.writeText(url.toString()).then(()=>{ document.getElementById("shareHint").textContent=I18N[currentLang].shareCopied; setTimeout(()=>{ document.getElementById("shareHint").textContent=""; },2200); }); }
function saveImage(){ const c=document.createElement("canvas"); c.width=1080; c.height=1350; const ctx=c.getContext("2d"); const grad=ctx.createLinearGradient(0,0,0,c.height); grad.addColorStop(0,"#1e0f2a"); grad.addColorStop(1,"#14081a"); ctx.fillStyle=grad; ctx.fillRect(0,0,c.width,c.height); ctx.fillStyle="#fffdf6"; ctx.fillRect(80,120,920,1110); const g=document.getElementById("grade").textContent||"-"; const t=document.getElementById("fortuneTitle").textContent||"-"; const b=(document.getElementById("fortuneBody").textContent||"-")+"\n\n"+(document.getElementById("luckyBox").innerText||""); const sig=document.getElementById("sig").textContent||""; ctx.fillStyle="#2c2c2c"; ctx.font="bold 64px 'Noto Sans JP', sans-serif"; ctx.fillText("NAYUN SHRINE",120,220); ctx.font="900 96px 'Noto Sans JP', sans-serif"; ctx.fillText(g,120,340); ctx.font="700 54px 'Noto Sans JP', sans-serif"; wrapText(ctx,t,120,420,840,56); ctx.font="32px 'Noto Sans JP', sans-serif"; wrapText(ctx,b,120,520,840,44); ctx.font="24px monospace"; ctx.fillText(sig,120,1200); const a=document.createElement("a"); a.download="nayun_omikuji.png"; a.href=c.toDataURL("image/png"); a.click(); }
function wrapText(ctx,text,x,y,maxW,lh){ const words=text.split(/\s+/), lines=[]; let line=""; for(const w of words){ const t=line?line+" "+w:w; if(ctx.measureText(t).width>maxW){ lines.push(line); line=w; } else line=t; } lines.push(line); lines.forEach((l,i)=>ctx.fillText(l,x,y+i*lh)); }

/* ====== Ema (wish wall) ====== */
const EMK_USER = "nayun.user";      // { id, nick }
const EMK_WISH_LOCAL = "nayun.ema.v2"; // local array
const EMA_BACKEND = () => SUPABASE_URL && SUPABASE_ANON;

// Auth (nickname)
function uuidv4(){return 'xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx'.replace(/[xy]/g,c=>{const r=Math.random()*16|0,v=c==='x'?r:(r&0x3|0x8);return v.toString(16);});}
function getUser(){ try{ return JSON.parse(localStorage.getItem(EMK_USER)||'null'); }catch(e){ return null; } }
function setUser(u){ if(u) localStorage.setItem(EMK_USER, JSON.stringify(u)); else localStorage.removeItem(EMK_USER); renderAuth(); }
function renderAuth(){ const me=getUser(); const tag=document.getElementById('meTag'); const si=document.getElementById('btnSign'); const so=document.getElementById('btnSignOut'); if(!si||!so||!tag) return; if(me){ si.style.display='none'; so.style.display='inline-block'; tag.textContent='@'+me.nick+' • '+me.id.slice(0,8); } else { si.style.display='inline-block'; so.style.display='none'; tag.textContent=''; } }

// Supabase REST adapters
async function sbList(){ const r= await fetch(`${SUPABASE_URL}/rest/v1/ema_wishes?select=*&order=created_at.desc`,{headers:{apikey:SUPABASE_ANON, Authorization:`Bearer ${SUPABASE_ANON}`}}); return await r.json(); }
async function sbAdd(w){ const r= await fetch(`${SUPABASE_URL}/rest/v1/ema_wishes`,{method:'POST', headers:{'Content-Type':'application/json', apikey:SUPABASE_ANON, Authorization:`Bearer ${SUPABASE_ANON}`}, body:JSON.stringify(w)}); if(!r.ok) throw new Error('add_failed'); }
// Delete: user can delete own; owner can delete any
async function sbDel(id, user_id, any=false){ const query = any ? `id=eq.${id}` : `id=eq.${id}&user_id=eq.${user_id}`; await fetch(`${SUPABASE_URL}/rest/v1/ema_wishes?${query}`,{method:'DELETE', headers:{apikey:SUPABASE_ANON, Authorization:`Bearer ${SUPABASE_ANON}`}}); }

// Local adapters
function lcList(){ try{ return JSON.parse(localStorage.getItem(EMK_WISH_LOCAL)||'[]'); }catch(e){ return []; } }
function lcSave(arr){ localStorage.setItem(EMK_WISH_LOCAL, JSON.stringify(arr)); }
async function emaList(){ if(EMA_BACKEND()) return await sbList(); return lcList().sort((a,b)=>b.t-a.t); }
async function emaAdd(text){ const me=getUser(); if(!me) throw new Error('no_user'); const row={ id: uuidv4(), user_id: me.id, nick: me.nick, wish: text, created_at: new Date().toISOString(), t: Date.now() }; if(EMA_BACKEND()) await sbAdd(row); else { const arr=lcList(); arr.push(row); lcSave(arr); } }
async function emaDel(id){ const me=getUser(); if(EMA_BACKEND()) { await sbDel(id, me?.id, ownerMode); } else { const arr=lcList(); const idx = ownerMode ? arr.findIndex(x=>x.id===id) : arr.findIndex(x=>x.id===id && x.user_id===(me?.id)); if(idx>=0){ arr.splice(idx,1); lcSave(arr); } } }

function serializeEma(arr){ return btoa(unescape(encodeURIComponent(JSON.stringify(arr)))); }
function deserializeEma(s){ try{ return JSON.parse(decodeURIComponent(escape(atob(s)))); }catch(e){ return []; } }

async function renderEma(){ const ul=document.getElementById('emaList'); if(!ul) return; ul.innerHTML='';
  const url = new URL(location.href); const snap = url.searchParams.get('ew');
  let list = []; if(snap){ list = deserializeEma(snap); } else { list = await emaList(); }
  if(list.length===0){ const li=document.createElement('li'); li.className='muted'; li.textContent = {ja:'まだ絵馬がありません。', en:'No wishes yet.', ko:'아직 소원이 없어요.'}[currentLang]; ul.appendChild(li); return; }
  const me=getUser();
  list.slice(0,100).forEach(w=>{ const li=document.createElement('li'); const you = me && (w.user_id===me.id); const txt = w.wish || w.w; li.innerHTML = `🎋 <b>${w.nick||'Anonymous'}</b>：${txt}`;
    if((you || ownerMode) && !snap){ const btn=document.createElement('button'); btn.className='btn secondary'; btn.style.marginLeft='8px'; btn.textContent={ja:'削除',en:'Delete',ko:'삭제'}[currentLang]; btn.addEventListener('click', async()=>{ await emaDel(w.id); renderEma(); }); li.appendChild(btn); }
    ul.appendChild(li);
  });
}

function renderEmaInfo(){ const el=document.getElementById('emaInfo'); const text={ ja: EMA_BACKEND()? 'みんなの絵馬は公開で閲覧できます。削除は本人のみ／オーナーは全件削除可。' : 'この端末に保存。公開は「公開リンクをコピー」。削除は本人のみ／オーナーは全件削除可。', en: EMA_BACKEND()? 'All ema are publicly viewable. Authors can delete their own; owner can delete any.' : 'Saved on this device. Share via “Copy Public Link”. Authors can delete their own; owner can delete any.', ko: EMA_BACKEND()? '에마는 모두가 볼 수 있어요. 작성자는 본인 것만 삭제, 오너는 전체 삭제 가능.' : '이 기기에 저장됩니다. “공개 링크 복사”로 공유. 작성자는 본인만 삭제, 오너는 전체 삭제 가능.' }[currentLang]; el.textContent=text; document.getElementById('emaPublic').style.display = EMA_BACKEND()? 'none':'inline-block'; }
async function copyEmaPublic(){ const url=new URL(location.href); const arr= await emaList(); url.searchParams.set('ew', serializeEma(arr)); navigator.clipboard.writeText(url.toString()).then(()=>{ document.getElementById('emaPublicHint').textContent={ja:'リンクをコピーしました', en:'Link copied', ko:'링크를 복사했어요'}[currentLang]; setTimeout(()=>document.getElementById('emaPublicHint').textContent='',2000); }); }

/* ====== Events (local with snapshot share) ====== */
const EV_LOCAL_KEY = "nayun.events";
let ownerMode = false; let snapshotMode = false;
function loadLocalEvents(){ return JSON.parse(localStorage.getItem(EV_LOCAL_KEY)||"[]"); }
function saveLocalEvents(arr){ localStorage.setItem(EV_LOCAL_KEY, JSON.stringify(arr)); renderEvents(); }
function serializeEvents(arr){ return btoa(unescape(encodeURIComponent(JSON.stringify(arr)))); }
function deserializeEvents(s){ try{ return JSON.parse(decodeURIComponent(escape(atob(s)))); }catch(e){ return []; } }
function setOwnerUI(){ const bar = document.getElementById("ownerBar"); const form = document.getElementById("eventFormWrap"); const logout=document.getElementById("ownerLogout"); const publish=document.getElementById("publishBtn"); bar.style.display = "block"; document.getElementById("ownerLogin").style.display = ownerMode?"none":"inline-block"; logout.style.display = ownerMode?"inline-block":"none"; publish.style.display = ownerMode?"inline-block":"none"; form.style.display = ownerMode?"block":"none"; }
function renderEvents(){ const wrap = document.getElementById("eventList"); if(!wrap) return; wrap.innerHTML = ""; const url = new URL(location.href); const evParam = url.searchParams.get("ev"); const list = evParam ? (snapshotMode = true, deserializeEvents(evParam)) : loadLocalEvents(); list.sort((a,b)=> (a.date||"")+(a.time||"") < (b.date||"")+(b.time||"") ? -1 : 1); if(list.length===0){ const p=document.createElement("p"); p.className="muted"; p.textContent = {ja:"イベントはまだありません。", en:"No events yet.", ko:"등록된 이벤트가 없습니다."}[currentLang]; wrap.appendChild(p); } list.forEach((ev, idx)=>{ const box = document.createElement("div"); box.className = "event"; const top = document.createElement("div"); top.className = "top"; const left = document.createElement("div"); left.style.display="flex"; left.style.gap="8px"; left.style.alignItems="center"; const b = document.createElement("span"); b.className = "badge"; b.textContent = (ev.date||"") + (ev.time?` ${ev.time}`:""); const t = document.createElement("span"); t.className = "title"; t.textContent = ev.title||"(no title)"; left.appendChild(b); left.appendChild(t); top.appendChild(left); if(ownerMode && !snapshotMode){ const del = document.createElement("button"); del.className="btn secondary"; del.textContent = {ja:"削除", en:"Delete", ko:"삭제"}[currentLang]; del.addEventListener('click', ()=>{ const cur=loadLocalEvents(); cur.splice(idx,1); saveLocalEvents(cur); }); top.appendChild(del); } box.appendChild(top); if(ev.desc){ const d=document.createElement("div"); d.className="desc"; d.textContent = ev.desc; box.appendChild(d); } if(ev.link){ const a=document.createElement("a"); a.href=ev.link; a.target="_blank"; a.rel="noopener"; a.className="link"; a.textContent = ev.link; box.appendChild(a); } wrap.appendChild(box); }); }
function copyPublicLink(){ const list = loadLocalEvents(); const url = new URL(location.href); url.searchParams.delete("n"); url.searchParams.delete("s"); url.searchParams.delete("l"); url.searchParams.set("ev", serializeEvents(list)); navigator.clipboard.writeText(url.toString()).then(()=>{ alert({ja:"公開リンクをコピーしました", en:"Public link copied", ko:"공개 링크를 복사했어요"}[currentLang]); }); }

/* ====== Init ====== */
function initFromStorage(){
  const saved = localStorage.getItem("nayun.omikuji.last");
  const url = new URL(location.href); const qn=url.searchParams.get("n"); const qs=url.searchParams.get("s"); const ql=url.searchParams.get("l");
  let storedLang=null; try{ storedLang=localStorage.getItem('nayun.lang'); }catch(e){}
  const chosenLang = ql && I18N[ql] ? ql : (storedLang && I18N[storedLang] ? storedLang : 'ja');
  setLang(chosenLang);

  if(qn){ document.getElementById("seed").value = qn; }
  if(qs){ document.getElementById("scope").value = qs; }
  if(qn){ switchView("omikuji"); draw(true); }
  else if(saved){ const obj=JSON.parse(saved); if(obj.name) document.getElementById("seed").value=obj.name; if(obj.scope) document.getElementById("scope").value=obj.scope; }
  if(!hasDrawn) setHint(I18N[currentLang].inputHint);

  // Auth/Ema
  renderAuth();
  renderEmaInfo();
  renderEma();

  // Events
  ownerMode = sessionStorage.getItem("nayun.owner") === "1";
  if(new URL(location.href).searchParams.get("admin") === OWNER_KEY && OWNER_KEY !== "CHANGE_ME"){ ownerMode = true; sessionStorage.setItem("nayun.owner","1"); }
  setOwnerUI();
  renderEvents();
}

// Bindings
document.getElementById("drawBtn").addEventListener("click", draw);
document.getElementById("shareBtn").addEventListener("click", share);
document.getElementById("saveBtn").addEventListener("click", saveImage);

// Auth buttons
const btnSign=document.getElementById('btnSign'); const btnOut=document.getElementById('btnSignOut');
btnSign.addEventListener('click', ()=>{ const nick=(document.getElementById('authNick').value||'').trim(); if(!nick){ alert({ja:'ニックネームを入力',en:'Enter nickname',ko:'닉네임을 입력하세요'}[currentLang]); return; } const me=getUser()||{id:uuidv4()}; me.nick=nick; setUser(me); renderEma(); });
btnOut.addEventListener('click', ()=>{ setUser(null); renderEma(); });

// Ema
document.getElementById('emaAdd').addEventListener('click', async()=>{ const txt=(document.getElementById('emaWish').value||'').trim(); if(!txt) return; const me=getUser(); if(!me){ alert({ja:'まずログインしてください',en:'Please sign in first',ko:'먼저 로그인하세요'}[currentLang]); return; } await emaAdd(txt); document.getElementById('emaWish').value=''; renderEma(); });
document.getElementById('emaPublic').addEventListener('click', copyEmaPublic);

// Events
document.getElementById("ownerLogin").addEventListener("click", ()=>{ const input = prompt({ja:"オーナーキー", en:"Owner Key", ko:"오너 키"}[currentLang] + "?"); if(input && input === OWNER_KEY && OWNER_KEY !== "CHANGE_ME"){ ownerMode = true; sessionStorage.setItem("nayun.owner","1"); setOwnerUI(); renderEvents(); } else { alert({ja:'キーが違います',en:'Wrong key',ko:'키가 올바르지 않습니다'}[currentLang]); }});
document.getElementById("ownerLogout").addEventListener("click", ()=>{ ownerMode=false; sessionStorage.removeItem("nayun.owner"); setOwnerUI(); renderEvents(); });
document.getElementById("publishBtn").addEventListener("click", copyPublicLink);
document.getElementById("addEvent").addEventListener("click", ()=>{ if(!ownerMode){ alert({ja:"権限がありません",en:"No permission",ko:"권한이 없습니다"}[currentLang]); return; } const title=document.getElementById("evTitle").value.trim(); const date=document.getElementById("evDate").value; const time=document.getElementById("evTime").value; const desc=document.getElementById("evDesc").value.trim(); const link=document.getElementById("evLink").value.trim(); if(!title){ alert({ja:"タイトル必須",en:"Title required",ko:"제목이 필요합니다"}[currentLang]); return; } const cur=loadLocalEvents(); cur.push({title,date,time,desc,link,created:Date.now()}); saveLocalEvents(cur); document.getElementById("evTitle").value=""; document.getElementById("evDesc").value=""; document.getElementById("evLink").value=""; });
document.getElementById("clearEvents").addEventListener("click", ()=>{ if(!ownerMode) return; if(confirm({ja:"すべて削除しますか？", en:"Clear all events?", ko:"모두 삭제할까요?"}[currentLang])) saveLocalEvents([]); });

initFromStorage();
</script>
</body>
</html>
