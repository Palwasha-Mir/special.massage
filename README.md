<!DOCTYPE html>
<html lang="ur">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Im So Sorry Dil ❤️</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 99%, #feada6 100%);
            transition: background 0.8s ease;
        }

        /* Card Setup with Smooth Zoom Animations */
        .card {
            background: rgba(255, 255, 255, 0.92);
            padding: 25px 20px;
            border-radius: 30px;
            box-shadow: 0 15px 35px rgba(255, 105, 180, 0.3);
            text-align: center;
            max-width: 420px;
            width: 90%;
            backdrop-filter: blur(10px);
            position: relative;
            z-index: 10;
            border: 4px solid #fff;
            transition: transform 0.5s ease, opacity 0.5s ease;
        }

        .zoom-in {
            animation: popIn 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
        }

        .zoom-out {
            animation: popOut 0.4s ease forwards;
        }

        @keyframes popIn {
            0% { opacity: 0; transform: scale(0.2) rotate(-10deg); }
            100% { opacity: 1; transform: scale(1) rotate(0deg); }
        }

        @keyframes popOut {
            0% { opacity: 1; transform: scale(1); }
            100% { opacity: 0; transform: scale(1.5) rotate(10deg); }
        }

        /* Animation Stage Container */
        .stage {
            height: 160px;
            width: 100%;
            position: relative;
            background: rgba(255, 240, 245, 0.7);
            border-radius: 20px;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: flex-end;
            padding-bottom: 10px;
            margin-bottom: 15px;
            border: 2px dashed #ffb6c1;
        }

        /* --- SVG Animated Characters (Bubu Bear & Dudu Panda) --- */
        .character {
            width: 80px;
            height: 90px;
            position: absolute;
            transition: all 0.5s ease;
        }

        /* Page 1: Walking & Approaching */
        .walk-bubu {
            left: 10px;
            animation: walkRight 2.5s forwards ease-in-out;
        }

        .walk-dudu {
            right: 10px;
            animation: walkLeft 2.5s forwards ease-in-out;
        }

        @keyframes walkRight {
            0% { left: -60px; }
            50% { transform: translateY(-5px); }
            100% { left: 90px; }
        }

        @keyframes walkLeft {
            0% { right: -60px; }
            50% { transform: translateY(-5px); }
            100% { right: 90px; }
        }

        /* Page 2: SORRY Animation (Bowing & Ear Holding) */
        .sorry-bubu {
            left: 100px;
            animation: earHoldBowing 1.5s infinite alternate ease-in-out;
        }
        .sad-dudu {
            right: 100px;
            animation: sadHeadShake 2s infinite ease-in-out;
        }

        @keyframes earHoldBowing {
            0% { transform: translateY(0) rotate(0deg); }
            100% { transform: translateY(12px) rotate(-15deg); }
        }

        @keyframes sadHeadShake {
            0%, 100% { transform: rotate(0deg); }
            50% { transform: rotate(8deg); }
        }

        /* Page 3: Handshake Animation */
        .hs-bubu { left: 120px; animation: handShakePulse 0.8s infinite alternate; }
        .hs-dudu { right: 120px; animation: handShakePulse 0.8s infinite alternate reverse; }

        @keyframes handShakePulse {
            0% { transform: scale(1); }
            100% { transform: scale(1.08) translateY(-3px); }
        }

        /* Page 4: Grand Hug Animation */
        .hug-couple {
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            animation: hugSqueeze 1.2s infinite ease-in-out;
        }

        @keyframes hugSqueeze {
            0%, 100% { transform: translateX(-50%) scale(1); }
            50% { transform: translateX(-50%) scale(1.15) rotate(3deg); }
        }

        /* Typography & Buttons */
        h1 {
            color: #ff3366;
            font-size: 1.5rem;
            margin-bottom: 8px;
        }

        p {
            color: #555;
            font-size: 1rem;
            line-height: 1.4;
            margin-bottom: 18px;
        }

        .btn-box {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        button {
            background: linear-gradient(45deg, #ff6b81, #ff4757);
            border: none;
            padding: 12px 20px;
            color: white;
            font-size: 1rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(255, 71, 87, 0.4);
            transition: all 0.3s ease;
        }

        button:hover {
            transform: scale(1.06) translateY(-2px);
            box-shadow: 0 8px 20px rgba(255, 71, 87, 0.6);
        }

        .hidden { display: none !important; }

        /* Background Particle Effect */
        .particle {
            position: absolute;
            user-select: none;
            pointer-events: none;
            z-index: 1;
            animation: floatUp 4s linear forwards;
        }

        @keyframes floatUp {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        /* Magic Floating Wand */
        .magic-wand {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #fff;
            width: 55px;
            height: 55px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 26px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.2);
            cursor: pointer;
            z-index: 100;
        }
    </style>
</head>
<body>

    <div id="particles"></div>
    <div class="magic-wand" onclick="burstParticles()" title="Click for Magic!">🪄</div>

    <!-- PAGE 1: WALKING & MEETING -->
    <div id="page1" class="card zoom-in">
        <div class="stage">
            <!-- Bubu Bear -->
            <svg class="character walk-bubu" viewBox="0 0 100 100">
                <circle cx="50" cy="55" r="35" fill="#f4a261"/>
                <circle cx="28" cy="28" r="12" fill="#f4a261"/>
                <circle cx="72" cy="28" r="12" fill="#f4a261"/>
                <circle cx="42" cy="50" r="4" fill="#333"/>
                <circle cx="58" cy="50" r="4" fill="#333"/>
                <ellipse cx="50" cy="62" rx="8" ry="5" fill="#e76f51"/>
            </svg>
            <!-- Dudu Panda -->
            <svg class="character walk-dudu" viewBox="0 0 100 100">
                <circle cx="50" cy="55" r="35" fill="#ffffff" stroke="#333" stroke-width="3"/>
                <circle cx="25" cy="25" r="12" fill="#333"/>
                <circle cx="75" cy="25" r="12" fill="#333"/>
                <ellipse cx="38" cy="50" rx="7" ry="9" fill="#333"/>
                <ellipse cx="62" cy="50" rx="7" ry="9" fill="#333"/>
                <circle cx="38" cy="48" r="2" fill="#fff"/>
                <circle cx="62" cy="48" r="2" fill="#fff"/>
                <ellipse cx="50" cy="63" rx="6" ry="4" fill="#ffb6c1"/>
            </svg>
        </div>
        <h1>Hey Dil! Dekho Kaun Aaya... 🐾</h1>
        <p>Bubu aur Dudu aapse milne chal kar aa rahe hain! Ek dafa unki baat sun lo please?</p>
        <button onclick="goToPage(2, '#e0c3fc')">Suno Unki Baat ✨</button>
    </div>

    <!-- PAGE 2: SORRY (BOWING & EAR HOLDING) -->
    <div id="page2" class="card hidden">
        <div class="stage">
            <!-- Bubu Holding Ears & Bowing -->
            <svg class="character sorry-bubu" viewBox="0 0 100 100">
                <circle cx="50" cy="55" r="35" fill="#f4a261"/>
                <circle cx="28" cy="28" r="12" fill="#e76f51"/>
                <circle cx="72" cy="28" r="12" fill="#e76f51"/>
                <!-- Sad Tear Eyes -->
                <circle cx="42" cy="52" r="4" fill="#333"/>
                <circle cx="58" cy="52" r="4" fill="#333"/>
                <path d="M 45 68 Q 50 60 55 68" stroke="#333" stroke-width="3" fill="none"/>
                <!-- Tear Drop -->
                <path d="M 62 55 Q 65 62 62 65 Q 59 62 62 55" fill="#00b4d8"/>
                <!-- Hands Holding Ears -->
                <ellipse cx="22" cy="35" rx="6" ry="12" fill="#f4a261"/>
                <ellipse cx="78" cy="35" rx="6" ry="12" fill="#f4a261"/>
            </svg>
            <!-- Dudu Sad & Upset -->
            <svg class="character sad-dudu" viewBox="0 0 100 100">
                <circle cx="50" cy="55" r="35" fill="#ffffff" stroke="#333" stroke-width="3"/>
                <circle cx="25" cy="25" r="12" fill="#333"/>
                <circle cx="75" cy="25" r="12" fill="#333"/>
                <ellipse cx="38" cy="52" rx="7" ry="9" fill="#333"/>
                <ellipse cx="62" cy="52" rx="7" ry="9" fill="#333"/>
                <path d="M 43 68 Q 50 62 57 68" stroke="#333" stroke-width="3" fill="none"/>
            </svg>
        </div>
        <h1>I Am So So Sorry Dil! 🥺🙏</h1>
        <p>Bubu apny kaan pakad kar "SORRY" bol raha hai! Ab itna pyara sorry sun kar gussa khatam kar do na?</p>
        <div class="btn-box">
            <button onclick="goToPage(3, '#84fab0')">Acha Thoda Sa Maaf Kiya! 🤝</button>
            <button onclick="goToPage(3, '#84fab0')">Pehle Dosti Karo! 😜</button>
        </div>
    </div>

    <!-- PAGE 3: HANDSHAKE & DOSTI -->
    <div id="page3" class="card hidden">
        <div class="stage">
            <!-- Bubu Handshake -->
            <svg class="character hs-bubu" viewBox="0 0 100 100">
                <circle cx="50" cy="55" r="35" fill="#f4a261"/>
                <circle cx="28" cy="28" r="12" fill="#f4a261"/>
                <circle cx="72" cy="28" r="12" fill="#f4a261"/>
                <circle cx="42" cy="50" r="4" fill="#333"/>
                <circle cx="58" cy="50" r="4" fill="#333"/>
                <path d="M 42 63 Q 50 72 58 63" stroke="#333" stroke-width="3" fill="none"/>
            </svg>
            <!-- Dudu Handshake -->
            <svg class="character hs-dudu" viewBox="0 0 100 100">
                <circle cx="50" cy="55" r="35" fill="#ffffff" stroke="#333" stroke-width="3"/>
                <circle cx="25" cy="25" r="12" fill="#333"/>
                <circle cx="75" cy="25" r="12" fill="#333"/>
                <ellipse cx="38" cy="50" rx="7" ry="9" fill="#333"/>
                <ellipse cx="62" cy="50" rx="7" ry="9" fill="#333"/>
                <path d="M 42 63 Q 50 72 58 63" stroke="#333" stroke-width="3" fill="none"/>
            </svg>
        </div>
        <h1>Pehle Dosti Ka Handshake! 🤝✨</h1>
        <p>Dekho dono ne dosti ka haath mila liya hai. Ab koi gussa nahi bacha!</p>
        <div class="btn-box">
            <button onclick="goToPage(4, '#ffecd2')">Chalo Ab Big Hug Karo! 🫂💖</button>
        </div>
    </div>

    <!-- PAGE 4: GRAND HUG & CELEBRATION -->
    <div id="page4" class="card hidden">
        <div class="stage">
            <!-- Combined Hug Couple -->
            <div class="hug-couple">
                <svg viewBox="0 0 160 100" width="140" height="90">
                    <!-- Bubu Hugging -->
                    <circle cx="55" cy="55" r="35" fill="#f4a261"/>
                    <circle cx="30" cy="28" r="12" fill="#f4a261"/>
                    <!-- Dudu Hugging -->
                    <circle cx="105" cy="55" r="35" fill="#ffffff" stroke="#333" stroke-width="3"/>
                    <circle cx="130" cy="28" r="12" fill="#333"/>
                    <!-- Happy Eyes -->
                    <path d="M 45 52 Q 50 45 55 52" stroke="#333" stroke-width="3" fill="none"/>
                    <path d="M 100 52 Q 105 45 110 52" stroke="#333" stroke-width="3" fill="none"/>
                    <!-- Big Heart Above Hug -->
                    <path d="M 80 25 C 80 15, 65 15, 65 25 C 65 35, 80 45, 80 45 C 80 45, 95 35, 95 25 C 95 15, 80 15, 80 25 Z" fill="#ff4757"/>
                </svg>
            </div>
        </div>
        <h1>Yayyyy! Dil Maan Gaya! 🎉💖</h1>
        <p>Thank you so much Dil! Aapki smile sabse pyari hai. Humesha aise hi khush raho! 🌺🍨✨</p>
        <button onclick="burstParticles()">Ghar Bhar Ke Phool Barsao! 🌸🎆</button>
    </div>

    <script>
        let currPage = 1;
        const pageTheme = {
            1: ['🌸', '🌷', '🐾', '✨', '💖'],
            2: ['🥺', '🌸', '💐', '💔', '🌹'],
            3: ['🤝', '🍫', '⭐', '✨', '🍩'],
            4: ['🎉', '🎆', '💖', '🫂', '🥳', '🌸']
        };

        function goToPage(target, color) {
            const activeCard = document.getElementById('page' + currPage);
            const nextCard = document.getElementById('page' + target);

            document.body.style.background = color;

            activeCard.classList.remove('zoom-in');
            activeCard.classList.add('zoom-out');

            setTimeout(() => {
                activeCard.classList.add('hidden');
                activeCard.classList.remove('zoom-out');

                nextCard.classList.remove('hidden');
                nextCard.classList.add('zoom-in');
                currPage = target;
                burstParticles();
            }, 450);
        }

        function createParticle() {
            const list = pageTheme[currPage] || pageTheme[1];
            const p = document.createElement('div');
            p.className = 'particle';
            p.innerText = list[Math.floor(Math.random() * list.length)];
            p.style.left = Math.random() * 95 + 'vw';
            p.style.fontSize = (Math.random() * 15 + 22) + 'px';
            p.style.animationDuration = (Math.random() * 2 + 3) + 's';
            
            document.getElementById('particles').appendChild(p);
            setTimeout(() => p.remove(), 4000);
        }

        setInterval(createParticle, 300);

        function burstParticles() {
            for(let i = 0; i < 25; i++) {
                setTimeout(createParticle, i * 50);
            }
        }
    </script>
</body>
</html>
