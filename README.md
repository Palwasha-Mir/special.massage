<!DOCTYPE html>
<html lang="ur">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Special Dil ❤️</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            color: #4a4a4a;
            transition: background 1s ease-in-out;
        }

        /* Page Themes (Different Colors for Every Page) */
        .theme-1 { background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 100%); }
        .theme-2 { background: linear-gradient(135deg, #e0c3fc 0%, #8ec5fc 100%); }
        .theme-3 { background: linear-gradient(135deg, #84fab0 0%, #8fd3f4 100%); }
        .theme-4 { background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%); }

        /* Main Card Container */
        .card {
            background: rgba(255, 255, 255, 0.92);
            padding: 25px 20px;
            border-radius: 30px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.15);
            text-align: center;
            max-width: 420px;
            width: 90%;
            backdrop-filter: blur(12px);
            position: relative;
            z-index: 10;
            border: 4px solid rgba(255, 255, 255, 0.8);
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        /* Zoom Animations */
        .zoom-in {
            animation: cartoonZoomIn 0.7s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
        }

        .zoom-out {
            animation: cartoonZoomOut 0.5s ease-in forwards;
        }

        @keyframes cartoonZoomIn {
            0% { opacity: 0; transform: scale(0.1) rotate(-10deg); }
            100% { opacity: 1; transform: scale(1) rotate(0deg); }
        }

        @keyframes cartoonZoomOut {
            0% { opacity: 1; transform: scale(1); }
            100% { opacity: 0; transform: scale(1.8) rotate(10deg); }
        }

        /* Interactive Scene Containers */
        .scene-box {
            height: 140px;
            width: 100%;
            position: relative;
            margin-bottom: 15px;
            overflow: hidden;
            border-radius: 15px;
            background: rgba(255, 255, 255, 0.5);
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .char-img {
            height: 110px;
            width: auto;
        }

        /* Walking Animation for Page 1 */
        .walk-left {
            position: absolute;
            left: -20px;
            animation: walkInLeft 2.5s forwards ease-out;
        }

        .walk-right {
            position: absolute;
            right: -20px;
            animation: walkInRight 2.5s forwards ease-out;
        }

        @keyframes walkInLeft {
            0% { left: -60px; transform: scaleX(1); }
            100% { left: 80px; transform: scaleX(1); }
        }

        @keyframes walkInRight {
            0% { right: -60px; transform: scaleX(-1); }
            100% { right: 80px; transform: scaleX(-1); }
        }

        /* Handshake Pulse Animation */
        .handshake-img {
            animation: bounceShake 1s infinite alternate ease-in-out;
        }

        @keyframes bounceShake {
            0% { transform: scale(1) rotate(-2deg); }
            100% { transform: scale(1.08) rotate(2deg); }
        }

        /* Hug Warmth Animation */
        .hug-img {
            animation: warmHug 1.5s infinite ease-in-out;
        }

        @keyframes warmHug {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.12); }
        }

        h1 {
            color: #ff4081;
            margin-bottom: 10px;
            font-size: 1.6rem;
        }

        p {
            font-size: 1.05rem;
            margin-bottom: 18px;
            line-height: 1.5;
            color: #555;
        }

        .btn-container {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        /* Bouncy Buttons */
        button {
            background: linear-gradient(45deg, #ff758c, #ff7eb3);
            border: none;
            padding: 12px 20px;
            color: white;
            font-size: 1rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(255, 117, 140, 0.4);
        }

        button:hover {
            transform: scale(1.08) translateY(-2px);
            box-shadow: 0 8px 25px rgba(255, 117, 140, 0.6);
        }

        .hidden { display: none !important; }

        /* Floating Background Particles */
        .particle {
            position: absolute;
            user-select: none;
            pointer-events: none;
            z-index: 1;
        }

        @keyframes floatUp {
            0% { transform: translateY(105vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        @keyframes floatSide {
            0% { transform: translateX(-10vw) translateY(50vh) rotate(0deg); opacity: 1; }
            100% { transform: translateX(110vw) translateY(-20vh) rotate(360deg); opacity: 0; }
        }

        /* Magic Wand Button */
        .magic-btn {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #fff;
            border-radius: 50%;
            width: 60px;
            height: 60px;
            font-size: 28px;
            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: 0 5px 20px rgba(0,0,0,0.2);
            cursor: pointer;
            z-index: 100;
            transition: transform 0.3s ease;
        }

        .magic-btn:hover {
            transform: rotate(360deg) scale(1.2);
        }
    </style>
</head>
<body class="theme-1">

    <!-- Dynamic Background Particle Layer -->
    <div id="particle-field"></div>

    <!-- Magic Wand Button -->
    <div class="magic-btn" onclick="triggerMagicExplosion()" title="Click for Magic!">✨</div>

    <!-- Page 1: Walking Bubu & Dudu -->
    <div id="page1" class="card zoom-in">
        <div class="scene-box">
            <img src="https://media.tenor.com/tH-g1W_v41IAAAAC/bear-panda.gif" class="char-img walk-left" alt="Bubu Walking">
            <img src="https://media.tenor.com/2X8s6kF3sBIAAAAC/bubu-dudu.gif" class="char-img walk-right" alt="Dudu Walking">
        </div>
        <h1>Hey Dil! Look Who Came Walking... 🐾🌸</h1>
        <p>Aap naraz ho is liye Bubu aur Dudu aapse milne chal kar aa rahe hain! Unki baat sunoge?</p>
        <button onclick="nextPage(2, 'theme-2')">Aane Do Unhe! ✨</button>
    </div>

    <!-- Page 2: Handshake Scene -->
    <div id="page2" class="card hidden">
        <div class="scene-box">
            <img src="https://media.tenor.com/5wN7b3s47iAAAAAC/bubu-dudu-handshake.gif" class="char-img handshake-img" alt="Bubu Dudu Handshake">
        </div>
        <h1>Pehle Dosti / Handshake Karo! 🤝💖</h1>
        <p>Aise gussa rehne se koi fayda nahi. Dekho dono ne Dosti ka haath badha diya hai!</p>
        <div class="btn-container">
            <button onclick="nextPage(3, 'theme-3')">Handshake Kar Liya! 🤝😊</button>
            <button onclick="nextPage(3, 'theme-3')">Abhi Bhi Thoda Nakhra Hai! 😜</button>
        </div>
    </div>

    <!-- Page 3: Warm Cute Hug Scene -->
    <div id="page3" class="card hidden">
        <div class="scene-box">
            <img src="https://media.tenor.com/J3tG5y0z_kQAAAAC/bubu-dudu-hug.gif" class="char-img hug-img" alt="Bubu Dudu Hug">
        </div>
        <h1>Ab Ek Cute Sa Hug! 🫂❤️</h1>
        <p>Gussa bilkul khatam! Aao ek warm hugging moment create karte hain. Maan jao na please?</p>
        <div class="btn-container">
            <button onclick="nextPage(4, 'theme-4')">Chalo Maan Gayi/Gaya! 🥰</button>
            <button onclick="nextPage(4, 'theme-4')">Ghar Aakar Treat Deno Paregi! 🍫🍦</button>
        </div>
    </div>

    <!-- Page 4: Final Celebration -->
    <div id="page4" class="card hidden">
        <div class="scene-box">
            <img src="https://media.tenor.com/w2Yv2e8254IAAAAC/happy.gif" class="char-img" alt="Happy Dance">
        </div>
        <h1>Yayyyy! Dil Maan Gaya! 🎉✨🐼</h1>
        <p>Thank you Dil! Aapki smile sabse pyari hai. Humesha aise hi khush raho aur muskurate raho! 🌺🍨💖</p>
        <button onclick="triggerMagicExplosion()">Ghar Bhar Kar Phool Barsao! 🌸🎆</button>
    </div>

    <script>
        let currentPage = 1;

        // Custom Items Array for Each Unique Page
        const pageItems = {
            1: ['🌸', '🌷', '🐾', '✨', '💖', '🍃'],
            2: ['🍫', '🍩', '⭐', '🤝', '🍦', '🍓'],
            3: ['🫂', '🌹', '💕', '🧸', '🎈', '💐'],
            4: ['🎉', '🎆', '🐼', '🥳', '🌺', '✨', '💖', '🍨']
        };

        function nextPage(targetPage, newTheme) {
            const currentCard = document.getElementById('page' + currentPage);
            const nextCard = document.getElementById('page' + targetPage);

            // Change Body Background Gradient Smoothly
            document.body.className = newTheme;

            // Apply Zoom Out Effect
            currentCard.classList.remove('zoom-in');
            currentCard.classList.add('zoom-out');

            setTimeout(() => {
                currentCard.classList.add('hidden');
                currentCard.classList.remove('zoom-out');

                // Show Next Page with Zoom In Effect
                nextCard.classList.remove('hidden');
                nextCard.classList.add('zoom-in');
                currentPage = targetPage;

                // Trigger Extra Particles for the New Page
                triggerMagicExplosion();
            }, 500);
        }

        // Particle Creator Function
        function createParticle(itemsArray, animName) {
            const particle = document.createElement('div');
            particle.classList.add('particle');
            particle.innerText = itemsArray[Math.floor(Math.random() * itemsArray.length)];
            particle.style.fontSize = (Math.random() * 18 + 24) + 'px';
            particle.style.animation = `${animName} ${Math.random() * 3 + 4}s linear infinite`;

            if(animName === 'floatUp') {
                particle.style.left = Math.random() * 95 + 'vw';
            } else {
                particle.style.top = Math.random() * 90 + 'vh';
            }

            document.getElementById('particle-field').appendChild(particle);

            setTimeout(() => { particle.remove(); }, 5000);
        }

        // Background Continuous Spawner for Current Page Items
        setInterval(() => {
            const currentList = pageItems[currentPage] || pageItems[1];
            createParticle(currentList, 'floatUp');
        }, 300);

        // Explosion Magic Wand Function
        function triggerMagicExplosion() {
            const currentList = pageItems[currentPage] || pageItems[1];
            for(let i = 0; i < 20; i++) {
                setTimeout(() => createParticle(currentList, 'floatUp'), i * 50);
                setTimeout(() => createParticle(currentList, 'floatSide'), i * 60);
            }
        }
    </script>
</body>
</html>
