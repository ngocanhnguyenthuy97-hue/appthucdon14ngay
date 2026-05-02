

<style>
* { box-sizing: border-box; margin: 0; padding: 0; }
:root {
  --p1: #fde8f0; --p1t: #a03060;
  --p2: #e8f4fd; --p2t: #1a5a8a;
  --p3: #e8fdf0; --p3t: #1a6a40;
  --p4: #fdf5e8; --p4t: #8a5a1a;
  --p5: #f0e8fd; --p5t: #5a1a8a;
  --pg: #f5f0fb; --pcard: #fffcfe;
  --text1: #2a2235; --text2: #6b6080; --text3: #9b90b0;
  --br: 16px; --br2: 12px;
}
body { font-family: var(--font-sans); background: var(--pg); }
.screen { display: none; padding: 0 0 2rem; }
.screen.active { display: block; }

/* NAV */
.nav { display: flex; align-items: center; gap: 10px; padding: 1.2rem 0 1rem; margin-bottom: 0.5rem; }
.nav-title { font-size: 20px; font-weight: 500; color: var(--text1); }
.btn-home { display: flex; align-items: center; gap: 6px; padding: 7px 14px; background: white; border: 0.5px solid #ddd6f3; border-radius: 20px; font-size: 13px; color: var(--p5t); cursor: pointer; font-weight: 500; }
.btn-home svg { width: 15px; height: 15px; }

/* HOME */
.home-hero { background: white; border-radius: var(--br); padding: 1.5rem; margin-bottom: 1rem; border: 0.5px solid #ead6f5; }
.home-hero-title { font-size: 22px; font-weight: 500; color: var(--text1); margin-bottom: 6px; }
.home-hero-sub { font-size: 14px; color: var(--text2); line-height: 1.6; }
.stat-row { display: grid; grid-template-columns: repeat(4,1fr); gap: 8px; margin-bottom: 1rem; }
.scard { border-radius: var(--br2); padding: 0.9rem 0.75rem; text-align: center; }
.scard-v { font-size: 20px; font-weight: 500; margin-bottom: 3px; }
.scard-l { font-size: 11px; opacity: 0.75; }
.menu-cards { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-bottom: 1rem; }
.menu-card { background: white; border-radius: var(--br); padding: 1.25rem; cursor: pointer; border: 0.5px solid #e8e0f5; transition: transform 0.12s; }
.menu-card:hover { transform: translateY(-2px); }
.mc-icon { width: 44px; height: 44px; border-radius: 12px; display: flex; align-items: center; justify-content: center; margin-bottom: 10px; font-size: 20px; }
.mc-title { font-size: 15px; font-weight: 500; color: var(--text1); margin-bottom: 4px; }
.mc-sub { font-size: 12px; color: var(--text2); line-height: 1.5; }

/* WEEK TABS */
.wtabs { display: flex; gap: 8px; margin-bottom: 1rem; }
.wtab { flex: 1; padding: 9px; border: 0.5px solid #ddd6f3; border-radius: 20px; font-size: 13px; cursor: pointer; background: white; color: var(--text2); text-align: center; font-weight: 500; }
.wtab.on { background: var(--p5); color: var(--p5t); border-color: #c4a8f0; }

/* DAY GRID */
.day-grid { display: grid; grid-template-columns: repeat(7,1fr); gap: 6px; margin-bottom: 1.25rem; }
.day-btn { padding: 10px 4px; border-radius: var(--br2); font-size: 11px; cursor: pointer; background: white; color: var(--text2); text-align: center; border: 0.5px solid #e8e0f5; }
.day-btn .dn { font-size: 10px; color: var(--text3); display: block; margin-bottom: 3px; }
.day-btn.on { background: var(--p5); color: var(--p5t); border-color: #c4a8f0; font-weight: 500; }

/* CAL SUMMARY BAR */
.cal-bar { background: white; border-radius: var(--br); padding: 1rem 1.25rem; margin-bottom: 1rem; display: flex; align-items: center; gap: 14px; border: 0.5px solid #e8e0f5; }
.cal-num { font-size: 26px; font-weight: 500; color: var(--text1); }
.cal-lbl { font-size: 12px; color: var(--text2); }
.deficit-pill { background: var(--p3); color: var(--p3t); font-size: 12px; font-weight: 500; padding: 4px 12px; border-radius: 20px; }
.macro-stack { flex: 1; }
.macro-row { display: flex; align-items: center; gap: 6px; margin-bottom: 4px; }
.macro-row:last-child { margin-bottom: 0; }
.macro-lbl { font-size: 11px; color: var(--text3); width: 50px; }
.macro-track { flex: 1; height: 6px; background: #f0ebfa; border-radius: 3px; overflow: hidden; }
.macro-fill { height: 100%; border-radius: 3px; }
.macro-val { font-size: 11px; color: var(--text2); width: 28px; text-align: right; }

/* MEAL CARDS */
.meal-pair { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-bottom: 1rem; }
.meal-card { background: white; border-radius: var(--br); padding: 1.1rem 1.2rem; border: 0.5px solid #e8e0f5; }
.meal-tag { display: inline-flex; align-items: center; gap: 5px; font-size: 11px; font-weight: 500; padding: 3px 10px; border-radius: 20px; margin-bottom: 10px; }
.meal-name { font-size: 14px; font-weight: 500; color: var(--text1); margin-bottom: 10px; line-height: 1.4; }
.item-row { display: flex; justify-content: space-between; align-items: center; padding: 5px 0; border-bottom: 0.5px solid #f0ebf8; }
.item-row:last-of-type { border-bottom: none; }
.item-n { font-size: 13px; color: var(--text2); }
.item-q { font-size: 12px; color: var(--text3); background: #f5f0fb; padding: 2px 8px; border-radius: 8px; font-family: var(--font-mono); }
.meal-footer { margin-top: 10px; display: flex; align-items: center; gap: 6px; }
.cal-pill { background: var(--p3); color: var(--p3t); font-size: 12px; font-weight: 500; padding: 3px 10px; border-radius: 20px; }
.macro-mini { font-size: 11px; color: var(--text3); }

/* ALT BOX */
.alt-box { background: var(--p4); border-radius: var(--br2); padding: 0.9rem 1.1rem; margin-bottom: 1.25rem; }
.alt-title { font-size: 12px; font-weight: 500; color: var(--p4t); margin-bottom: 5px; display: flex; align-items: center; gap: 5px; }
.alt-body { font-size: 13px; color: #6b5a30; line-height: 1.6; }

/* TIPS */
.tips-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
.tip-card { background: white; border-radius: var(--br); padding: 1rem; border: 0.5px solid #e8e0f5; }
.tip-icon { width: 34px; height: 34px; border-radius: 10px; display: flex; align-items: center; justify-content: center; margin-bottom: 8px; font-size: 16px; }
.tip-title { font-size: 13px; font-weight: 500; color: var(--text1); margin-bottom: 5px; }
.tip-body { font-size: 12px; color: var(--text2); line-height: 1.6; }
.section-title { font-size: 15px; font-weight: 500; color: var(--text1); margin-bottom: 10px; display: flex; align-items: center; gap: 8px; }
.section-title::before { content: ''; display: block; width: 4px; height: 18px; border-radius: 2px; background: currentColor; opacity: 0.3; }

/* SHOPPING */
.shop-summary { display: grid; grid-template-columns: repeat(3,1fr); gap: 8px; margin-bottom: 1.25rem; }
.cat-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
.cat-card { background: white; border-radius: var(--br); padding: 1.1rem 1.2rem; border: 0.5px solid #e8e0f5; }
.cat-header { display: flex; align-items: center; gap: 8px; margin-bottom: 10px; padding-bottom: 8px; border-bottom: 0.5px solid #f0ebf8; }
.shape { width: 22px; height: 22px; flex-shrink: 0; }
.cat-label { font-size: 14px; font-weight: 500; color: var(--text1); }
.cat-count { font-size: 11px; color: var(--text3); margin-left: auto; background: #f5f0fb; padding: 2px 8px; border-radius: 20px; }
.shop-item { display: flex; justify-content: space-between; align-items: center; padding: 5px 0; border-bottom: 0.5px solid #f0ebf8; }
.shop-item:last-child { border-bottom: none; }
.shop-name { font-size: 13px; color: var(--text2); }
.shop-qty { font-size: 12px; color: var(--text3); background: #f5f0fb; padding: 2px 8px; border-radius: 8px; font-family: var(--font-mono); }
.tip-shop { background: var(--p3); border-radius: var(--br2); padding: 0.9rem 1.1rem; margin-top: 1rem; }
.tip-shop-title { font-size: 12px; font-weight: 500; color: var(--p3t); margin-bottom: 5px; }
.tip-shop-body { font-size: 13px; color: #1a5a40; line-height: 1.6; }
</style>

<h2 class="sr-only">Ứng dụng thực đơn giảm cân 14 ngày – thực đơn và danh mục mua sắm</h2>

<div id="home" class="screen active">
  <div class="nav"><span class="nav-title">Thực đơn giảm cân</span></div>
  <div class="home-hero">
    <div class="home-hero-title">Chào mừng trở lại!</div>
    <div class="home-hero-sub">Kế hoạch 14 ngày · 74kg → 64kg · Gạo trắng · 2 bữa/ngày</div>
  </div>
  <div class="stat-row">
    <div class="scard" style="background:var(--p1);color:var(--p1t);">
      <div class="scard-v">28.2</div><div class="scard-l">BMI</div>
    </div>
    <div class="scard" style="background:var(--p2);color:var(--p2t);">
      <div class="scard-v">1,820</div><div class="scard-l">TDEE kcal</div>
    </div>
    <div class="scard" style="background:var(--p3);color:var(--p3t);">
      <div class="scard-v">1,200</div><div class="scard-l">Mục tiêu</div>
    </div>
    <div class="scard" style="background:var(--p4);color:var(--p4t);">
      <div class="scard-v">~620</div><div class="scard-l">Thâm hụt</div>
    </div>
  </div>
  <div class="menu-cards">
    <div class="menu-card" onclick="go('menu')">
      <div class="mc-icon" style="background:var(--p5);">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#7c3aed" stroke-width="2" stroke-linecap="round"><path d="M3 6h18M3 12h18M3 18h12"/></svg>
      </div>
      <div class="mc-title">Thực đơn 14 ngày</div>
      <div class="mc-sub">Xem chi tiết từng ngày, calo và macro</div>
    </div>
    <div class="menu-card" onclick="go('shop')">
      <div class="mc-icon" style="background:var(--p3);">
        <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="#16a34a" stroke-width="2" stroke-linecap="round"><path d="M6 2L3 6v14a2 2 0 002 2h14a2 2 0 002-2V6l-3-4z"/><line x1="3" y1="6" x2="21" y2="6"/><path d="M16 10a4 4 0 01-8 0"/></svg>
      </div>
      <div class="mc-title">Danh mục mua sắm</div>
      <div class="mc-sub">Thực phẩm cần mua theo tuần</div>
    </div>
  </div>
  <div class="section-title" style="color:var(--p5t);">Lưu ý học buổi tối</div>
  <div class="tips-grid">
    <div class="tip-card">
      <div class="tip-icon" style="background:var(--p1);">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#a03060" stroke-width="2"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>
      </div>
      <div class="tip-title">Thời điểm ăn</div>
      <div class="tip-body">Ăn bữa tối trước 19h. Nếu học đến 22h+ thêm 1 trứng luộc hoặc sữa đậu nành không đường.</div>
    </div>
    <div class="tip-card">
      <div class="tip-icon" style="background:var(--p2);">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#1a5a8a" stroke-width="2"><path d="M12 2a7 7 0 017 7c0 5-7 13-7 13S5 14 5 9a7 7 0 017-7z"/></svg>
      </div>
      <div class="tip-title">Uống đủ nước</div>
      <div class="tip-body">Tối thiểu 2 lít/ngày. Uống 1 ly nước ấm trước khi học giúp tỉnh táo và giảm đói giả.</div>
    </div>
    <div class="tip-card">
      <div class="tip-icon" style="background:var(--p3);">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#1a6a40" stroke-width="2"><path d="M12 2C6 2 3 8 3 12s3 10 9 10 9-6 9-10S18 2 12 2z"/><path d="M12 8v8M8 12h8"/></svg>
      </div>
      <div class="tip-title">Snack học tối</div>
      <div class="tip-body">Chuối 1 trái, 5–6 hạt hạnh nhân hoặc 100ml sữa đậu nành. Không vượt 150 kcal.</div>
    </div>
    <div class="tip-card">
      <div class="tip-icon" style="background:var(--p4);">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#8a5a1a" stroke-width="2"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
      </div>
      <div class="tip-title">Bổ sung vi chất</div>
      <div class="tip-body">Uống vitamin tổng hợp buổi sáng để tránh thiếu vi chất. Ưu tiên vitamin B, sắt, kẽm.</div>
    </div>
  </div>
</div>

<div id="menu" class="screen">
  <div class="nav">
    <button class="btn-home" onclick="go('home')">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><path d="M3 9l9-7 9 7v11a2 2 0 01-2 2H5a2 2 0 01-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg>
      Home
    </button>
    <span class="nav-title">Thực đơn 14 ngày</span>
  </div>
  <div class="wtabs">
    <button class="wtab on" onclick="setMWeek(1)">Tuần 1 (Ngày 1–7)</button>
    <button class="wtab" onclick="setMWeek(2)">Tuần 2 (Ngày 8–14)</button>
  </div>
  <div class="day-grid" id="dayGrid"></div>
  <div class="cal-bar" id="calBar"></div>
  <div class="section-title" style="color:var(--p5t);">Bữa ăn trong ngày</div>
  <div class="meal-pair" id="mealPair"></div>
  <div class="alt-box" id="altBox"></div>
</div>

<div id="shop" class="screen">
  <div class="nav">
    <button class="btn-home" onclick="go('home')">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><path d="M3 9l9-7 9 7v11a2 2 0 01-2 2H5a2 2 0 01-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg>
      Home
    </button>
    <span class="nav-title">Danh mục mua sắm</span>
  </div>
  <div class="wtabs">
    <button class="wtab on" onclick="setSWeek(1)">Tuần 1 (Ngày 1–7)</button>
    <button class="wtab" onclick="setSWeek(2)">Tuần 2 (Ngày 8–14)</button>
  </div>
  <div class="shop-summary" id="shopSummary"></div>
  <div class="section-title" style="color:var(--p3t);">Danh sách thực phẩm</div>
  <div class="cat-grid" id="catGrid"></div>
  <div class="tip-shop" id="shopTip"></div>
</div>

<script>
const DAYS = ["T2","T3","T4","T5","T6","T7","CN"];
let mWeek=1, mDay=0, sWeek=1;

function go(id) {
  document.querySelectorAll('.screen').forEach(s=>s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
}

const meals = {
  1:[
    {lunch:{name:"Cơm trắng + ức gà luộc + rau muống",items:[["Gạo trắng (sống)","60g"],["Ức gà","130g"],["Rau muống","250g"],["Nước mắm + chanh","ít"]],cal:415,p:36,c:48,f:5},dinner:{name:"Trứng hấp + đậu hũ sốt cà chua",items:[["Trứng gà","2 quả"],["Đậu hũ non","100g"],["Cà chua","1 trái"],["Rau cải luộc","200g"]],cal:335,p:22,c:18,f:14},alt:"Bận: cơm ít (½ chén) + 3 trứng luộc + dưa leo · Tối: cháo trắng + cá kho"},
    {lunch:{name:"Cơm trắng + cá basa hấp gừng + cải xanh",items:[["Gạo trắng (sống)","60g"],["Cá basa","150g"],["Cải xanh luộc","250g"],["Gừng + nước mắm","ít"]],cal:420,p:33,c:49,f:7},dinner:{name:"Thịt heo nạc luộc + canh bí đao",items:[["Thịt heo nạc","100g"],["Bí đao","200g"],["Cà rốt","60g"],["Hành lá","ít"]],cal:315,p:24,c:20,f:8},alt:"Không có cá basa: thay tôm luộc 130g · Canh bí: thay canh rau ngót"},
    {lunch:{name:"Cơm trắng + tôm rang tỏi + bông cải",items:[["Gạo trắng (sống)","60g"],["Tôm tươi","130g"],["Bông cải xanh","250g"],["Tỏi + ½ muỗng dầu","5ml"]],cal:430,p:31,c:50,f:7},dinner:{name:"Súp đậu xanh + trứng luộc",items:[["Đậu xanh cà","70g"],["Cà rốt + nấm","80g"],["Trứng gà","1 quả"],["Hành + tiêu","ít"]],cal:340,p:20,c:46,f:6},alt:"Súp đậu xanh nấu nhiều để dùng 2 ngày · Tôm thay mực luộc 130g"},
    {lunch:{name:"Cháo gà trắng + rau cải",items:[["Gạo trắng","55g"],["Ức gà","120g"],["Cà rốt + nấm rơm","100g"],["Gừng + hành","ít"]],cal:395,p:30,c:45,f:5},dinner:{name:"Cá basa áp chảo + salad dưa leo cà chua",items:[["Cá basa","150g"],["Dưa leo","120g"],["Cà chua","1 trái"],["Chanh + muối","ít"]],cal:330,p:28,c:14,f:10},alt:"Cháo nấu trước hâm lại · Salad thêm 1 trứng luộc nếu đói"},
    {lunch:{name:"Cơm trắng + thịt heo kho gừng + rau",items:[["Gạo trắng (sống)","60g"],["Thịt heo nạc","110g"],["Rau muống / cải luộc","250g"],["Gừng + nước mắm","ít"]],cal:420,p:30,c:50,f:8},dinner:{name:"Đậu hũ non hấp + canh rau ngót trứng",items:[["Đậu hũ non","150g"],["Trứng gà","1 quả"],["Rau ngót","120g"],["Hành + tỏi","ít"]],cal:335,p:22,c:20,f:13},alt:"Cuối tuần bận: bánh mì 2 lát + ức gà + dưa leo thay bữa trưa"},
    {lunch:{name:"Cơm trắng + cá kho gừng tiêu + bắp cải",items:[["Gạo trắng (sống)","60g"],["Cá trắm / cá diêu hồng","150g"],["Bắp cải luộc","250g"],["Gừng + nước mắm","ít"]],cal:425,p:32,c:50,f:7},dinner:{name:"Trứng chiên ít dầu + canh chua rau muống",items:[["Trứng gà","2 quả"],["½ muỗng dầu","5ml"],["Rau muống","150g"],["Dứa + cà chua","60g"]],cal:330,p:18,c:20,f:16},alt:"Cá kho: thay cá hú hoặc cá basa · Canh chua: thay me bằng giấm + dứa"},
    {lunch:{name:"Cơm trắng + ức gà nướng + xà lách",items:[["Gạo trắng (sống)","60g"],["Ức gà","130g"],["Xà lách + cà chua + dưa","200g"],["Chanh + tỏi","ít"]],cal:410,p:33,c:48,f:7},dinner:{name:"Đậu hũ chiên sả + khoai lang hấp",items:[["Đậu hũ cứng","130g"],["Khoai lang","90g"],["Sả + ớt","ít"],["½ muỗng dầu","5ml"]],cal:360,p:18,c:44,f:12},alt:"Khoai lang thay khoai tây luộc 100g · Đậu hũ chiên thay đậu hũ hấp"},
  ],
  2:[
    {lunch:{name:"Cơm trắng + thịt bò nạc xào cải",items:[["Gạo trắng (sống)","60g"],["Thịt bò nạc","100g"],["Cải thảo / cải ngọt","250g"],["Tỏi + 5ml dầu","5ml"]],cal:435,p:32,c:50,f:10},dinner:{name:"Súp gà nấm trứng",items:[["Ức gà","100g"],["Nấm rơm / bào ngư","80g"],["Cà rốt + hành","80g"],["Trứng gà","1 quả"]],cal:325,p:28,c:18,f:8},alt:"Bò không có: thay thịt heo nạc 120g · Nấm: thay nấm đông cô"},
    {lunch:{name:"Cơm trắng + tôm hấp sả + rau cải",items:[["Gạo trắng (sống)","60g"],["Tôm tươi","140g"],["Rau cải / bok choy","250g"],["Sả + gừng","ít"]],cal:415,p:32,c:49,f:6},dinner:{name:"Đậu hũ non sốt cà chua + canh bầu",items:[["Đậu hũ non","150g"],["Cà chua","2 trái"],["Bầu / bí đao","200g"],["Hành + tỏi","ít"]],cal:300,p:16,c:22,f:10},alt:"Tôm thay mực luộc 130g · Canh bầu thay canh mướp hoặc bí xanh"},
    {lunch:{name:"Cơm trắng + cá ngừ xào dưa cải",items:[["Gạo trắng (sống)","60g"],["Cá ngừ hộp nước","120g"],["Dưa cải / bắp cải","200g"],["Tỏi + ít dầu","5ml"]],cal:400,p:30,c:48,f:8},dinner:{name:"Trứng hấp thịt băm + canh rau ngót",items:[["Trứng gà","2 quả"],["Thịt heo băm","50g"],["Rau ngót","120g"],["Hành + muối","ít"]],cal:310,p:24,c:14,f:14},alt:"Cá ngừ hộp không có: thay cá basa hấp 150g"},
    {lunch:{name:"Cháo trắng + gà + rau cải",items:[["Gạo trắng","55g"],["Ức gà","120g"],["Cải xanh + cà rốt","100g"],["Gừng + hành","ít"]],cal:390,p:30,c:44,f:5},dinner:{name:"Cá diêu hồng hấp + rau muống tỏi",items:[["Cá diêu hồng","150g"],["Rau muống xào tỏi","200g"],["½ muỗng dầu","5ml"],["Chanh + ớt","ít"]],cal:320,p:28,c:12,f:10},alt:"Cá diêu hồng thay cá hú hoặc cá trắm · Rau muống thay cải ngọt"},
    {lunch:{name:"Cơm trắng + gà kho gừng + su su",items:[["Gạo trắng (sống)","60g"],["Đùi gà không da","130g"],["Su su / bầu","220g"],["Gừng + nước mắm","ít"]],cal:425,p:30,c:51,f:8},dinner:{name:"Đậu hũ non + tôm + canh rau cải",items:[["Đậu hũ non","100g"],["Tôm tươi","80g"],["Rau cải ngọt","180g"],["Tỏi + hành","ít"]],cal:295,p:24,c:18,f:8},alt:"Su su không có: thay khoai lang 80g luộc · Tôm thay thịt heo nạc mỏng 80g"},
    {lunch:{name:"Cơm trắng + thịt heo nạc luộc + rau muống",items:[["Gạo trắng (sống)","60g"],["Thịt heo nạc","110g"],["Rau muống luộc","250g"],["Nước chấm gừng","ít"]],cal:415,p:30,c:50,f:8},dinner:{name:"Trứng chiên ít dầu + canh cải trắng",items:[["Trứng gà","2 quả"],["½ muỗng dầu","5ml"],["Cải trắng / bok choy","200g"],["Hành + tỏi","ít"]],cal:305,p:16,c:16,f:16},alt:"Đói tối: thêm 1 hộp sữa chua không đường 100ml (~65 kcal)"},
    {lunch:{name:"Cơm trắng + gà nướng chanh + salad",items:[["Gạo trắng (sống)","60g"],["Ức gà nướng","130g"],["Xà lách + cà chua + dưa","200g"],["Dầu olive + chanh","8ml"]],cal:425,p:34,c:49,f:12},dinner:{name:"Trứng + đậu hũ + canh rau củ tổng hợp",items:[["Trứng gà","2 quả"],["Đậu hũ cứng","100g"],["Bí đao + cà rốt + nấm","200g"],["Hành + gia vị","ít"]],cal:335,p:22,c:20,f:14},alt:"Tráng miệng: 1 trái chuối chín hoặc 100g sữa chua không đường"},
  ]
};

const shopData = {
  1:{summary:{items:28,est:"250.000–320.000",days:7},tip:"Mua thịt, cá, tôm vào đầu tuần – ngăn mát 2 ngày, còn lại bỏ ngăn đá. Rau xanh mua 2 lần/tuần (đầu + giữa) để đảm bảo tươi.",cats:[
    {label:"Thịt, cá, hải sản",shape:"meat",items:[["Ức gà","700g"],["Đùi gà không da","200g"],["Thịt heo nạc","400g"],["Cá basa / cá diêu hồng","450g"],["Cá trắm / cá chép","200g"],["Tôm tươi","260g"]]},
    {label:"Trứng & đậu hũ",shape:"egg",items:[["Trứng gà","14 quả (~2 vỉ)"],["Đậu hũ non","300g (3 hộp)"],["Đậu hũ cứng","300g (2 bìa)"],["Đậu xanh cà","70g"]]},
    {label:"Rau xanh & củ quả",shape:"veg",items:[["Rau muống","700g"],["Cải xanh / cải ngọt","500g"],["Bông cải xanh","300g"],["Bắp cải","300g"],["Bí đao","400g"],["Cà rốt","200g"],["Cà chua","6 trái"],["Dưa leo","4 trái"],["Xà lách","200g"],["Nấm rơm","100g"],["Khoai lang","200g"]]},
    {label:"Tinh bột & gia vị",shape:"grain",items:[["Gạo trắng","500g"],["Tỏi","1 củ"],["Gừng","1 nhánh"],["Sả","3 cây"],["Nước mắm","1 chai nhỏ"],["Dầu ăn / olive","100ml"],["Chanh","5 trái"]]}
  ]},
  2:{summary:{items:27,est:"240.000–300.000",days:7},tip:"Tuần 2 dùng cá ngừ hộp và thịt bò – tiết kiệm thời gian nấu. Mua thêm 1 lốc sữa chua không đường (lốc 4) dùng cuối tuần ~65 kcal/hộp.",cats:[
    {label:"Thịt, cá, hải sản",shape:"meat",items:[["Ức gà","600g"],["Đùi gà không da","130g"],["Thịt bò nạc","200g"],["Thịt heo nạc","400g"],["Cá diêu hồng / cá hú","430g"],["Cá ngừ hộp nước","2 hộp 120g"],["Tôm tươi","350g"]]},
    {label:"Trứng & đậu hũ",shape:"egg",items:[["Trứng gà","14 quả (~2 vỉ)"],["Đậu hũ non","400g (4 hộp)"],["Đậu hũ cứng","230g"],["Thịt heo băm","50g"]]},
    {label:"Rau xanh & củ quả",shape:"veg",items:[["Rau muống","600g"],["Cải ngọt / bok choy","600g"],["Bông cải xanh","200g"],["Cải thảo","300g"],["Bí đao / bầu","500g"],["Cà rốt","200g"],["Cà chua","8 trái"],["Dưa leo","4 trái"],["Xà lách","200g"],["Nấm đông cô","130g"],["Khoai lang","90g"],["Mướp đắng","100g"]]},
    {label:"Tinh bột & gia vị",shape:"grain",items:[["Gạo trắng","500g"],["Tỏi","1 củ"],["Gừng","1 nhánh"],["Sả","2 cây"],["Nước mắm","bổ sung nếu hết"],["Dầu ăn / olive","bổ sung nếu hết"],["Chanh","5 trái"]]}
  ]}
};

const shapeColors = {meat:"#fde8f0",egg:"#fdf5e8",veg:"#e8fdf0",grain:"#e8f4fd"};
const shapeSVG = {
  meat:`<svg class="shape" viewBox="0 0 22 22" fill="none"><ellipse cx="11" cy="11" rx="8" ry="6" fill="#fbbdd4" stroke="#e07090" stroke-width="1.2"/><circle cx="11" cy="11" r="3.5" fill="#f472a0" stroke="#e07090" stroke-width="1"/></svg>`,
  egg:`<svg class="shape" viewBox="0 0 22 22" fill="none"><ellipse cx="11" cy="12" rx="6" ry="8" fill="#fde68a" stroke="#d9a020" stroke-width="1.2"/><circle cx="11" cy="13" r="3" fill="#fbbf24" stroke="#d9a020" stroke-width="1"/></svg>`,
  veg:`<svg class="shape" viewBox="0 0 22 22" fill="none"><rect x="3" y="5" width="16" height="13" rx="6" fill="#86efac" stroke="#22a84a" stroke-width="1.2"/><path d="M11 5 Q13 2 16 4" stroke="#22a84a" stroke-width="1.2" fill="none" stroke-linecap="round"/></svg>`,
  grain:`<svg class="shape" viewBox="0 0 22 22" fill="none"><polygon points="11,3 19,8 19,15 11,20 3,15 3,8" fill="#bfdbfe" stroke="#3b7ee8" stroke-width="1.2"/><circle cx="11" cy="11" r="3" fill="#93c5fd" stroke="#3b7ee8" stroke-width="1"/></svg>`
};

function renderMenu() {
  const offset = mWeek===1?0:7;
  document.getElementById('dayGrid').innerHTML = DAYS.map((d,i)=>`
    <button class="day-btn ${i===mDay?'on':''}" onclick="setMDay(${i})">
      <span class="dn">${d}</span>Ngày ${offset+i+1}
    </button>`).join('');
  const day = meals[mWeek][mDay];
  const total = day.lunch.cal + day.dinner.cal;
  const tp = day.lunch.p+day.dinner.p, tc = day.lunch.c+day.dinner.c, tf = day.lunch.f+day.dinner.f;
  document.getElementById('calBar').innerHTML = `
    <div><div class="cal-num">${total}</div><div class="cal-lbl">kcal hôm nay</div></div>
    <span class="deficit-pill">Thâm hụt ~${1820-total} kcal</span>
    <div class="macro-stack">
      <div class="macro-row"><span class="macro-lbl">Protein</span><div class="macro-track"><div class="macro-fill" style="width:${Math.round(tp*4/total*100)}%;background:#86efac;"></div></div><span class="macro-val">${tp}g</span></div>
      <div class="macro-row"><span class="macro-lbl">Carb</span><div class="macro-track"><div class="macro-fill" style="width:${Math.round(tc*4/total*100)}%;background:#93c5fd;"></div></div><span class="macro-val">${tc}g</span></div>
      <div class="macro-row"><span class="macro-lbl">Chất béo</span><div class="macro-track"><div class="macro-fill" style="width:${Math.round(tf*9/total*100)}%;background:#fbbf24;"></div></div><span class="macro-val">${tf}g</span></div>
    </div>`;
  document.getElementById('mealPair').innerHTML = renderMealCard(day.lunch,'Bữa trưa · 11h–13h','var(--p5)','#7c3aed') + renderMealCard(day.dinner,'Bữa tối · 17h–19h','var(--p2)','#1a5a8a');
  document.getElementById('altBox').innerHTML = `
    <div class="alt-title">
      <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="#8a5a1a" stroke-width="2"><circle cx="12" cy="12" r="10"/><line x1="12" y1="8" x2="12" y2="12"/><line x1="12" y1="16" x2="12.01" y2="16"/></svg>
      Thay thế nếu bận / thiếu nguyên liệu
    </div>
    <div class="alt-body">${day.alt}</div>`;
}

function renderMealCard(m,label,bg,col) {
  return `<div class="meal-card">
    <div class="meal-tag" style="background:${bg};color:${col};">
      <svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>
      ${label}
    </div>
    <div class="meal-name">${m.name}</div>
    ${m.items.map(([n,q])=>`<div class="item-row"><span class="item-n">${n}</span><span class="item-q">${q}</span></div>`).join('')}
    <div class="meal-footer"><span class="cal-pill">${m.cal} kcal</span><span class="macro-mini">P:${m.p}g · C:${m.c}g · F:${m.f}g</span></div>
  </div>`;
}

function renderShop() {
  const d = shopData[sWeek];
  document.getElementById('shopSummary').innerHTML = `
    <div class="scard" style="background:var(--p5);color:var(--p5t);"><div class="scard-v">${d.summary.items}</div><div class="scard-l">loại thực phẩm</div></div>
    <div class="scard" style="background:var(--p3);color:var(--p3t);"><div class="scard-v" style="font-size:14px;padding-top:4px;">${d.summary.est}đ</div><div class="scard-l">chi phí ước tính</div></div>
    <div class="scard" style="background:var(--p2);color:var(--p2t);"><div class="scard-v">${d.summary.days} ngày</div><div class="scard-l">2 bữa/ngày</div></div>`;
  document.getElementById('catGrid').innerHTML = d.cats.map(cat=>`
    <div class="cat-card">
      <div class="cat-header">
        ${shapeSVG[cat.shape]}
        <span class="cat-label">${cat.label}</span>
        <span class="cat-count">${cat.items.length} món</span>
      </div>
      ${cat.items.map(([n,q])=>`<div class="shop-item"><span class="shop-name">${n}</span><span class="shop-qty">${q}</span></div>`).join('')}
    </div>`).join('');
  document.getElementById('shopTip').innerHTML = `
    <div class="tip-shop-title">Mẹo mua sắm tuần ${sWeek}</div>
    <div class="tip-shop-body">${d.tip}</div>`;
}

function setMWeek(w) {
  mWeek=w; mDay=0;
  document.querySelectorAll('#menu .wtab').forEach((t,i)=>t.classList.toggle('on',i===w-1));
  renderMenu();
}
function setMDay(i) { mDay=i; renderMenu(); }
function setSWeek(w) {
  sWeek=w;
  document.querySelectorAll('#shop .wtab').forEach((t,i)=>t.classList.toggle('on',i===w-1));
  renderShop();
}

renderMenu(); renderShop();
</script>
