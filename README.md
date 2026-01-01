<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TREINADOR - PROTOCOLO CAVEIRA</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Russo+One&family=Audiowide&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        /* TEMA: DARK, AGRESSIVO, SUJO, OLD SCHOOL */
        :root {
            --blood: #8B0000;
            --black-metal: #0A0A0A;
            --rusted: #B7410E;
            --concrete: #2A2A2A;
            --steel: #555555;
            --neon: #39FF14;
            --gold: #FFD700;
            --warning: #FF4500;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: url('https://images.unsplash.com/photo-1550684376-efcbd6e3f031?q=80&w=1000') no-repeat center center fixed;
            background-size: cover;
            background-blend-mode: multiply;
            background-color: rgba(0, 0, 0, 0.9);
            min-height: 100vh;
            color: #CCC;
            font-family: 'Orbitron', monospace;
            overflow-x: hidden;
            position: relative;
        }
        
        /* EFEITO DE GRANULAÇÃO/VELHO */
        body::before {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 20% 50%, rgba(139, 0, 0, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(183, 65, 14, 0.1) 0%, transparent 50%),
                repeating-linear-gradient(
                    0deg,
                    rgba(0, 0, 0, 0.2) 0px,
                    rgba(0, 0, 0, 0.2) 1px,
                    transparent 2px,
                    transparent 3px
                );
            pointer-events: none;
            z-index: 1;
        }
        
        /* CONTAINER PRINCIPAL */
        .container {
            max-width: 100%;
            margin: 0;
            background: rgba(10, 10, 10, 0.95);
            border: 3px solid var(--blood);
            position: relative;
            min-height: 100vh;
            box-shadow: 
                0 0 50px rgba(139, 0, 0, 0.7),
                inset 0 0 30px rgba(0, 0, 0, 0.9);
            z-index: 2;
        }
        
        /* EFEITO DE RACHADURAS */
        .container::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: 
                linear-gradient(90deg, transparent 95%, rgba(183, 65, 14, 0.1) 100%),
                linear-gradient(0deg, transparent 95%, rgba(183, 65, 14, 0.1) 100%);
            pointer-events: none;
            z-index: 1;
        }
        
        /* CABEÇALHO - ESTILO CAVEIRA */
        header {
            background: linear-gradient(135deg, 
                rgba(0, 0, 0, 0.9) 0%, 
                rgba(70, 0, 0, 0.8) 50%, 
                rgba(0, 0, 0, 0.9) 100%);
            padding: 15px;
            text-align: center;
            border-bottom: 3px solid var(--rusted);
            position: relative;
            overflow: hidden;
        }
        
        .header-title {
            font-family: 'Russo One', sans-serif;
            font-size: 2.8rem;
            font-weight: 900;
            text-transform: uppercase;
            letter-spacing: 6px;
            color: transparent;
            background: linear-gradient(45deg, var(--blood), var(--gold), var(--neon));
            background-clip: text;
            -webkit-background-clip: text;
            text-shadow: 
                3px 3px 0 #000,
                6px 6px 0 rgba(139, 0, 0, 0.5);
            margin-bottom: 5px;
            animation: titleGlitch 5s infinite;
        }
        
        @keyframes titleGlitch {
            0%, 100% { transform: translateX(0); }
            95% { transform: translateX(0); }
            96% { transform: translateX(-2px); }
            97% { transform: translateX(2px); }
            98% { transform: translateX(-1px); }
            99% { transform: translateX(1px); }
        }
        
        /* BADGE "DESISTIR JAMAIS!" */
        .warrior-badge {
            display: inline-block;
            background: linear-gradient(135deg, #000, var(--blood));
            color: #FFF;
            padding: 8px 20px;
            margin: 10px 0;
            border: 2px solid var(--gold);
            font-family: 'Audiowide', cursive;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 3px;
            position: relative;
            overflow: hidden;
        }
        
        .warrior-badge::before {
            content: "";
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(
                45deg,
                transparent 30%,
                rgba(255, 215, 0, 0.3) 50%,
                transparent 70%
            );
            animation: badgeShine 3s infinite;
        }
        
        @keyframes badgeShine {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }
        
        /* ANIMAÇÃO DE CAVEIRA */
        .skull-animation {
            font-size: 4rem;
            color: var(--neon);
            text-shadow: 
                0 0 10px var(--neon),
                0 0 20px var(--neon),
                0 0 30px var(--blood);
            animation: skullPulse 2s infinite;
            margin: 10px 0;
            filter: drop-shadow(2px 2px 0 #000);
        }
        
        @keyframes skullPulse {
            0%, 100% { 
                transform: scale(1) rotate(0deg);
                opacity: 1;
            }
            50% { 
                transform: scale(1.1) rotate(5deg);
                opacity: 0.8;
            }
        }
        
        /* NAVEGAÇÃO - ESTILO PAINEL DANIFICADO */
        .nav-tabs {
            display: flex;
            background: linear-gradient(to bottom, #111, #000);
            border-top: 2px solid var(--rusted);
            border-bottom: 2px solid var(--blood);
            position: sticky;
            top: 0;
            z-index: 1000;
            overflow-x: auto;
        }
        
        .nav-tab {
            flex: 1;
            padding: 15px 5px;
            color: #888;
            text-decoration: none;
            text-align: center;
            font-family: 'Audiowide', cursive;
            font-size: 0.8rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            border-right: 1px solid #333;
            position: relative;
            transition: all 0.3s;
            min-width: 70px;
        }
        
        .nav-tab:last-child {
            border-right: none;
        }
        
        .nav-tab::before {
            content: "▸";
            position: absolute;
            left: 5px;
            top: 50%;
            transform: translateY(-50%);
            color: transparent;
            transition: color 0.3s;
        }
        
        .nav-tab:hover {
            background: linear-gradient(to bottom, rgba(139, 0, 0, 0.3), transparent);
            color: var(--neon);
        }
        
        .nav-tab:hover::before {
            color: var(--neon);
        }
        
        .nav-tab.active {
            background: linear-gradient(to bottom, var(--blood), #000);
            color: #FFF;
            border-bottom: 3px solid var(--neon);
        }
        
        .nav-tab.active::before {
            color: var(--neon);
        }
        
        /* CONTEÚDO DAS ABAS */
        .tab-content {
            display: none;
            padding: 20px 15px;
            animation: fadeIn 0.5s ease;
            position: relative;
            z-index: 2;
        }
        
        .tab-content.active {
            display: block;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* SEÇÕES - ESTILO PLACA METÁLICA */
        .section {
            background: linear-gradient(135deg, 
                rgba(42, 42, 42, 0.9) 0%, 
                rgba(28, 28, 28, 0.9) 100%);
            border: 2px solid #444;
            border-left: 5px solid var(--blood);
            padding: 15px;
            margin-bottom: 20px;
            position: relative;
            box-shadow: 
                0 5px 15px rgba(0, 0, 0, 0.5),
                inset 0 0 10px rgba(0, 0, 0, 0.8);
        }
        
        .section::before {
            content: "■";
            position: absolute;
            top: 5px;
            left: 5px;
            color: var(--neon);
            font-size: 12px;
            text-shadow: 0 0 5px var(--neon);
        }
        
        .section-title {
            color: var(--neon);
            font-family: 'Russo One', sans-serif;
            font-size: 1.4rem;
            margin-bottom: 20px;
            text-transform: uppercase;
            letter-spacing: 3px;
            border-bottom: 2px solid #555;
            padding-bottom: 8px;
            text-shadow: 1px 1px 0 #000;
        }
        
        /* CARDS DE INFO */
        .info-card {
            background: rgba(0, 0, 0, 0.8);
            border: 1px solid #555;
            border-left: 4px solid var(--rusted);
            padding: 15px;
            margin: 15px 0;
            position: relative;
            transition: transform 0.3s;
        }
        
        .info-card:hover {
            transform: translateY(-3px);
            border-left-color: var(--neon);
        }
        
        .info-card.critical {
            border-left-color: var(--blood);
            background: linear-gradient(135deg, 
                rgba(70, 0, 0, 0.8) 0%, 
                rgba(40, 0, 0, 0.8) 100%);
            animation: criticalPulse 2s infinite;
        }
        
        @keyframes criticalPulse {
            0%, 100% { box-shadow: 0 0 0 0 rgba(255, 69, 0, 0.4); }
            50% { box-shadow: 0 0 0 5px rgba(255, 69, 0, 0); }
        }
        
        /* BOTÕES - ESTILO BOTÃO DE AÇÃO MECÂNICO */
        .btn {
            background: linear-gradient(to bottom, #333, #111);
            color: #FFF;
            border: 2px solid #555;
            padding: 12px 20px;
            font-family: 'Audiowide', cursive;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 2px;
            cursor: pointer;
            transition: all 0.3s;
            width: 100%;
            margin: 8px 0;
            position: relative;
            overflow: hidden;
        }
        
        .btn::before {
            content: "";
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, 
                transparent, 
                rgba(57, 255, 20, 0.2), 
                transparent);
            transition: 0.5s;
        }
        
        .btn:hover::before {
            left: 100%;
        }
        
        .btn:hover {
            border-color: var(--neon);
            color: var(--neon);
            box-shadow: 
                0 0 15px rgba(57, 255, 20, 0.3),
                inset 0 0 10px rgba(57, 255, 20, 0.1);
        }
        
        .btn-primary {
            background: linear-gradient(to bottom, var(--blood), #600);
            border-color: var(--rusted);
        }
        
        /* CHECKLIST */
        .checklist-item {
            background: rgba(30, 30, 30, 0.8);
            border: 1px solid #444;
            margin: 10px 0;
            padding: 12px;
            display: flex;
            align-items: center;
            transition: all 0.3s;
        }
        
        .checklist-item:hover {
            border-color: #666;
            background: rgba(40, 40, 40, 0.9);
        }
        
        .checklist-item input[type="checkbox"] {
            width: 22px;
            height: 22px;
            margin-right: 15px;
            accent-color: var(--neon);
            cursor: pointer;
        }
        
        /* TREINO */
        .muscle-group {
            background: rgba(0, 0, 0, 0.7);
            border: 1px solid #444;
            margin: 15px 0;
            padding: 15px;
            border-left: 4px solid var(--rusted);
        }
        
        .muscle-title {
            color: var(--neon);
            font-family: 'Russo One', sans-serif;
            font-size: 1.2rem;
            margin-bottom: 15px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        
        .rep-input {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin: 15px 0;
        }
        
        .rep-box {
            background: #000;
            border: 2px solid #444;
            color: #FFF;
            width: 60px;
            height: 45px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: 'Orbitron', monospace;
            font-size: 1.3rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.2s;
        }
        
        .rep-box:hover {
            border-color: var(--neon);
            background: rgba(57, 255, 20, 0.1);
            transform: scale(1.05);
        }
        
        .rep-box.active {
            background: var(--blood);
            border-color: var(--neon);
            box-shadow: 0 0 10px var(--neon);
        }
        
        /* CICLO HORMONAL */
        .cycle-card {
            background: rgba(30, 0, 0, 0.8);
            border: 1px solid var(--blood);
            margin: 15px 0;
            padding: 15px;
            position: relative;
        }
        
        .cycle-title {
            color: #FF6347;
            font-family: 'Audiowide', cursive;
            font-size: 1.1rem;
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        
        /* NOTIFICAÇÕES */
        .notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: linear-gradient(135deg, #000, var(--blood));
            border: 2px solid var(--rusted);
            padding: 15px;
            max-width: 300px;
            z-index: 10000;
            display: none;
            box-shadow: 0 0 30px rgba(255, 69, 0, 0.7);
        }
        
        .notification.show {
            display: block;
            animation: slideIn 0.5s;
        }
        
        @keyframes slideIn {
            from { transform: translateX(100%); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }
        
        /* AVATAR DE PROGRESSO */
        .avatar-container {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }
        
        .avatar-stat {
            background: rgba(0, 0, 0, 0.8);
            border: 1px solid #444;
            padding: 15px;
        }
        
        .stat-name {
            color: #888;
            font-family: 'Audiowide', cursive;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        
        .stat-value {
            color: var(--neon);
            font-family: 'Orbitron', monospace;
            font-size: 1.5rem;
            font-weight: bold;
            margin: 10px 0;
        }
        
        /* PROGRESS BARS */
        .progress-container {
            background: #000;
            border: 1px solid #444;
            height: 20px;
            margin: 10px 0;
            position: relative;
            overflow: hidden;
        }
        
        .progress-bar {
            height: 100%;
            background: linear-gradient(90deg, var(--blood), var(--rusted));
            transition: width 0.5s;
            position: relative;
        }
        
        .progress-bar::after {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(90deg, 
                transparent, 
                rgba(255, 255, 255, 0.1), 
                transparent);
            animation: scan 2s infinite linear;
        }
        
        @keyframes scan {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }
        
        /* INPUTS */
        input, select, textarea {
            background: rgba(0, 0, 0, 0.9);
            border: 1px solid #444;
            color: #CCC;
            padding: 12px;
            width: 100%;
            margin: 8px 0;
            font-family: 'Orbitron', monospace;
            transition: all 0.3s;
        }
        
        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: var(--neon);
            box-shadow: 0 0 15px rgba(57, 255, 20, 0.3);
        }
        
        /* RODAPÉ */
        footer {
            background: #000;
            border-top: 2px solid var(--blood);
            padding: 15px;
            text-align: center;
            font-family: 'Audiowide', cursive;
            font-size: 0.8rem;
            color: #666;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        
        /* RESPONSIVIDADE */
        @media (max-width: 768px) {
            .header-title {
                font-size: 2rem;
                letter-spacing: 3px;
            }
            
            .nav-tab {
                font-size: 0.7rem;
                padding: 12px 3px;
                letter-spacing: 1px;
            }
            
            .section-title {
                font-size: 1.2rem;
            }
            
            .skull-animation {
                font-size: 3rem;
            }
        }
        
        /* EFEITO DE DIGITAÇÃO PARA TEXTOS */
        .typewriter {
            overflow: hidden;
            border-right: 3px solid var(--neon);
            white-space: nowrap;
            margin: 0 auto;
            letter-spacing: 2px;
            animation: 
                typing 3.5s steps(40, end),
                blink-caret 0.75s step-end infinite;
        }
        
        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }
        
        @keyframes blink-caret {
            from, to { border-color: transparent }
            50% { border-color: var(--neon) }
        }
        
        /* MODAIS */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.95);
            z-index: 2000;
            align-items: center;
            justify-content: center;
        }
        
        .modal-content {
            background: #000;
            border: 3px solid var(--blood);
            padding: 25px;
            max-width: 500px;
            width: 90%;
            max-height: 80vh;
            overflow-y: auto;
            box-shadow: 0 0 50px rgba(139, 0, 0, 0.8);
        }
        
        .close-modal {
            color: var(--neon);
            float: right;
            font-size: 28px;
            font-weight: bold;
            cursor: pointer;
            transition: color 0.3s;
        }
        
        .close-modal:hover {
            color: var(--blood);
        }
        
        /* EFEITO DE VHS/DEGRADAÇÃO */
        .vhs-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 3;
            opacity: 0.05;
            background: 
                repeating-linear-gradient(
                    0deg,
                    rgba(0, 0, 0, 0.15) 0px,
                    rgba(0, 0, 0, 0.15) 1px,
                    transparent 1px,
                    transparent 2px
                );
            mix-blend-mode: overlay;
        }
    </style>
</head>
<body>
    <!-- OVERLAY VHS -->
    <div class="vhs-overlay"></div>
    
    <div class="container">
        <!-- CABEÇALHO -->
        <header>
            <div class="header-title">TREINADOR</div>
            <div style="color: #888; font-family: 'Audiowide', cursive; font-size: 0.9rem; letter-spacing: 3px;">
                PROTOCOLO MENS CLASSIC 2026
            </div>
            
            <div class="warrior-badge">DESISTIR JAMAIS!</div>
            
            <!-- ANIMAÇÃO DE CAVEIRA -->
            <div class="skull-animation" style="text-align: center;">
                💀
            </div>
            
            <!-- MOTIVAÇÃO DO DIA -->
            <div id="dailyQuote" style="margin-top: 10px; color: var(--gold); font-family: 'Audiowide', cursive; font-size: 0.9rem; text-align: center;">
                <!-- Será preenchido por JavaScript -->
            </div>
        </header>
        
        <!-- NAVEGAÇÃO -->
        <nav class="nav-tabs">
            <a href="#" class="nav-tab active" data-tab="hoje">HOJE</a>
            <a href="#" class="nav-tab" data-tab="treino">TREINO</a>
            <a href="#" class="nav-tab" data-tab="saude">SAÚDE</a>
            <a href="#" class="nav-tab" data-tab="evolucao">EVOLUIR</a>
            <a href="#" class="nav-tab" data-tab="config">SISTEMA</a>
        </nav>
        
        <!-- ABA: HOJE -->
        <div class="tab-content active" id="hoje">
            <div class="section">
                <div class="section-title">COMANDO DO DIA</div>
                
                <div id="dayMission" class="typewriter" style="color: var(--neon); font-size: 1.1rem; margin-bottom: 20px;">
                    <!-- Será preenchido por JS -->
                </div>
                
                <div class="info-card">
                    <strong style="color: var(--gold);">💪 TREINO HOJE:</strong>
                    <div id="todayWorkout" style="margin-top: 10px; color: #CCC;"></div>
                </div>
                
                <div class="info-card">
                    <strong style="color: var(--gold);">💊 CICLO HOJE:</strong>
                    <div id="todayCycle" style="margin-top: 10px; color: #CCC;"></div>
                </div>
                
                <div class="info-card">
                    <strong style="color: var(--gold);">☕ CHÁS HOJE:</strong>
                    <div id="todayTeas" style="margin-top: 10px; color: #CCC;"></div>
                </div>
            </div>
            
            <div class="section">
                <div class="section-title">CHECKLIST DE GUERREIRO</div>
                
                <div class="checklist-item">
                    <input type="checkbox" id="checkWeight" onchange="saveChecklist()">
                    <label for="checkWeight" style="flex: 1;">PESO MEDIDO (JEJUM)</label>
                    <input type="number" id="weightInput" placeholder="kg" style="width: 80px; padding: 5px; margin-left: 10px;" onchange="updateWeight(this.value)">
                </div>
                
                <div class="checklist-item">
                    <input type="checkbox" id="checkBP" onchange="saveChecklist()">
                    <label for="checkBP">PRESSÃO ARTERIAL</label>
                    <button class="btn" onclick="measureBP()" style="padding: 5px 10px; margin-left: 10px; width: auto;">MEDIR</button>
                </div>
                
                <div class="checklist-item">
                    <input type="checkbox" id="checkCycle" onchange="saveChecklist()">
                    <label for="checkCycle">APLICAÇÕES HORMONAIS</label>
                </div>
                
                <div class="checklist-item">
                    <input type="checkbox" id="checkTeas" onchange="saveChecklist()">
                    <label for="checkTeas">CHÁS DO DIA <span id="teaCount">(0/5)</span></label>
                </div>
                
                <div class="checklist-item">
                    <input type="checkbox" id="checkWater" onchange="saveChecklist()">
                    <label for="checkWater">ÁGUA: <span id="waterAmount">0</span>/5000ml</label>
                    <div style="display: flex; gap: 5px; margin-left: 10px;">
                        <button class="btn" onclick="addWater(250)" style="padding: 3px 8px; width: auto;">+250</button>
                        <button class="btn" onclick="addWater(500)" style="padding: 3px 8px; width: auto;">+500</button>
                    </div>
                </div>
                
                <div class="progress-container" style="margin: 15px 0;">
                    <div class="progress-bar" id="waterBar" style="width: 0%"></div>
                </div>
                
                <div class="checklist-item">
                    <input type="checkbox" id="checkSuplements" onchange="saveChecklist()">
                    <label for="checkSuplements">SUPLEMENTAÇÃO COMPLETA</label>
                </div>
            </div>
            
            <div class="section">
                <div class="section-title">COMANDOS RÁPIDOS</div>
                <button class="btn btn-primary" onclick="showModal('adjustModal')">REGISTRAR FALHA/VITÓRIA</button>
                <button class="btn" onclick="showModal('warDiaryModal')">DIÁRIO DE GUERRA</button>
                <button class="btn" onclick="completeDay()">DIA CONCLUÍDO</button>
            </div>
        </div>
        
        <!-- ABA: TREINO -->
        <div class="tab-content" id="treino">
            <div class="section">
                <div class="section-title">CAMPO DE BATALHA</div>
                <div id="workoutContainer">
                    <!-- Preenchido por JavaScript -->
                </div>
                
                <div style="margin-top: 25px; display: flex; gap: 10px;">
                    <button class="btn btn-primary" onclick="saveWorkout()">SALVAR BATALHA</button>
                    <button class="btn" onclick="clearWorkout()">LIMPAR CAMPOS</button>
                    <button class="btn" onclick="showModal('prModal')">REGISTRAR RECORDE</button>
                </div>
            </div>
            
            <div class="section">
                <div class="section-title">HISTÓRICO DE BATALHAS</div>
                <div id="workoutHistory">
                    <!-- Preenchido por JavaScript -->
                </div>
            </div>
        </div>
        
        <!-- ABA: SAÚDE -->
        <div class="tab-content" id="saude">
            <div class="section">
                <div class="section-title">ARSENAL HORMONAL</div>
                
                <div class="cycle-card">
                    <div class="cycle-title">ENANTATO</div>
                    <div style="color: #CCC; margin-bottom: 10px;" id="enantatoDetails">250mg/ml | 400mg/semana</div>
                    <div>Próxima: <span id="nextEnantato" style="color: var(--neon);">--</span></div>
                    <button class="btn" onclick="markInjection('enantato')" style="margin-top: 15px;">APLIQUEI AGORA</button>
                </div>
                
                <div class="cycle-card">
                    <div class="cycle-title">DECA NPP</div>
                    <div style="color: #CCC; margin-bottom: 10px;" id="decaDetails">100mg/ml | 300mg/semana</div>
                    <div>Próxima: <span id="nextDeca" style="color: var(--neon);">--</span></div>
                    <button class="btn" onclick="markInjection('deca')" style="margin-top: 15px;">APLIQUEI AGORA</button>
                </div>
                
                <div class="cycle-card">
                    <div class="cycle-title">DIANABOL</div>
                    <div style="color: #CCC; margin-bottom: 10px;" id="dianabolDetails">10mg/comprimido | 20mg/dia</div>
                    <div>Status: <span id="dianabolStatus" style="color: var(--neon);">DIA 1/28</span></div>
                    <button class="btn" onclick="markDianabol()" style="margin-top: 15px;">TOMEI AGORA</button>
                </div>
                
                <div class="cycle-card">
                    <div class="cycle-title">STANOZOLOL (OPCIONAL)</div>
                    <div style="color: #CCC; margin-bottom: 10px;">10mg/dia (pré-treino) - USAR APENAS SE NECESSÁRIO</div>
                    <div>Status: <span id="stanoStatus" style="color: #888;">NÃO USAR HOJE</span></div>
                    <button class="btn" onclick="toggleStano()" style="margin-top: 15px; background: #333;">ATIVAR/DESATIVAR</button>
                </div>
                
                <button class="btn" onclick="showModal('concentrationModal')" style="margin-top: 15px; background: linear-gradient(to bottom, #333, #111);">
                    ⚗️ CONFIGURAR CONCENTRAÇÕES
                </button>
                
                <div class="info-card critical">
                    <strong style="color: var(--neon);">⚠️ PROTEÇÃO HEPÁTICA (OBRIGATÓRIA)</strong>
                    <div style="margin-top: 10px;">
                        <div>• TUDCA: 750mg/dia 18h</div>
                        <div>• Cardo Mariano: 500mg/dia</div>
                        <div>• Saw Palmetto: 320mg/dia (anti-DHT)</div>
                        <div>• N-Acetil Cisteína: 600mg/dia</div>
                    </div>
                </div>
            </div>
            
            <div class="section">
                <div class="section-title">CHÁS DE PROTEÇÃO</div>
                
                <div class="info-card">
                    <strong style="color: var(--gold);">🛡️ ANTI-DHT (CABELO):</strong>
                    <div>• Saw Palmetto - 2x/dia (manhã/noite)</div>
                    <div>• Chá Verde - 3x/dia</div>
                    <div>• Óleo de Abóbora - 1 colher/dia</div>
                </div>
                
                <div class="info-card">
                    <strong style="color: var(--gold);">🛡️ HEPÁTICO (FÍGADO):</strong>
                    <div>• Cardo Mariano - 2x/dia</div>
                    <div>• Dente-de-Leão - 1x/dia</div>
                    <div>• Boldo - 1x/dia (se sentir desconforto)</div>
                </div>
                
                <div class="info-card">
                    <strong style="color: var(--gold);">🛡️ CARDÍACO (PRESSÃO):</strong>
                    <div>• Hibisco - 2x/dia</div>
                    <div>• Espinheiro Branco - 1x/dia</div>
                    <div>• Alho - 1 dente cru/dia</div>
                </div>
                
                <button class="btn" onclick="markTea()" style="margin-top: 15px;">MARCAR CHÁ TOMADO</button>
            </div>
            
            <div class="section">
                <div class="section-title">BIOMARCADORES</div>
                
                <div style="display: grid; grid-template-columns: repeat(2, 1fr); gap: 15px;">
                    <div class="info-card">
                        <div style="color: #888; font-size: 0.9rem;">PRESSÃO</div>
                        <div id="bpValue" style="color: var(--neon); font-size: 1.5rem; font-weight: bold;">--/--</div>
                    </div>
                    
                    <div class="info-card">
                        <div style="color: #888; font-size: 0.9rem;">PULSO</div>
                        <div id="pulseValue" style="color: var(--neon); font-size: 1.5rem; font-weight: bold;">--</div>
                    </div>
                    
                    <div class="info-card">
                        <div style="color: #888; font-size: 0.9rem;">TEMPERATURA</div>
                        <div id="tempValue" style="color: var(--neon); font-size: 1.5rem; font-weight: bold;">--°C</div>
                    </div>
                    
                    <div class="info-card">
                        <div style="color: #888; font-size: 0.9rem;">OXIGENAÇÃO</div>
                        <div id="oxValue" style="color: var(--neon); font-size: 1.5rem; font-weight: bold;">--%</div>
                    </div>
                </div>
                
                <button class="btn" onclick="showModal('healthModal')" style="margin-top: 20px;">REGISTRAR DADOS MÉDICOS</button>
            </div>
        </div>
        
        <!-- ABA: EVOLUIR -->
        <div class="tab-content" id="evolucao">
            <div class="section">
                <div class="section-title">ESTÁTUA DO PROGRESSO</div>
                
                <div class="avatar-container">
                    <div class="avatar-stat">
                        <div class="stat-name">PESO</div>
                        <div class="stat-value" id="statWeight">95/105kg</div>
                        <div class="progress-container">
                            <div class="progress-bar" id="weightBar" style="width: 30%"></div>
                        </div>
                        <div style="color: #888; font-size: 0.8rem; margin-top: 5px;">+0.5kg esta semana</div>
                    </div>
                    
                    <div class="avatar-stat">
                        <div class="stat-name">BRAÇO</div>
                        <div class="stat-value" id="statArm">41/47.7cm</div>
                        <div class="progress-container">
                            <div class="progress-bar" id="armBar" style="width: 25%"></div>
                        </div>
                        <div style="color: #888; font-size: 0.8rem; margin-top: 5px;">Meta: +0.5cm/mês</div>
                    </div>
                    
                    <div class="avatar-stat">
                        <div class="stat-name">BARRIGA</div>
                        <div class="stat-value" id="statBelly" style="color: var(--warning);">99cm ⚠️</div>
                        <div class="progress-container">
                            <div class="progress-bar" id="bellyBar" style="width: 15%; background: var(--warning);"></div>
                        </div>
                        <div style="color: #888; font-size: 0.8rem; margin-top: 5px;">Foco: -1cm/mês</div>
                    </div>
                    
                    <div class="avatar-stat">
                        <div class="stat-name">FORÇA TOTAL</div>
                        <div class="stat-value" id="statStrength">+8.5%</div>
                        <div class="progress-container">
                            <div class="progress-bar" id="strengthBar" style="width: 65%"></div>
                        </div>
                        <div style="color: #888; font-size: 0.8rem; margin-top: 5px;">Baseado em PRs</div>
                    </div>
                </div>
            </div>
            
            <div class="section">
                <div class="section-title">GRÁFICO DE GUERRA</div>
                <canvas id="progressChart" width="400" height="200"></canvas>
            </div>
            
            <div class="section">
                <div class="section-title">TROFÉUS DE GUERRA (PRs)</div>
                <div id="prList">
                    <!-- Preenchido por JavaScript -->
                </div>
                <button class="btn" onclick="showModal('prModal')" style="margin-top: 15px;">ADICIONAR TROFÉU</button>
            </div>
        </div>
        
        <!-- ABA: SISTEMA -->
        <div class="tab-content" id="config">
            <div class="section">
                <div class="section-title">PERFIL DE GUERREIRO</div>
                
                <div style="margin-bottom: 15px;">
                    <label style="color: #888; display: block; margin-bottom: 5px;">Peso Atual (kg):</label>
                    <input type="number" id="configWeight" value="95" step="0.1">
                </div>
                
                <div style="margin-bottom: 15px;">
                    <label style="color: #888; display: block; margin-bottom: 5px;">Braço (cm):</label>
                    <input type="number" id="configArm" value="41" step="0.1">
                </div>
                
                <div style="margin-bottom: 15px;">
                    <label style="color: #888; display: block; margin-bottom: 5px;">Barriga (cm):</label>
                    <input type="number" id="configBelly" value="99" step="0.1">
                </div>
                
                <button class="btn btn-primary" onclick="updateProfile()">ATUALIZAR PERFIL</button>
            </div>
            
            <div class="section">
                <div class="section-title">ALERTAS DE BATALHA</div>
                
                <div class="checklist-item">
                    <input type="checkbox" id="notifHormones" checked>
                    <label for="notifHormones">Aplicações hormonais</label>
                </div>
                
                <div class="checklist-item">
                    <input type="checkbox" id="notifTeas" checked>
                    <label for="notifTeas">Chás de proteção</label>
                </div>
                
                <div class="checklist-item">
                    <input type="checkbox" id="notifBP" checked>
                    <label for="notifBP">Pressão arterial (2ª feira)</label>
                </div>
                
                <div class="checklist-item">
                    <input type="checkbox" id="notifPR">
                    <label for="notifPR">Lembretes de recordes</label>
                </div>
                
                <div class="checklist-item">
                    <input type="checkbox" id="notifWater">
                    <label for="notifWater">Água (a cada 2h)</label>
                </div>
            </div>
            
            <div class="section">
                <div class="section-title">SISTEMA DE BACKUP</div>
                <button class="btn" onclick="exportData()">EXPORTAR ARQUIVO DE GUERRA</button>
                <button class="btn" onclick="importData()">IMPORTAR ARQUIVO DE GUERRA</button>
                <button class="btn" onclick="clearData()" style="background: linear-gradient(to bottom, var(--blood), #400);">ZERAR SISTEMA</button>
            </div>
            
            <div class="info-card">
                <strong style="color: var(--neon);">💾 STATUS DO SISTEMA</strong>
                <div style="margin-top: 10px;">
                    <div>Último backup: <span id="lastBackup" style="color: var(--gold);">Nunca</span></div>
                    <div>Armazenamento: <span id="dataSize" style="color: var(--gold);">0 KB</span></div>
                    <div>Versão: 2.0.2 CAVEIRA</div>
                    <div>Build: 2025.10</div>
                </div>
            </div>
        </div>
        
        <!-- RODAPÉ -->
        <footer>
            <div style="margin-bottom: 5px;">
                <span style="color: var(--neon);">⚙️</span> SISTEMA TREINADOR | 
                <span style="color: var(--neon);">📅</span> <span id="currentDate"></span> | 
                <span style="color: var(--neon);">⏰</span> <span id="currentTime"></span>
            </div>
            <div style="font-size: 0.7rem; color: #444; font-family: 'Orbitron', monospace;">
                "O SUOR DE HOJE É O SANGUE DO INIMIGO AMANHÃ"
            </div>
        </footer>
    </div>
    
    <!-- MODAL PARA AJUSTES -->
    <div class="modal" id="adjustModal">
        <div class="modal-content">
            <span class="close-modal" onclick="hideModal('adjustModal')">&times;</span>
            <div class="section-title">REGISTRAR FALHA/VITÓRIA</div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Tipo:</label>
                <select id="adjustType">
                    <option value="missedMeal">Refeição perdida</option>
                    <option value="extraFood">Comida extra</option>
                    <option value="missedWater">Água abaixo da meta</option>
                    <option value="missedInjection">Injeção atrasada</option>
                    <option value="extraCardio">Cardio extra</option>
                    <option value="achievement">Vitória/conquista</option>
                    <option value="other">Outro</option>
                </select>
            </div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Detalhes:</label>
                <textarea id="adjustDetails" rows="4" placeholder="Descreva o que aconteceu..."></textarea>
            </div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Compensação:</label>
                <select id="adjustCompensation">
                    <option value="none">Nenhuma</option>
                    <option value="extraReps">+10 reps no próximo treino</option>
                    <option value="lessCarbs">-20g de carboidrato</option>
                    <option value="extraCardio">+10min cardio</option>
                    <option value="extraWater">+500ml água extra</option>
                </select>
            </div>
            
            <button class="btn btn-primary" onclick="saveAdjustment()">REGISTRAR NO DIÁRIO</button>
        </div>
    </div>
    
    <!-- MODAL PARA DIÁRIO DE GUERRA -->
    <div class="modal" id="warDiaryModal">
        <div class="modal-content">
            <span class="close-modal" onclick="hideModal('warDiaryModal')">&times;</span>
            <div class="section-title">DIÁRIO DE GUERRA</div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Data:</label>
                <input type="date" id="warDiaryDate" value="">
            </div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Relatório do Dia:</label>
                <textarea id="warDiaryContent" rows="10" placeholder="Como foi o dia? O que aprendeu? O que precisa melhorar? Registre sua batalha..."></textarea>
            </div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Estado Mental (1-10):</label>
                <input type="range" id="mentalState" min="1" max="10" value="5">
                <span id="mentalStateValue">5</span>
            </div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Energia (1-10):</label>
                <input type="range" id="energyLevel" min="1" max="10" value="5">
                <span id="energyLevelValue">5</span>
            </div>
            
            <button class="btn btn-primary" onclick="saveWarDiary()">SALVAR DIÁRIO</button>
        </div>
    </div>
    
    <!-- MODAL PARA REGISTRAR PR -->
    <div class="modal" id="prModal">
        <div class="modal-content">
            <span class="close-modal" onclick="hideModal('prModal')">&times;</span>
            <div class="section-title">REGISTRAR TROFÉU DE GUERRA</div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Exercício:</label>
                <input type="text" id="prExercise" placeholder="Ex: Supino Reto">
            </div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Peso (kg):</label>
                <input type="number" id="prWeight" step="0.5">
            </div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Repetições:</label>
                <input type="number" id="prReps" min="1" max="50">
            </div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Data:</label>
                <input type="date" id="prDate" value="">
            </div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Observações:</label>
                <textarea id="prNotes" rows="3" placeholder="Alguma observação especial?"></textarea>
            </div>
            
            <button class="btn btn-primary" onclick="savePR()">REGISTRAR TROFÉU</button>
        </div>
    </div>
    
    <!-- MODAL PARA SAÚDE -->
    <div class="modal" id="healthModal">
        <div class="modal-content">
            <span class="close-modal" onclick="hideModal('healthModal')">&times;</span>
            <div class="section-title">REGISTRO MÉDICO</div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Pressão Sistólica:</label>
                <input type="number" id="healthSystolic" placeholder="Ex: 120">
            </div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Pressão Diastólica:</label>
                <input type="number" id="healthDiastolic" placeholder="Ex: 80">
            </div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Pulso (bpm):</label>
                <input type="number" id="healthPulse" placeholder="Ex: 70">
            </div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Temperatura (°C):</label>
                <input type="number" id="healthTemp" step="0.1" placeholder="Ex: 36.5">
            </div>
            
            <div style="margin: 15px 0;">
                <label style="color: #888; display: block; margin-bottom: 5px;">Oxigenação (%):</label>
                <input type="number" id="healthOx" min="80" max="100" placeholder="Ex: 98">
            </div>
            
            <button class="btn btn-primary" onclick="saveHealthData()">SALVAR DADOS</button>
        </div>
    </div>
    
    <!-- MODAL PARA CONFIGURAR CONCENTRAÇÕES -->
    <div class="modal" id="concentrationModal">
        <div class="modal-content">
            <span class="close-modal" onclick="hideModal('concentrationModal')">&times;</span>
            <div class="section-title">CONFIGURAR CONCENTRAÇÕES</div>
            
            <div class="info-card">
                <strong style="color: var(--gold);">ENANTATO</strong>
                <div style="margin-top: 10px;">
                    <label style="color: #888; display: block; margin-bottom: 5px;">Concentração (mg/ml):</label>
                    <input type="number" id="configEnantatoConc" value="250" step="1">
                </div>
                <div style="margin-top: 10px;">
                    <label style="color: #888; display: block; margin-bottom: 5px;">Dose Semanal (mg):</label>
                    <input type="number" id="configEnantatoWeekly" value="400" step="1">
                </div>
                <div id="enantatoCalc" style="color: var(--neon); margin-top: 10px; font-size: 0.9rem;">
                    <!-- Calculado automaticamente -->
                </div>
            </div>
            
            <div class="info-card">
                <strong style="color: var(--gold);">NANDROLONA (DECA)</strong>
                <div style="margin-top: 10px;">
                    <label style="color: #888; display: block; margin-bottom: 5px;">Concentração (mg/ml):</label>
                    <input type="number" id="configDecaConc" value="100" step="1">
                </div>
                <div style="margin-top: 10px;">
                    <label style="color: #888; display: block; margin-bottom: 5px;">Dose Semanal (mg):</label>
                    <input type="number" id="configDecaWeekly" value="300" step="1">
                </div>
                <div id="decaCalc" style="color: var(--neon); margin-top: 10px; font-size: 0.9rem;">
                    <!-- Calculado automaticamente -->
                </div>
            </div>
            
            <div class="info-card">
                <strong style="color: var(--gold);">DIANABOL</strong>
                <div style="margin-top: 10px;">
                    <label style="color: #888; display: block; margin-bottom: 5px;">Mg por comprimido:</label>
                    <input type="number" id="configDianabolMg" value="10" step="1">
                </div>
                <div style="margin-top: 10px;">
                    <label style="color: #888; display: block; margin-bottom: 5px;">Dose Diária (mg):</label>
                    <input type="number" id="configDianabolDaily" value="20" step="1">
                </div>
                <div id="dianabolCalc" style="color: var(--neon); margin-top: 10px; font-size: 0.9rem;">
                    <!-- Calculado automaticamente -->
                </div>
            </div>
            
            <button class="btn btn-primary" onclick="saveConcentrations()">SALVAR CONFIGURAÇÕES</button>
        </div>
    </div>
    
    <!-- NOTIFICAÇÃO -->
    <div class="notification" id="notification">
        <div id="notificationTitle" style="color: var(--neon); font-weight: bold; font-size: 1.1rem;"></div>
        <div id="notificationMessage" style="margin-top: 10px;"></div>
        <button class="btn" onclick="hideNotification()" style="margin-top: 15px;">ENTENDIDO</button>
    </div>

    <script>
        // ======================
        // BANCO DE DADOS ATUALIZADO
        // ======================
        let appData = {
            warrior: {
                name: "JUNÃO",
                weight: 95,
                arm: 41,
                belly: 99,
                goalWeight: 105,
                goalArm: 47.7,
                goalBelly: 85
            },
            
            battle: {
                water: 0,
                teas: 0,
                injections: {},
                checklist: {},
                adjustments: [],
                warDiary: [],
                dailyNotes: ""
            },
            
            training: {
                current: {},
                history: [],
                prs: []
            },
            
            arsenal: {
                enantato: { 
                    last: null, 
                    next: null,
                    concentration: 250, // mg/ml
                    weeklyDose: 400, // mg/semana
                    perInjection: 0, // será calculado
                    frequency: 2
                },
                deca: { 
                    last: null, 
                    next: null,
                    concentration: 100, // mg/ml
                    weeklyDose: 300, // mg/semana
                    perInjection: 0, // será calculado
                    frequency: 3
                },
                dianabol: { 
                    days: 1, 
                    totalDays: 28,
                    pillMg: 10, // mg por comprimido
                    dailyDose: 20, // mg/dia
                    pillsPerDay: 0 // será calculado
                },
                stano: { active: false, used: false }
            },
            
            health: {
                bp: { systolic: 0, diastolic: 0 },
                pulse: 0,
                temperature: 0,
                oxygenation: 0,
                history: []
            },
            
            system: {
                notifications: {
                    hormones: true,
                    teas: true,
                    bp: true,
                    pr: false,
                    water: false
                },
                lastBackup: null,
                version: "2.0.2"
            }
        };
        
        // ======================
        // DADOS DE TREINO SEMANAL
        // ======================
        const weeklyWarrior = {
            0: { // Domingo
                day: "DOMINGO - RECUPERAÇÃO",
                muscles: ["Prancha", "Panturrilha s/", "Antebraço", "Perna"],
                message: "Dia de regeneração - preparar para a guerra da semana"
            },
            1: { // Segunda
                day: "SEGUNDA - INÍCIO DA GUERRA",
                muscles: ["Prancha", "Panturrilha s/", "Peito", "Tríceps", "Trapézio/Ombro"],
                message: "Primeiro dia de batalha - dar o sangue desde o início"
            },
            2: { // Terça
                day: "TERÇA - COSTAS & BÍCEPS",
                muscles: ["Abs", "Panturrilha c/", "Costas", "Bíceps", "Antebraço"],
                message: "Dia de puxar - lembre-se: costas largas, inimigos pequenos"
            },
            3: { // Quarta
                day: "QUARTA - PERNAS & OMBROS",
                muscles: ["Prancha", "Panturrilha s/", "Trapézio", "Ombro", "Perna"],
                message: "Meio da semana - se doer, está funcionando"
            },
            4: { // Quinta
                day: "QUINTA - PEITO & TRÍCEPS",
                muscles: ["Abs", "Panturrilha c/", "Peito", "Tríceps", "Antebraço"],
                message: "Segunda dose de peito - deixar queimando"
            },
            5: { // Sexta
                day: "SEXTA - ÚLTIMO ATAQUE",
                muscles: ["Prancha", "Panturrilha s/", "Costas", "Bíceps", "Antebraço"],
                message: "Último dia pesado - terminar a semana sem deixar nada no tanque"
            },
            6: { // Sábado
                day: "SÁBADO - FINALIZAÇÃO",
                muscles: ["Abs", "Panturrilha c/", "Trapézio", "Ombro", "Perna"],
                message: "Último esforço - amanhã é descanso merecido"
            }
        };
        
        // ======================
        // CITAÇÕES MOTIVACIONAIS
        // ======================
        const warriorQuotes = [
            "A dor é temporária, o orgulho é eterno.",
            "O inimigo não descansa. Você pode?",
            "Mais uma repetição. Mais um quilograma. Mais um centímetro.",
            "O suor de hoje é o sangue do inimigo amanhã.",
            "Desistir? Jamais!",
            "O corpo obedece quando a mente comanda.",
            "Não é sobre ser o melhor. É sobre ser melhor que ontem.",
            "A batalha é ganha no planejamento, não no campo.",
            "Foco. Disciplina. Consistência. Vitória.",
            "Quando pensar em parar, lembre-se do porquê começou."
        ];
        
        // ======================
        // FUNÇÕES PARA CALCULAR DOSAGENS
        // ======================
        function calculateDosages() {
            // Calcular volume por injeção para Enantato
            appData.arsenal.enantato.perInjection = 
                (appData.arsenal.enantato.weeklyDose / appData.arsenal.enantato.frequency) / appData.arsenal.enantato.concentration;
            
            // Calcular volume por injeção para Deca
            appData.arsenal.deca.perInjection = 
                (appData.arsenal.deca.weeklyDose / appData.arsenal.deca.frequency) / appData.arsenal.deca.concentration;
            
            // Calcular comprimidos por dia para Dianabol
            appData.arsenal.dianabol.pillsPerDay = 
                appData.arsenal.dianabol.dailyDose / appData.arsenal.dianabol.pillMg;
            
            console.log("Dosagens calculadas:");
            console.log(`- Enantato: ${appData.arsenal.enantato.perInjection.toFixed(2)}ml por aplicação (${appData.arsenal.enantato.frequency}x/semana)`);
            console.log(`- Deca: ${appData.arsenal.deca.perInjection.toFixed(2)}ml por aplicação (${appData.arsenal.deca.frequency}x/semana)`);
            console.log(`- Dianabol: ${appData.arsenal.dianabol.pillsPerDay} comprimidos/dia`);
        }
        
        // ======================
        // INICIALIZAÇÃO DO SISTEMA
        // ======================
        function initWarriorSystem() {
            loadWarriorData();
            updateWarriorTime();
            setupDailyWarfare();
            setupBattlefield();
            calculateDosages();
            updateArsenalStatus();
            setupNotifications();
            loadChecklist();
            
            // Atualizar hora
            setInterval(updateWarriorTime, 60000);
            
            // Motivação aleatória
            setTimeout(showRandomMotivation, 2000);
            
            // Adicionar eventos para atualização em tempo real
            const concentrationInputs = [
                'configEnantatoConc', 'configEnantatoWeekly',
                'configDecaConc', 'configDecaWeekly',
                'configDianabolMg', 'configDianabolDaily'
            ];
            
            concentrationInputs.forEach(id => {
                const element = document.getElementById(id);
                if (element) {
                    element.addEventListener('input', updateConcentrationPreview);
                }
            });
            
            console.log("⚔️ SISTEMA TREINADOR INICIADO");
        }
        
        // ======================
        // FUNÇÕES PRINCIPAIS
        // ======================
        function loadWarriorData() {
            const saved = localStorage.getItem("warriorTrainingSystem");
            if (saved) {
                appData = JSON.parse(saved);
                console.log("Dados de guerra carregados");
            }
            
            // Atualizar data no modal do diário
            const today = new Date().toISOString().split('T')[0];
            document.getElementById('warDiaryDate').value = today;
            document.getElementById('prDate').value = today;
            
            // Configurar sliders
            document.getElementById('mentalState').addEventListener('input', function() {
                document.getElementById('mentalStateValue').textContent = this.value;
            });
            
            document.getElementById('energyLevel').addEventListener('input', function() {
                document.getElementById('energyLevelValue').textContent = this.value;
            });
        }
        
        function saveWarriorData() {
            localStorage.setItem("warriorTrainingSystem", JSON.stringify(appData));
            console.log("Dados de guerra salvos");
        }
        
        function updateWarriorTime() {
            const now = new Date();
            document.getElementById("currentDate").textContent = 
                now.toLocaleDateString('pt-BR', { weekday: 'short', day: '2-digit', month: '2-digit' });
            document.getElementById("currentTime").textContent = 
                now.toLocaleTimeString('pt-BR', { hour: '2-digit', minute: '2-digit' });
        }
        
        function setupDailyWarfare() {
            const today = new Date();
            const dayOfWeek = today.getDay();
            const battle = weeklyWarrior[dayOfWeek];
            
            // Missão do dia
            document.getElementById("dayMission").textContent = battle.message;
            
            // Treino do dia
            const workoutList = battle.muscles.map(m => `⚔️ ${m}`).join('<br>');
            document.getElementById("todayWorkout").innerHTML = workoutList;
            
            // Ciclo do dia - USANDO DOSAGENS CALCULADAS
            let arsenalInfo = "";
            if (dayOfWeek === 1 || dayOfWeek === 3 || dayOfWeek === 5) { // Seg, Qua, Sex
                const decaMg = appData.arsenal.deca.perInjection * appData.arsenal.deca.concentration;
                arsenalInfo += `• Deca NPP ${appData.arsenal.deca.perInjection.toFixed(2)}ml (${decaMg.toFixed(0)}mg)<br>`;
            }
            if (dayOfWeek === 4 || dayOfWeek === 0) { // Qui, Dom
                const enantatoMg = appData.arsenal.enantato.perInjection * appData.arsenal.enantato.concentration;
                arsenalInfo += `• Enantato ${appData.arsenal.enantato.perInjection.toFixed(2)}ml (${enantatoMg.toFixed(0)}mg)<br>`;
            }
            arsenalInfo += `• Dianabol ${appData.arsenal.dianabol.pillsPerDay} comprimidos (${appData.arsenal.dianabol.dailyDose}mg)<br>`;
            if (appData.arsenal.stano.active) {
                arsenalInfo += "• Stanozolol 10mg (pré-treino)<br>";
            }
            document.getElementById("todayCycle").innerHTML = arsenalInfo;
            
            // Chás do dia
            const teasInfo = `
                ☕ Saw Palmetto (manhã/noite)<br>
                ☕ Chá Verde (3x/dia)<br>
                ☕ Cardo Mariano (manhã/noite)<br>
                ☕ Hibisco (tarde)<br>
                ☕ Dente-de-Leão (noite)
            `;
            document.getElementById("todayTeas").innerHTML = teasInfo;
            
            updateInjectionStatus();
            updateWaterDisplay();
            updateTeaDisplay();
        }
        
        // ======================
        // FUNÇÕES PARA CHECKLIST
        // ======================
        function saveChecklist() {
            const today = new Date().toISOString().split('T')[0];
            
            // Salvar estado de cada checkbox
            const checkboxes = ['checkWeight', 'checkBP', 'checkCycle', 'checkTeas', 'checkWater', 'checkSuplements'];
            checkboxes.forEach(id => {
                const checkbox = document.getElementById(id);
                if (checkbox) {
                    if (!appData.battle.checklist[today]) {
                        appData.battle.checklist[today] = {};
                    }
                    appData.battle.checklist[today][id] = checkbox.checked;
                }
            });
            
            saveWarriorData();
        }
        
        function loadChecklist() {
            const today = new Date().toISOString().split('T')[0];
            const todayChecklist = appData.battle.checklist[today] || {};
            
            // Carregar estado de cada checkbox
            for (const [id, checked] of Object.entries(todayChecklist)) {
                const checkbox = document.getElementById(id);
                if (checkbox) {
                    checkbox.checked = checked;
                }
            }
        }
        
        // ======================
        // FUNÇÕES PARA ÁGUA E CHÁS
        // ======================
        function addWater(ml) {
            appData.battle.water += ml;
            updateWaterDisplay();
            saveWarriorData();
            
            // Verificar se completou a meta
            if (appData.battle.water >= 5000) {
                showWarriorNotification("💧 HIDRATAÇÃO", "Meta de 5L atingida! Corpo pronto para a guerra.");
                document.getElementById('checkWater').checked = true;
                saveChecklist();
            }
        }
        
        function updateWaterDisplay() {
            const waterBar = document.getElementById("waterBar");
            const waterAmount = document.getElementById("waterAmount");
            const percentage = Math.min((appData.battle.water / 5000) * 100, 100);
            
            waterBar.style.width = percentage + "%";
            waterAmount.textContent = appData.battle.water;
        }
        
        function markTea() {
            appData.battle.teas++;
            updateTeaDisplay();
            saveWarriorData();
            
            // Verificar se completou a meta
            if (appData.battle.teas >= 5) {
                showWarriorNotification("☕ CHÁS", "Todos os chás do dia consumidos! Proteção máxima ativada.");
                document.getElementById('checkTeas').checked = true;
                saveChecklist();
            }
        }
        
        function updateTeaDisplay() {
            const teaCount = document.getElementById("teaCount");
            teaCount.textContent = `(${appData.battle.teas}/5)`;
        }
        
        // ======================
        // FUNÇÕES PARA CICLO HORMONAL
        // ======================
        function updateArsenalStatus() {
            const now = new Date();
            
            // Enantato (Quinta e Domingo)
            const nextEnantato = new Date(now);
            if (now.getDay() === 4) {
                nextEnantato.setDate(now.getDate() + 3);
            } else if (now.getDay() === 0) {
                nextEnantato.setDate(now.getDate() + 4);
            } else {
                const daysUntilThursday = (4 - now.getDay() + 7) % 7;
                const daysUntilSunday = (0 - now.getDay() + 7) % 7;
                nextEnantato.setDate(now.getDate() + Math.min(daysUntilThursday, daysUntilSunday));
            }
            
            // Atualizar display com dosagens calculadas
            document.getElementById("nextEnantato").innerHTML = `
                ${nextEnantato.toLocaleDateString('pt-BR')}<br>
                <small style="color: #888; font-size: 0.8rem;">
                    ${appData.arsenal.enantato.perInjection.toFixed(2)}ml por aplicação<br>
                    (${(appData.arsenal.enantato.perInjection * appData.arsenal.enantato.concentration).toFixed(0)}mg)
                </small>
            `;
            
            // Atualizar detalhes do Enantato
            document.getElementById("enantatoDetails").innerHTML = `
                ${appData.arsenal.enantato.concentration}mg/ml | ${appData.arsenal.enantato.weeklyDose}mg/semana
            `;
            
            // Deca NPP (Segunda, Quarta, Sexta)
            const nextDeca = new Date(now);
            const decaDays = [1, 3, 5];
            let minDaysDeca = 7;
            
            decaDays.forEach(day => {
                let daysUntil = (day - now.getDay() + 7) % 7;
                if (daysUntil === 0) daysUntil = 7;
                if (daysUntil < minDaysDeca) minDaysDeca = daysUntil;
            });
            
            nextDeca.setDate(now.getDate() + minDaysDeca);
            
            document.getElementById("nextDeca").innerHTML = `
                ${nextDeca.toLocaleDateString('pt-BR')}<br>
                <small style="color: #888; font-size: 0.8rem;">
                    ${appData.arsenal.deca.perInjection.toFixed(2)}ml por aplicação<br>
                    (${(appData.arsenal.deca.perInjection * appData.arsenal.deca.concentration).toFixed(0)}mg)
                </small>
            `;
            
            // Atualizar detalhes do Deca
            document.getElementById("decaDetails").innerHTML = `
                ${appData.arsenal.deca.concentration}mg/ml | ${appData.arsenal.deca.weeklyDose}mg/semana
            `;
            
            // Dianabol
            document.getElementById("dianabolStatus").innerHTML = `
                DIA ${appData.arsenal.dianabol.days}/${appData.arsenal.dianabol.totalDays}<br>
                <small style="color: #888; font-size: 0.8rem;">
                    ${appData.arsenal.dianabol.pillsPerDay} comprimidos/dia<br>
                    (${appData.arsenal.dianabol.dailyDose}mg)
                </small>
            `;
            
            // Atualizar detalhes do Dianabol
            document.getElementById("dianabolDetails").innerHTML = `
                ${appData.arsenal.dianabol.pillMg}mg/comprimido | ${appData.arsenal.dianabol.dailyDose}mg/dia
            `;
            
            // Stanozolol
            const stanoStatus = document.getElementById("stanoStatus");
            if (appData.arsenal.stano.active) {
                stanoStatus.textContent = "ATIVO PARA HOJE";
                stanoStatus.style.color = "var(--neon)";
            } else {
                stanoStatus.textContent = "NÃO USAR HOJE";
                stanoStatus.style.color = "#888";
            }
        }
        
        function markInjection(type) {
            const today = new Date().toISOString().split('T')[0];
            
            if (!appData.battle.injections[today]) {
                appData.battle.injections[today] = {};
            }
            
            // Calcular a dosagem em mg baseada na concentração
            let dosageMg = 0;
            let volume = 0;
            if (type === 'enantato') {
                volume = appData.arsenal.enantato.perInjection;
                dosageMg = volume * appData.arsenal.enantato.concentration;
            } else if (type === 'deca') {
                volume = appData.arsenal.deca.perInjection;
                dosageMg = volume * appData.arsenal.deca.concentration;
            }
            
            appData.battle.injections[today][type] = {
                time: new Date().toLocaleTimeString(),
                dosage: dosageMg.toFixed(0),
                volume: volume.toFixed(2),
                concentration: type === 'enantato' ? appData.arsenal.enantato.concentration : appData.arsenal.deca.concentration
            };
            
            updateInjectionStatus();
            saveWarriorData();
            
            showWarriorNotification("💉 " + type.toUpperCase(), 
                `${dosageMg.toFixed(0)}mg aplicados (${volume.toFixed(2)}ml)`);
        }
        
        function markDianabol() {
            const today = new Date().toISOString().split('T')[0];
            
            if (!appData.battle.injections[today]) {
                appData.battle.injections[today] = {};
            }
            
            appData.battle.injections[today].dianabol = {
                time: new Date().toLocaleTimeString(),
                dosage: appData.arsenal.dianabol.dailyDose,
                pills: appData.arsenal.dianabol.pillsPerDay,
                pillMg: appData.arsenal.dianabol.pillMg
            };
            
            appData.arsenal.dianabol.days++;
            
            updateInjectionStatus();
            updateArsenalStatus();
            saveWarriorData();
            
            showWarriorNotification("💊 DIANABOL", 
                `${appData.arsenal.dianabol.dailyDose}mg registrados - dia ${appData.arsenal.dianabol.days} da batalha`);
        }
        
        function toggleStano() {
            appData.arsenal.stano.active = !appData.arsenal.stano.active;
            updateArsenalStatus();
            saveWarriorData();
            
            if (appData.arsenal.stano.active) {
                showWarriorNotification("⚔️ STANOZOLOL", "Ativado para hoje. Use com sabedoria guerreiro!");
            } else {
                showWarriorNotification("⚔️ STANOZOLOL", "Desativado. Descanso também é treino.");
            }
        }
        
        function updateInjectionStatus() {
            const today = new Date().toISOString().split('T')[0];
            const todayInjections = appData.battle.injections[today] || {};
            
            // Verificar se todas as injeções foram aplicadas
            const cycleCheck = document.getElementById('checkCycle');
            if (cycleCheck) {
                const hasEnantato = todayInjections.enantato || false;
                const hasDeca = todayInjections.deca || false;
                const hasDianabol = todayInjections.dianabol || false;
                
                // Marcar como concluído se todas as injeções do dia foram aplicadas
                const dayOfWeek = new Date().getDay();
                let expectedInjections = 0;
                let completedInjections = 0;
                
                if (dayOfWeek === 1 || dayOfWeek === 3 || dayOfWeek === 5) {
                    expectedInjections++; // Deca
                    if (hasDeca) completedInjections++;
                }
                if (dayOfWeek === 4 || dayOfWeek === 0) {
                    expectedInjections++; // Enantato
                    if (hasEnantato) completedInjections++;
                }
                
                // Dianabol sempre
                expectedInjections++;
                if (hasDianabol) completedInjections++;
                
                cycleCheck.checked = (completedInjections === expectedInjections);
                saveChecklist();
            }
        }
        
        // ======================
        // FUNÇÕES PARA CONCENTRAÇÕES
        // ======================
        function updateConcentrationPreview() {
            // Enantato
            const enantatoConc = parseFloat(document.getElementById('configEnantatoConc').value) || 250;
            const enantatoWeekly = parseFloat(document.getElementById('configEnantatoWeekly').value) || 400;
            const enantatoPerInjection = (enantatoWeekly / 2) / enantatoConc;
            
            document.getElementById('enantatoCalc').innerHTML = `
                <strong>Resultado:</strong><br>
                • ${enantatoWeekly}mg/semana<br>
                • ${enantatoPerInjection.toFixed(2)}ml por aplicação (2×/semana)<br>
                • Total: ${(enantatoPerInjection * 2).toFixed(2)}ml/semana
            `;
            
            // Deca
            const decaConc = parseFloat(document.getElementById('configDecaConc').value) || 100;
            const decaWeekly = parseFloat(document.getElementById('configDecaWeekly').value) || 300;
            const decaPerInjection = (decaWeekly / 3) / decaConc;
            
            document.getElementById('decaCalc').innerHTML = `
                <strong>Resultado:</strong><br>
                • ${decaWeekly}mg/semana<br>
                • ${decaPerInjection.toFixed(2)}ml por aplicação (3×/semana)<br>
                • Total: ${(decaPerInjection * 3).toFixed(2)}ml/semana
            `;
            
            // Dianabol
            const dianabolMg = parseFloat(document.getElementById('configDianabolMg').value) || 10;
            const dianabolDaily = parseFloat(document.getElementById('configDianabolDaily').value) || 20;
            const pillsPerDay = dianabolDaily / dianabolMg;
            
            document.getElementById('dianabolCalc').innerHTML = `
                <strong>Resultado:</strong><br>
                • ${dianabolDaily}mg/dia<br>
                • ${pillsPerDay} comprimidos de ${dianabolMg}mg<br>
                • Total: ${(dianabolDaily * 28)}mg/ciclo (28 dias)
            `;
        }
        
        function saveConcentrations() {
            // Salvar Enantato
            appData.arsenal.enantato.concentration = parseFloat(document.getElementById('configEnantatoConc').value) || 250;
            appData.arsenal.enantato.weeklyDose = parseFloat(document.getElementById('configEnantatoWeekly').value) || 400;
            
            // Salvar Deca
            appData.arsenal.deca.concentration = parseFloat(document.getElementById('configDecaConc').value) || 100;
            appData.arsenal.deca.weeklyDose = parseFloat(document.getElementById('configDecaWeekly').value) || 300;
            
            // Salvar Dianabol
            appData.arsenal.dianabol.pillMg = parseFloat(document.getElementById('configDianabolMg').value) || 10;
            appData.arsenal.dianabol.dailyDose = parseFloat(document.getElementById('configDianabolDaily').value) || 20;
            
            // Recalcular dosagens
            calculateDosages();
            
            // Atualizar display
            updateArsenalStatus();
            setupDailyWarfare();
            
            // Salvar dados
            saveWarriorData();
            
            // Fechar modal
            hideModal('concentrationModal');
            
            showWarriorNotification("⚗️ CONCENTRAÇÕES", "Configurações de dosagem atualizadas!");
        }
        
        // ======================
        // FUNÇÕES PARA TREINO
        // ======================
        function setupBattlefield() {
            const today = new Date();
            const dayOfWeek = today.getDay();
            const battle = weeklyWarrior[dayOfWeek];
            const container = document.getElementById("workoutContainer");
            
            container.innerHTML = `
                <div style="color: var(--neon); font-family: 'Russo One', sans-serif; font-size: 1.3rem; margin-bottom: 20px; text-transform: uppercase; letter-spacing: 2px;">
                    ${battle.day}
                </div>
            `;
            
            battle.muscles.forEach(muscle => {
                const muscleDiv = document.createElement("div");
                muscleDiv.className = "muscle-group";
                
                muscleDiv.innerHTML = `
                    <div class="muscle-title">${muscle}</div>
                    <div class="rep-input">
                        <div class="rep-box" data-muscle="${muscle}" data-reps="5">5</div>
                        <div class="rep-box" data-muscle="${muscle}" data-reps="10">10</div>
                        <div class="rep-box" data-muscle="${muscle}" data-reps="15">15</div>
                        <div class="rep-box" data-muscle="${muscle}" data-reps="20">20</div>
                        <div class="rep-box" data-muscle="${muscle}" data-reps="25">25</div>
                        <input type="number" placeholder="Outro" style="width: 80px; padding: 5px; background: #111; color: #FFF;" 
                               onchange="setCustomReps('${muscle}', this.value)">
                    </div>
                    <div style="margin-top: 10px; color: #888; font-family: 'Orbitron', monospace; font-size: 0.9rem;">
                        Reps registradas: <span id="reps-${muscle}" style="color: var(--neon);">0</span>
                    </div>
                `;
                
                container.appendChild(muscleDiv);
            });
            
            // Event listeners para reps
            setTimeout(() => {
                document.querySelectorAll(".rep-box").forEach(box => {
                    box.addEventListener("click", function() {
                        const muscle = this.getAttribute("data-muscle");
                        const reps = parseInt(this.getAttribute("data-reps"));
                        addWarriorReps(muscle, reps);
                    });
                });
            }, 100);
            
            loadBattleHistory();
            loadTrophies();
        }
        
        function addWarriorReps(muscle, reps) {
            if (!appData.training.current[muscle]) {
                appData.training.current[muscle] = [];
            }
            
            appData.training.current[muscle].push(reps);
            updateRepDisplay(muscle);
            saveWarriorData();
        }
        
        function setCustomReps(muscle, reps) {
            if (reps && !isNaN(reps) && reps > 0) {
                addWarriorReps(muscle, parseInt(reps));
            }
        }
        
        function updateRepDisplay(muscle) {
            const element = document.getElementById(`reps-${muscle}`);
            if (element && appData.training.current[muscle]) {
                const total = appData.training.current[muscle].reduce((a, b) => a + b, 0);
                element.textContent = appData.training.current[muscle].join(" + ") + ` = ${total}`;
            }
        }
        
        function saveWorkout() {
            const today = new Date().toISOString().split('T')[0];
            const workout = {
                date: today,
                muscles: appData.training.current,
                totalReps: Object.values(appData.training.current).flat().reduce((a, b) => a + b, 0)
            };
            
            appData.training.history.push(workout);
            appData.training.current = {};
            
            saveWarriorData();
            showWarriorNotification("💪 BATALHA", "Treino registrado nos anais da guerra!");
            setupBattlefield();
        }
        
        function clearWorkout() {
            if (confirm("Limpar campo de batalha? Todos os registros serão perdidos.")) {
                appData.training.current = {};
                setupBattlefield();
            }
        }
        
        // ======================
        // FUNÇÕES PARA DIÁRIO DE GUERRA
        // ======================
        function showRandomMotivation() {
            const quote = warriorQuotes[Math.floor(Math.random() * warriorQuotes.length)];
            document.getElementById("dailyQuote").textContent = `"${quote}"`;
        }
        
        function saveWarDiary() {
            const date = document.getElementById('warDiaryDate').value;
            const content = document.getElementById('warDiaryContent').value;
            const mentalState = document.getElementById('mentalState').value;
            const energyLevel = document.getElementById('energyLevel').value;
            
            if (!content.trim()) {
                showWarriorNotification("📝 DIÁRIO", "Por favor, escreva algo no diário.");
                return;
            }
            
            const entry = {
                date: date || new Date().toISOString().split('T')[0],
                content: content,
                mentalState: parseInt(mentalState),
                energyLevel: parseInt(energyLevel),
                timestamp: new Date().toISOString()
            };
            
            appData.battle.warDiary.push(entry);
            saveWarriorData();
            
            // Limpar campos
            document.getElementById('warDiaryContent').value = '';
            document.getElementById('mentalState').value = 5;
            document.getElementById('mentalStateValue').textContent = '5';
            document.getElementById('energyLevel').value = 5;
            document.getElementById('energyLevelValue').textContent = '5';
            
            hideModal('warDiaryModal');
            showWarriorNotification("📝 DIÁRIO", "Registro de guerra salvo com sucesso!");
        }
        
        // ======================
        // FUNÇÃO DIA CONCLUÍDO
        // ======================
        function completeDay() {
            const today = new Date().toISOString().split('T')[0];
            
            // Marcar todos os checkboxes como concluídos
            const checkboxes = ['checkWeight', 'checkBP', 'checkCycle', 'checkTeas', 'checkWater', 'checkSuplements'];
            checkboxes.forEach(id => {
                const checkbox = document.getElementById(id);
                if (checkbox) {
                    checkbox.checked = true;
                }
            });
            
            // Completar metas de água e chás
            appData.battle.water = 5000;
            appData.battle.teas = 5;
            
            // Atualizar exibição
            updateWaterDisplay();
            updateTeaDisplay();
            
            // Salvar checklist
            saveChecklist();
            
            // Criar registro do dia concluído
            const completedDay = {
                date: today,
                timestamp: new Date().toISOString(),
                water: appData.battle.water,
                teas: appData.battle.teas,
                checklist: appData.battle.checklist[today] || {}
            };
            
            if (!appData.battle.adjustments) {
                appData.battle.adjustments = [];
            }
            
            appData.battle.adjustments.push({
                type: "dayCompleted",
                date: today,
                details: "Dia concluído com sucesso!",
                timestamp: new Date().toISOString()
            });
            
            saveWarriorData();
            
            showWarriorNotification("✅ DIA CONCLUÍDO", 
                "Todos os objetivos do dia foram alcançados! Descanse, guerreiro. Amanhã a batalha continua.");
        }
        
        // ======================
        // FUNÇÃO PARA REGISTRAR AJUSTES
        // ======================
        function saveAdjustment() {
            const type = document.getElementById('adjustType').value;
            const details = document.getElementById('adjustDetails').value;
            const compensation = document.getElementById('adjustCompensation').value;
            
            if (!details.trim()) {
                showWarriorNotification("⚠️ AJUSTE", "Por favor, descreva o ajuste.");
                return;
            }
            
            const adjustment = {
                type: type,
                details: details,
                compensation: compensation,
                date: new Date().toISOString().split('T')[0],
                timestamp: new Date().toISOString()
            };
            
            if (!appData.battle.adjustments) {
                appData.battle.adjustments = [];
            }
            
            appData.battle.adjustments.push(adjustment);
            saveWarriorData();
            
            // Limpar campos
            document.getElementById('adjustDetails').value = '';
            document.getElementById('adjustCompensation').value = 'none';
            
            hideModal('adjustModal');
            showWarriorNotification("📝 AJUSTE", "Ajuste registrado no sistema!");
        }
        
        // ======================
        // FUNÇÕES PARA PRs
        // ======================
        function savePR() {
            const exercise = document.getElementById('prExercise').value;
            const weight = parseFloat(document.getElementById('prWeight').value);
            const reps = parseInt(document.getElementById('prReps').value);
            const date = document.getElementById('prDate').value;
            const notes = document.getElementById('prNotes').value;
            
            if (!exercise || !weight || !reps) {
                showWarriorNotification("🏆 PR", "Preencha todos os campos obrigatórios!");
                return;
            }
            
            const pr = {
                exercise: exercise,
                weight: weight,
                reps: reps,
                date: date || new Date().toISOString().split('T')[0],
                notes: notes,
                timestamp: new Date().toISOString()
            };
            
            appData.training.prs.push(pr);
            saveWarriorData();
            
            // Limpar campos
            document.getElementById('prExercise').value = '';
            document.getElementById('prWeight').value = '';
            document.getElementById('prReps').value = '';
            document.getElementById('prNotes').value = '';
            
            hideModal('prModal');
            showWarriorNotification("🏆 TROFÉU", `Novo recorde registrado: ${exercise} - ${weight}kg × ${reps} reps!`);
            loadTrophies();
        }
        
        function loadTrophies() {
            const container = document.getElementById('prList');
            if (!appData.training.prs || appData.training.prs.length === 0) {
                container.innerHTML = `
                    <div style="text-align: center; color: #666; padding: 20px; font-family: 'Audiowide', cursive;">
                        NENHUM TROFÉU REGISTRADO<br>
                        <small>O primeiro recorde começa aqui</small>
                    </div>
                `;
                return;
            }
            
            let html = '';
            // Mostrar apenas os últimos 5 PRs
            const recentPRs = appData.training.prs.slice(-5).reverse();
            
            recentPRs.forEach(pr => {
                html += `
                    <div class="info-card" style="margin-bottom: 10px; border-left-color: var(--gold);">
                        <div style="color: var(--gold); font-weight: bold;">🏆 ${pr.exercise}</div>
                        <div style="color: var(--neon); font-size: 1.1rem; margin: 5px 0;">
                            ${pr.weight}kg × ${pr.reps} reps
                        </div>
                        <div style="color: #888; font-size: 0.8rem;">${pr.date}</div>
                        ${pr.notes ? `<div style="color: #aaa; font-size: 0.9rem; margin-top: 5px;">${pr.notes}</div>` : ''}
                    </div>
                `;
            });
            
            container.innerHTML = html;
        }
        
        // ======================
        // FUNÇÕES PARA SAÚDE
        // ======================
        function measureBP() {
            // Simulação - em app real seria integrado com dispositivo
            const systolic = Math.floor(Math.random() * 20) + 120;
            const diastolic = Math.floor(Math.random() * 15) + 75;
            
            appData.health.bp = { systolic, diastolic };
            document.getElementById("bpValue").textContent = `${systolic}/${diastolic}`;
            
            // Marcar checkbox
            document.getElementById('checkBP').checked = true;
            saveChecklist();
            
            saveWarriorData();
            
            let message = `Pressão: ${systolic}/${diastolic} mmHg`;
            if (systolic > 140 || diastolic > 90) {
                message += " ⚠️ ALTA";
                showWarriorNotification("❤️ ALERTA", "Pressão elevada - monitorar!");
            }
            
            showWarriorNotification("❤️ PRESSÃO", message);
        }
        
        function saveHealthData() {
            const systolic = parseInt(document.getElementById('healthSystolic').value);
            const diastolic = parseInt(document.getElementById('healthDiastolic').value);
            const pulse = parseInt(document.getElementById('healthPulse').value);
            const temp = parseFloat(document.getElementById('healthTemp').value);
            const ox = parseInt(document.getElementById('healthOx').value);
            
            if (!systolic || !diastolic || !pulse || !temp || !ox) {
                showWarriorNotification("❤️ SAÚDE", "Preencha todos os campos!");
                return;
            }
            
            const healthRecord = {
                date: new Date().toISOString().split('T')[0],
                bp: { systolic, diastolic },
                pulse: pulse,
                temperature: temp,
                oxygenation: ox,
                timestamp: new Date().toISOString()
            };
            
            appData.health.history.push(healthRecord);
            appData.health.bp = { systolic, diastolic };
            appData.health.pulse = pulse;
            appData.health.temperature = temp;
            appData.health.oxygenation = ox;
            
            // Atualizar exibição
            document.getElementById('bpValue').textContent = `${systolic}/${diastolic}`;
            document.getElementById('pulseValue').textContent = pulse;
            document.getElementById('tempValue').textContent = `${temp}°C`;
            document.getElementById('oxValue').textContent = `${ox}%`;
            
            // Limpar campos
            document.getElementById('healthSystolic').value = '';
            document.getElementById('healthDiastolic').value = '';
            document.getElementById('healthPulse').value = '';
            document.getElementById('healthTemp').value = '';
            document.getElementById('healthOx').value = '';
            
            saveWarriorData();
            hideModal('healthModal');
            showWarriorNotification("❤️ SAÚDE", "Dados médicos registrados com sucesso!");
        }
        
        // ======================
        // FUNÇÕES PARA PERFIL
        // ======================
        function updateWeight(weight) {
            if (weight && !isNaN(weight) && weight > 0) {
                appData.warrior.weight = parseFloat(weight);
                document.getElementById('configWeight').value = weight;
                saveWarriorData();
                showWarriorNotification("⚖️ PESO", `Peso atualizado: ${weight}kg`);
            }
        }
        
        function updateProfile() {
            const weight = parseFloat(document.getElementById('configWeight').value);
            const arm = parseFloat(document.getElementById('configArm').value);
            const belly = parseFloat(document.getElementById('configBelly').value);
            
            if (weight && arm && belly) {
                appData.warrior.weight = weight;
                appData.warrior.arm = arm;
                appData.warrior.belly = belly;
                
                // Atualizar estatísticas
                document.getElementById('statWeight').textContent = `${weight}/105kg`;
                document.getElementById('statArm').textContent = `${arm}/47.7cm`;
                document.getElementById('statBelly').textContent = `${belly}cm ${belly > 85 ? '⚠️' : '✅'}`;
                
                // Atualizar barras de progresso
                const weightProgress = ((weight - 95) / (105 - 95)) * 100;
                document.getElementById('weightBar').style.width = `${Math.min(Math.max(weightProgress, 0), 100)}%`;
                
                const armProgress = ((arm - 41) / (47.7 - 41)) * 100;
                document.getElementById('armBar').style.width = `${Math.min(Math.max(armProgress, 0), 100)}%`;
                
                const bellyProgress = ((99 - belly) / (99 - 85)) * 100;
                document.getElementById('bellyBar').style.width = `${Math.min(Math.max(bellyProgress, 0), 100)}%`;
                
                saveWarriorData();
                showWarriorNotification("📊 PERFIL", "Dados atualizados com sucesso!");
            }
        }
        
        // ======================
        // FUNÇÕES DE NOTIFICAÇÃO
        // ======================
        function showWarriorNotification(title, message) {
            const notification = document.getElementById("notification");
            document.getElementById("notificationTitle").textContent = title;
            document.getElementById("notificationMessage").textContent = message;
            
            notification.classList.add("show");
            
            setTimeout(() => {
                notification.classList.remove("show");
            }, 5000);
        }
        
        function hideNotification() {
            document.getElementById("notification").classList.remove("show");
        }
        
        function showModal(modalId) {
            document.getElementById(modalId).style.display = "flex";
        }
        
        function hideModal(modalId) {
            document.getElementById(modalId).style.display = "none";
        }
        
        function setupNotifications() {
            // Em um app real, aqui configuraríamos notificações push
            console.log("Notificações configuradas:", appData.system.notifications);
        }
        
        // ======================
        // FUNÇÕES DE BACKUP
        // ======================
        function exportData() {
            const dataStr = JSON.stringify(appData);
            const dataUri = 'data:application/json;charset=utf-8,'+ encodeURIComponent(dataStr);
            
            const exportFileDefaultName = `warrior-backup-${new Date().toISOString().split('T')[0]}.json`;
            
            const linkElement = document.createElement('a');
            linkElement.setAttribute('href', dataUri);
            linkElement.setAttribute('download', exportFileDefaultName);
            linkElement.click();
            
            appData.system.lastBackup = new Date().toISOString();
            saveWarriorData();
            
            showWarriorNotification("💾 BACKUP", "Arquivo de guerra exportado com sucesso!");
        }
        
        function importData() {
            const input = document.createElement('input');
            input.type = 'file';
            input.accept = '.json';
            
            input.onchange = e => { 
                const file = e.target.files[0];
                const reader = new FileReader();
                
                reader.onload = event => {
                    try {
                        const importedData = JSON.parse(event.target.result);
                        appData = importedData;
                        saveWarriorData();
                        location.reload();
                    } catch (error) {
                        showWarriorNotification("❌ ERRO", "Arquivo de guerra corrompido!");
                    }
                };
                
                reader.readAsText(file);
            };
            
            input.click();
        }
        
        function clearData() {
            if (confirm("⚠️ ZERAR TODO O SISTEMA DE GUERRA?\n\nIsso apagará TODOS os dados de batalha, histórico e configurações.\n\nContinuar?")) {
                localStorage.removeItem("warriorTrainingSystem");
                location.reload();
            }
        }
        
        // ======================
        // HISTÓRICO DE BATALHAS
        // ======================
        function loadBattleHistory() {
            const container = document.getElementById("workoutHistory");
            if (!appData.training.history || appData.training.history.length === 0) {
                container.innerHTML = `
                    <div style="text-align: center; color: #666; padding: 20px; font-family: 'Audiowide', cursive;">
                        NENHUMA BATALHA REGISTRADA<br>
                        <small>O primeiro passo começa aqui</small>
                    </div>
                `;
                return;
            }
            
            let html = "";
            // Mostrar apenas os últimos 5 treinos
            const recentWorkouts = appData.training.history.slice(-5).reverse();
            
            recentWorkouts.forEach(workout => {
                const date = new Date(workout.date);
                html += `
                    <div class="info-card" style="margin-bottom: 10px;">
                        <strong style="color: var(--gold);">${date.toLocaleDateString('pt-BR')}</strong>
                        <div style="margin-top: 5px; color: #CCC;">
                            Reps totais: <span style="color: var(--neon);">${workout.totalReps}</span>
                        </div>
                    </div>
                `;
            });
            
            container.innerHTML = html;
        }
        
        // ======================
        // NAVEGAÇÃO ENTRE ABAS
        // ======================
        document.querySelectorAll('.nav-tab').forEach(tab => {
            tab.addEventListener('click', function(e) {
                e.preventDefault();
                
                document.querySelectorAll('.nav-tab').forEach(t => t.classList.remove('active'));
                document.querySelectorAll('.tab-content').forEach(c => c.classList.remove('active'));
                
                this.classList.add('active');
                const tabId = this.getAttribute('data-tab');
                document.getElementById(tabId).classList.add('active');
            });
        });
        
        // ======================
        // INICIALIZAR SISTEMA
        // ======================
        window.addEventListener('DOMContentLoaded', initWarriorSystem);
    </script>
</body>
</html>
