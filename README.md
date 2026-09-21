<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>五字種子面試順序 - 下半場抽籤系統</title>
    <style>
        :root {
            --bg-body: #f8fafc;
            --surface-white: #ffffff;
            --primary-navy: #0f172a;
            --accent-blue: #2563eb;
            --accent-blue-hover: #1d4ed8;
            --status-green: #059669;
            --text-main: #0f172a;
            --text-muted: #64748b;
            --border-color: #e2e8f0;
            --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
            --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Microsoft JhengHei", "微軟正黑體", sans-serif; }

        body {
            background-color: var(--bg-body);
            color: var(--text-main);
            padding: 24px 16px;
            min-height: 100vh;
            line-height: 1.5;
        }

        /* --- 導覽列 --- */
        .top-nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: var(--surface-white);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 12px 24px;
            box-shadow: var(--shadow-sm);
            max-width: 900px;
            width: 100%;
            margin: 0 auto 28px auto;
            position: sticky;
            top: 12px;
            z-index: 100;
        }

        .nav-brand {
            font-weight: 700;
            font-size: 1.05rem;
            color: var(--primary-navy);
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .system-badge {
            background: #f1f5f9;
            color: var(--text-muted);
            font-size: 0.75rem;
            font-weight: 600;
            padding: 2px 8px;
            border-radius: 4px;
            border: 1px solid var(--border-color);
            letter-spacing: 0.5px;
        }

        .nav-actions {
            display: flex;
            gap: 8px;
        }

        .nav-btn {
            background: var(--surface-white);
            border: 1px solid var(--border-color);
            color: var(--text-main);
            padding: 6px 12px;
            border-radius: 6px;
            font-size: 0.875rem;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.15s ease;
            box-shadow: var(--shadow-sm);
        }

        .nav-btn:hover {
            background: #f8fafc;
            border-color: #cbd5e1;
        }

        /* --- 主容器 --- */
        .container {
            max-width: 900px;
            margin: 0 auto;
        }

        .header-panel {
            background: var(--surface-white);
            border: 1px solid var(--border-color);
            border-radius: 10px;
            padding: 24px;
            box-shadow: var(--shadow-sm);
            margin-bottom: 24px;
        }

        .hero-title {
            font-size: 1.4rem;
            font-weight: 800;
            color: var(--primary-navy);
            letter-spacing: -0.025em;
            margin-bottom: 8px;
        }

        .hero-subtitle {
            font-size: 0.875rem;
            color: var(--text-muted);
            display: flex;
            gap: 16px;
            flex-wrap: wrap;
        }

        /* --- 控制面板 --- */
        .status-card {
            background: #f8fafc;
            border: 1px dashed #cbd5e1;
            border-radius: 8px;
            padding: 12px 16px;
            text-align: center;
            font-size: 0.95rem;
            font-weight: 600;
            color: var(--primary-navy);
            margin-bottom: 20px;
        }

        .control-panel {
            display: flex;
            justify-content: center;
            gap: 12px;
            flex-wrap: wrap;
            margin-bottom: 32px;
        }

        .btn-primary {
            background: var(--accent-blue);
            color: #ffffff;
            border: none;
            padding: 10px 24px;
            border-radius: 6px;
            font-size: 0.95rem;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.15s ease, box-shadow 0.15s ease;
            box-shadow: var(--shadow-sm);
        }

        .btn-primary:hover:not(:disabled) {
            background: var(--accent-blue-hover);
            box-shadow: var(--shadow-md);
        }

        .btn-secondary {
            background: var(--surface-white);
            color: var(--text-main);
            border: 1px solid var(--border-color);
            padding: 10px 20px;
            border-radius: 6px;
            font-size: 0.95rem;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.15s ease;
            box-shadow: var(--shadow-sm);
        }

        .btn-secondary:hover:not(:disabled) {
            background: #f1f5f9;
            border-color: #cbd5e1;
        }

        .btn-primary:disabled, .btn-secondary:disabled {
            opacity: 0.5;
            cursor: not-allowed;
            box-shadow: none;
        }

        .section-header {
            font-size: 1.1rem;
            font-weight: 700;
            color: var(--primary-navy);
            margin-bottom: 16px;
        }

        /* --- 順序卡片結構 --- */
        .card-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 16px;
        }

        .group-card {
            background: var(--surface-white);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 18px;
            box-shadow: var(--shadow-sm);
        }

        .group-title {
            font-size: 0.95rem;
            font-weight: 700;
            color: var(--primary-navy);
            padding-bottom: 10px;
            margin-bottom: 12px;
            border-bottom: 1px solid var(--border-color);
        }

        .slot-list {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .slot-item {
            display: flex;
            align-items: center;
            background: #f8fafc;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            padding: 10px 14px;
            font-size: 0.9rem;
            transition: all 0.2s ease;
        }

        .slot-item.rolling {
            background: #eff6ff;
            border-color: #93c5fd;
        }

        .slot-item.revealed {
            background: #f0fdf4;
            border-color: #a7f3d0;
            animation: fadeIn 0.3s ease;
        }

        .slot-tag {
            background: var(--primary-navy);
            color: #ffffff;
            font-size: 0.75rem;
            font-weight: 700;
            padding: 2px 8px;
            border-radius: 4px;
            margin-right: 12px;
            flex-shrink: 0;
            min-width: 65px;
            text-align: center;
        }

        .slot-team {
            font-weight: 600;
            color: var(--text-main);
        }

        .slot-team.empty {
            color: var(--text-muted);
            font-weight: 400;
            font-size: 0.85rem;
        }

        @keyframes fadeIn {
            from { opacity: 0.4; transform: translateY(2px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @media print {
            .top-nav, button, .status-card, .control-panel { display: none !important; }
            body { background: #fff; padding: 0; }
            .container { max-width: 100%; }
            .header-panel { border: none; padding: 0 0 20px 0; }
            .group-card { border: 1px solid #000; box-shadow: none; }
        }
    </style>
</head>
<body>

<nav class="top-nav">
    <div class="nav-brand">
        五字種子面試順序
        <span class="system-badge">下半場 共 13 位</span>
    </div>
    <div class="nav-actions">
        <button class="nav-btn" onclick="copyScheduleText()">複製結果</button>
    </div>
</nav>

<div class="container">
    <div class="header-panel">
        <h1 class="hero-title">五字種子面試順序抽籤程序 (下半場)</h1>
        <div class="hero-subtitle">
            <span>系統狀態：<strong style="color: var(--status-green);">準備就緒</strong></span>
            <span>執行時間：<span id="timestamp">2026-09-22 14:00</span></span>
        </div>
    </div>

    <div class="status-card" id="statusText">
        請點擊「抽取下一位順序」按鈕開始執行抽籤程序
    </div>

    <div class="control-panel">
        <button class="btn-primary" id="btnNext" onclick="triggerDrawEffect()">抽取下一位順序 ( 第 15 順位 )</button>
        <button class="btn-secondary" id="btnAll" onclick="drawAllSlots()">快速完成全開</button>
        <button class="btn-secondary" onclick="initSystem()">重新重置順序</button>
        <button class="btn-secondary" onclick="window.print()">列印下半場順序表</button>
    </div>

    <div class="section-header">
        ■ 官方面試順序表 (第 15 號 ~ 第 27 號)
    </div>
    
    <div id="matchList" class="card-grid"></div>
</div>

<script>
// 扣除上半場14位後，剩餘的 13 位面試者名單
const REMAINING_TEAMS = [
    "郭品成", "賴柏翰", "張祐嘉", "陳彥蓁", "陳昱任",
    "呂育叡", "邱妍廷", "莊淯荃", "郭忠豪", "郭羿霆",
    "洪維廷", "李威霖", "吳宜峰"
];

const TOTAL_SLOTS = REMAINING_TEAMS.length;
const START_OFFSET = 15; // 從第 15 順位開始

let generatedTeams = [];
let currentStep = 0;
let isRolling = false;

window.onload = function() {
    updateTimestamp();
    initSystem();
};

function updateTimestamp() {
    const now = new Date();
    const formatted = now.getFullYear() + '-' + 
        String(now.getMonth() + 1).padStart(2, '0') + '-' + 
        String(now.getDate()).padStart(2, '0') + ' ' + 
        String(now.getHours()).padStart(2, '0') + ':' + 
        String(now.getMinutes()).padStart(2, '0');
    document.getElementById('timestamp').innerText = formatted;
}

function shuffle(arr) {
    for (let i = arr.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [arr[i], arr[j]] = [arr[j], arr[i]];
    }
    return arr;
}

function initSystem() {
    currentStep = 0;
    isRolling = false;
    generatedTeams = shuffle([...REMAINING_TEAMS]); // 完全隨機打亂
    renderBoard();
    updateUI();
}

function renderBoard() {
    let html = `
        <div class="group-card">
            <div class="group-title">【下半場】第 15 ~ 27 面試順位</div>
            <div class="slot-list">
    `;
    
    for (let i = 0; i < TOTAL_SLOTS; i++) {
        const slotNumber = START_OFFSET + i;
        html += `
            <div class="slot-item" id="slot-${i}">
                <span class="slot-tag">第 ${slotNumber} 順位</span>
                <span class="slot-team empty" id="team-${i}">等待抽籤...</span>
            </div>
        `;
    }
    
    html += `</div></div>`;
    document.getElementById('matchList').innerHTML = html;
}

function triggerDrawEffect() {
    if (currentStep >= TOTAL_SLOTS || isRolling) return;

    isRolling = true;
    const btnNext = document.getElementById('btnNext');
    const slotElem = document.getElementById(`slot-${currentStep}`);
    const teamElem = document.getElementById(`team-${currentStep}`);
    const currentSlotNum = START_OFFSET + currentStep;

    btnNext.disabled = true;
    btnNext.innerText = `抽籤中 [ 第 ${currentSlotNum} 順位 ]...`;

    slotElem.classList.add('rolling');
    teamElem.classList.remove('empty');

    let counter = 0;
    const rollInterval = setInterval(() => {
        const randomTeam = REMAINING_TEAMS[Math.floor(Math.random() * REMAINING_TEAMS.length)];
        teamElem.innerText = `${randomTeam}`;
        counter++;

        if (counter >= 6) { // 0.45 秒俐落揭曉
            clearInterval(rollInterval);
            finalizeSlot(currentStep);
            isRolling = false;
            currentStep++;
            updateUI();
        }
    }, 75);
}

function finalizeSlot(index) {
    const slotElem = document.getElementById(`slot-${index}`);
    const teamElem = document.getElementById(`team-${index}`);
    
    slotElem.classList.remove('rolling');
    slotElem.classList.add('revealed');
    teamElem.innerText = generatedTeams[index];
}

function drawAllSlots() {
    if (isRolling) return;
    while (currentStep < TOTAL_SLOTS) {
        finalizeSlot(currentStep);
        currentStep++;
    }
    updateUI();
}

function updateUI() {
    const statusText = document.getElementById('statusText');
    const btnNext = document.getElementById('btnNext');
    const btnAll = document.getElementById('btnAll');

    if (currentStep === 0) {
        statusText.innerText = "請點擊「抽取下一位順序」按鈕開始執行下半場抽籤";
        btnNext.disabled = false;
        btnNext.innerText = "抽取下一位順序 ( 第 15 順位 )";
        btnAll.disabled = false;
    } else if (currentStep < TOTAL_SLOTS) {
        const nextSlotNum = START_OFFSET + currentStep;
        statusText.innerHTML = `已完成下半場 <strong>${currentStep} / ${TOTAL_SLOTS}</strong> 位分配（下一位：<strong>第 ${nextSlotNum} 順位</strong>）`;
        btnNext.disabled = false;
        btnNext.innerText = `抽取下一位順序 ( 第 ${nextSlotNum} 順位 )`;
    } else {
        statusText.innerHTML = "🎉 所有 13 位下半場五字種子面試順位已全部分配完畢！";
        btnNext.disabled = true;
        btnNext.innerText = "抽籤完畢";
        btnAll.disabled = true;
    }
}

function copyScheduleText() {
    if (currentStep < TOTAL_SLOTS) {
        if (!confirm("目前抽籤尚未完全結束，確定要複製已產生的部分結果嗎？")) return;
    }
    
    let text = "📋【五字種子面試順序抽籤結果 - 下半場】\n";
    text += `執行時間：${document.getElementById('timestamp').innerText}\n\n`;
    
    for (let i = 0; i < TOTAL_SLOTS; i++) {
        const name = generatedTeams[i] || "未分配";
        const slotNumber = START_OFFSET + i;
        text += `第 ${slotNumber} 順序：${name}\n`;
    }
    
    navigator.clipboard.writeText(text).then(() => {
        alert("已成功將下半場面試順序結果複製至剪貼簿！");
    });
}
</script>

</body>
</html>
