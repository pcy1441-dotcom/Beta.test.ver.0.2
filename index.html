<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>머더 미스터리 추첨기 - BETA</title>
<style>
  :root {
    --bg-color: radial-gradient(circle at center, #1a1a1a 0%, #050505 100%);
    --card-bg: #f5f5f5;
    --accent-red: #cc0000;
    --zombie-green: #32CD32;
    --chill-blue: #87CEEB;
  }

  body { 
    font-family: 'Segoe UI', sans-serif; 
    background: var(--bg-color);
    margin: 0; padding: 20px; text-align: center; color: #e0e0e0; 
    min-height: 100vh; display: flex; flex-direction: column; justify-content: center;
    overflow-x: hidden;
  }

  h1 { color: #555; letter-spacing: 10px; font-weight: 300; margin-bottom: 20px; }

  #menu, #draw-area { 
    background: rgba(30, 30, 30, 0.9); padding: 30px; border-radius: 20px; 
    display: inline-block; border: 1px solid #333; box-shadow: 0 10px 30px rgba(0,0,0,0.5);
    max-width: 90%;
  }

  .info-container { margin: 20px 0; display: flex; justify-content: center; gap: 10px; flex-wrap: wrap; }
  .info-btn { 
    padding: 8px 15px; border-radius: 8px; border: 1px solid #444; background: #222; 
    color: #888; cursor: pointer; font-size: 12px; transition: 0.3s;
  }
  .info-btn:hover { background: #333; color: #fff; }

  .switch-container { margin: 20px 0; display: flex; align-items: center; justify-content: center; gap: 10px; }
  .switch { position: relative; display: inline-block; width: 50px; height: 24px; }
  .switch input { opacity: 0; width: 0; height: 0; }
  .slider { 
    position: absolute; cursor: pointer; top: 0; left: 0; right: 0; bottom: 0; 
    background-color: #444; transition: .4s; border-radius: 24px; 
  }
  .slider:before { 
    position: absolute; content: ""; height: 18px; width: 18px; left: 3px; bottom: 3px; 
    background-color: white; transition: .4s; border-radius: 50%; 
  }
  input:checked + .slider { background-color: var(--accent-red); }
  input:checked + .slider:before { transform: translateX(26px); }

  button.main-btn { 
    padding: 15px 40px; font-size: 18px; cursor: pointer; border-radius: 12px; border: none; 
    background: #2a2a2a; color: #fff; font-weight: bold; transition: 0.3s;
  }

  #result { 
    display: none; background: var(--card-bg); color: #111; padding: 50px 30px; 
    border-radius: 30px; margin: 20px auto; max-width: 400px; box-shadow: 0 20px 50px rgba(0,0,0,0.8);
  }

  #final-screen { display: none; background: #000; padding: 120px 20px; border-top: 2px solid #1a1a1a; }
  .final-murder-type { font-size: 75px; font-weight: 900; margin-bottom: 25px; text-transform: uppercase; }
  .type-standard { color: var(--accent-red); text-shadow: 0 0 15px rgba(204, 0, 0, 0.4); }
  .type-zombie { 
    background: linear-gradient(to bottom, #44ff44, #003300); -webkit-background-clip: text; -webkit-text-fill-color: transparent; 
  }
  .type-chillsear { color: #fff; text-shadow: 0 0 15px var(--chill-blue), 0 0 30px var(--chill-blue); }

  #modal {
    display: none; position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%);
    background: #222; border: 1px solid #444; padding: 25px; border-radius: 15px;
    z-index: 100; width: 280px; box-shadow: 0 0 50px rgba(0,0,0,1);
  }
  #modal-overlay { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.8); z-index: 99; }
</style>
</head>
<body>

<div id="modal-overlay" onclick="closeModal()"></div>
<div id="modal">
  <h3 id="modal-title" style="margin-top: 0; color: #fff;"></h3>
  <p id="modal-body" style="color: #bbb; line-height: 1.5;"></p>
  <button onclick="closeModal()" style="background:#444; border:none; color:white; padding:8px 20px; border-radius:5px; cursor:pointer;">닫기</button>
</div>

<div id="game-container">
  <h1>MURDER BETA</h1>

  <div id="menu">
    <div class="info-container">
      <div class="info-btn" onclick="openModal('Standard', '기본 모드입니다. 머더는 랜덤으로 부여되는 한 가지 특수 능력을 가집니다.')">STANDARD</div>
      <div class="info-btn" onclick="openModal('Zombie', '감염 모드입니다. 머더에게 죽은 생존자는 좀비가 되어 함께 공격합니다. 의사가 치료하면 다시 시민이 됩니다.')">ZOMBIE</div>
      <div class="info-btn" onclick="openModal('Chillsear', '암살 모드입니다. 의사의 치료가 불가능하며 머더의 공격이 매우 치명적입니다.')">CHILLSEAR</div>
    </div>

    <div class="switch-container">
      <span style="font-size: 14px; color: #888;">능력/타입 활성화</span>
      <label class="switch">
        <input type="checkbox" id="useSkills" checked>
        <span class="slider"></span>
      </label>
    </div>

    <label>인원 수 : <input type="number" id="playerCount" min="4" max="20" value="6"></label><br>
    <button onclick="startGame()" class="main-btn" style="margin-top:20px;">GAME START</button>
  </div>

  <div id="draw-area" style="display:none;">
    <div id="playerNum" style="font-size: 30px; margin-bottom: 25px; color: #666;"></div>
    <button onclick="draw()" class="main-btn" style="background: var(--accent-red);">역할 확인</button>
  </div>

  <div id="result">
    <div id="role" style="font-size: 50px; font-weight: 900;"></div>
    <div id="skill" style="font-size: 30px; font-weight: bold; margin: 15px 0;"></div>
    <div id="desc" style="font-size: 18px; color: #666; margin-bottom: 30px;"></div>
    <button onclick="nextPlayer()" style="background: #111; color: #fff; width: 100%; padding: 18px; border-radius: 12px; border: none; font-size: 16px; cursor:pointer;">확인 완료</button>
  </div>

  <div id="final-screen">
    <div style="color: #666; font-size: 20px; margin-bottom: 30px; letter-spacing: 2px;">이번 라운드 머더는...</div>
    <div id="finalType" class="final-murder-type"></div>
    <div id="finalDetail" style="font-size: 24px; color: #888; font-weight: bold; line-height: 1.4;"></div>
    <br><br>
    <button onclick="location.reload()" style="background: none; border: 1px solid #333; color: #333; font-size: 12px; padding: 10px 20px; border-radius: 5px; cursor:pointer;">새 게임 시작</button>
  </div>
</div>

<script>
const skills = {
  머더: [{ name: "방탄", desc: "공격을 1회 버팁니다. (2목숨)" }, { name: "가방", desc: "죽인 사람을 생존자로 위장시킵니다." }, { name: "총잡이", desc: "원거리 사격이 가능합니다." }],
  시민: [{ name: "스파이", desc: "사망 시 범인의 힌트를 남깁니다." }, { name: "패링", desc: "공격을 1회 무효화합니다." }],
  보안관: [{ name: "강인한", desc: "목숨이 2개가 됩니다." }],
  의사: [{ name: "자가치유", desc: "자신을 1회 치료합니다." }]
};

const murderTypes = [
  { name: "Standard", weight: 60, desc: "추가 능력이 포함된 기본 라운드입니다.", class: "type-standard" },
  { name: "Chillsear", weight: 30, desc: "의사가 치료할 수 없는 무자비한 라운드입니다.", class: "type-chillsear" },
  { name: "Zombie", weight: 10, desc: "죽은 자들이 좀비가 되는 감염 라운드입니다.", class: "type-zombie" }
];

let totalPlayers, current, roles, roundMurderType, useSkills;

function openModal(title, body) {
  document.getElementById('modal-title').textContent = title;
  document.getElementById('modal-body').textContent = body;
  document.getElementById('modal').style.display = 'block';
  document.getElementById('modal-overlay').style.display = 'block';
}

function closeModal() {
  document.getElementById('modal').style.display = 'none';
  document.getElementById('modal-overlay').style.display = 'none';
}

function startGame() {
  totalPlayers = parseInt(document.getElementById("playerCount").value);
  useSkills = document.getElementById("useSkills").checked;
  roles = ["머더", "보안관", "의사"];
  for (let i = 4; i <= totalPlayers; i++) roles.push("시민");
  roles.sort(() => Math.random() - 0.5);
  const rand = Math.random() * 100;
  let cum = 0;
  for (const t of murderTypes) { cum += t.weight; if (rand < cum) { roundMurderType = t; break; } }
  current = 0;
  document.getElementById("menu").style.display = "none";
  document.getElementById("draw-area").style.display = "block";
  document.getElementById("playerNum").textContent = `PLAYER 1`;
}

function draw() {
  const role = roles[current];
  let dSkill = "능력 없음", dDesc = "순수 모드 또는 무능력 상태입니다.";
  if (useSkills) {
    if (role === "머더" && roundMurderType.name === "Standard") {
      const s = skills.머더[Math.floor(Math.random() * skills.머더.length)];
      dSkill = s.name; dDesc = s.desc;
    } else if (role === "머더") {
      dSkill = "SPECIAL TYPE"; dDesc = "특수 타입입니다. 정체는 마지막에 공개됩니다.";
    } else {
      const list = skills[role] || skills.시민;
      const s = list[Math.floor(Math.random() * list.length)];
      dSkill = s.name; dDesc = s.desc;
    }
  }
  const rDiv = document.getElementById("role");
  rDiv.textContent = role;
  rDiv.style.color = role === "머더" ? "#cc0000" : role === "보안관" ? "#2b57ff" : role === "의사" ? "#28a745" : "#666";
  document.getElementById("skill").textContent = dSkill;
  document.getElementById("desc").textContent = dDesc;
  document.getElementById("draw-area").style.display = "none";
  document.getElementById("result").style.display = "block";
}

function nextPlayer() {
  current++;
  if (current >= totalPlayers) {
    if (useSkills) {
      document.getElementById("result").style.display = "none";
      document.getElementById("final-screen").style.display = "block";
      const tElt = document.getElementById("finalType");
      tElt.textContent = roundMurderType.name;
      tElt.className = "final-murder-type " + roundMurderType.class;
      document.getElementById("finalDetail").textContent = roundMurderType.desc;
      
      // 진동 효과 추가 (1회, 200ms)
      if ("vibrate" in navigator) {
          navigator.vibrate(200);
      }
    } else {
      alert("게임 시작! (순수 모드)");
      location.reload();
    }
    return;
  }
  document.getElementById("result").style.display = "none";
  document.getElementById("draw-area").style.display = "block";
  document.getElementById("playerNum").textContent = `PLAYER ${current + 1}`;
}
</script>
</body>
</html>
