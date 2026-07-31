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
            background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 50%, #a1c4fd 100%);
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            color: #4a4a4a;
        }

        /* Card Container with Zoom In/Out Base Styles */
        .card {
            background: rgba(255, 255, 255, 0.88);
            padding: 35px 25px;
            border-radius: 25px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
            text-align: center;
            max-width: 420px;
            width: 90%;
            backdrop-filter: blur(12px);
            position: relative;
            z-index: 10;
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        /* Zoom-In & Zoom-Out Animation Classes */
        .zoom-in {
            animation: zoomIn 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
        }

        .zoom-out {
            animation: zoomOut 0.5s ease forwards;
        }

        @keyframes zoomIn {
            0% { opacity: 0; transform: scale(0.3) rotate(-5deg); }
            100% { opacity: 1; transform: scale(1) rotate(0deg); }
        }

        @keyframes zoomOut {
            0% { opacity: 1; transform: scale(1); }
            100% { opacity: 0; transform: scale(1.5); }
        }

        h1 {
            color: #d63384;
            margin-bottom: 15px;
            font-size: 1.8rem;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        p {
            font-size: 1.1rem;
            margin-bottom: 20px;
            line-height: 1.6;
            color: #555;
        }

        .btn-container {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

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
            background: linear-gradient(45deg, #ff7eb3, #ff758c);
        }

        .hidden {
            display: none !important;
        }

        /* Floating Magic Flowers & Emojis Background */
        .flower {
            position: absolute;
            font-size: 28px;
            user-select: none;
            pointer-events: none;
            animation: floatUp 4s linear infinite;
            z-index: 1;
        }

        @keyframes floatUp {
            0% { transform: translateY(105vh) rotate(0deg) scale(0.8); opacity: 1; }
            100% { transform: translateY(-10vh) rotate(360deg) scale(1.2); opacity: 0; }
        }

        /* Envelope / Letter Styling for Page 1 */
        .envelope {
            font-size: 80px;
            cursor: pointer;
            transition: transform 0.4s ease;
            display: inline-block;
            margin-bottom: 15px;
        }

        .envelope:hover {
            transform: scale(1.2) rotate(10deg);
        }

        /* Special Floating Magic Wand Button */
        .magic-btn {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #fff;
            border-radius: 50%;
            width: 55px;
            height: 55px;
            font-size: 25px;
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
<body>

    <!-- Floating Background Particles -->
    <div id="flower-field"></div>

    <!-- Magic Wand Button (Creates Instant Flower Boom) -->
    <div class="magic-btn" onclick="triggerMagicExplosion()" title="Click for Magic!">🪄</div>

    <!-- Page 1: Magical Envelope -->
    <div id="page1" class="card zoom-in">
        <div class="envelope" onclick="nextPage(2)">✉️</div>
        <h1>Hey Dil! 🌸</h1>
        <p>Aapke liye ek secret message hai... Is lifafe par click karke kholo na!</p>
        <button onclick="nextPage(2)">Unfold Secret Letter ✨</button>
    </div>

    <!-- Page 2: Complaint & Choice -->
    <div id="page2" class="card hidden">
        <h1>Suno Na Dil... 🥺</h1>
        <p>Mujhse galti ho gayi, par aap itna naraz rahoge to mera kya hoga? Ek choti si smile de do na!</p>
        <div class="btn-container">
            <button onclick="nextPage(3)">Acha Thoda Sa Smile Kiya! 😊</button>
            <button onclick="nextPage(3)">Abhi Bhi Thoda Gussa Hoon! 😤</button>
        </div>
    </div>

    <!-- Page 3: Interactive Bargain Page -->
    <div id="page3" class="card hidden">
        <h1>Maan Jao Na Please! 💐</h1>
        <p>Agar aap maan gaye to aapko duniya ki sabse pyari chocolates aur bohot saare phool milenge! 🍫🌸</p>
        <div class="btn-container">
            <button onclick="nextPage(4)">Chalo Maan Gaya/Gayi! 🥰</button>
            <button onclick="nextPage(4)">Khabardar Phir Se Gussa Dilaya To! 💖</button>
        </div>
    </div>

    <!-- Page 4: Final Celebration -->
    <div id="page4" class="card hidden">
        <h1>Yayyyy! Dil Maan Gaya! 🎉✨</h1>
        <p>Thank you Dil! Aapki smile se zyada pyari cheez koi nahi hai. Humesha aise hi khush raho! 🌺🌻🌸💐</p>
        <button onclick="triggerMagicExplosion()">Ghar Bhar Kar Phool Barsao! 🌸🎆</button>
    </div>

    <script>
        let currentPage = 1;

        function nextPage(targetPage) {
            const currentCard = document.getElementById('page' + currentPage);
            const nextCard = document.getElementById('page' + targetPage);

            // Apply Zoom Out to current card
            currentCard.classList.remove('zoom-in');
            currentCard.classList.add('zoom-out');

            setTimeout(() => {
                currentCard.classList.add('hidden');
                currentCard.classList.remove('zoom-out');

                // Show next card with Zoom In
                nextCard.classList.remove('hidden');
                nextCard.classList.add('zoom-in');
                currentPage = targetPage;

                // Extra flowers effect on final page
                if(targetPage === 4) {
                    triggerMagicExplosion();
                }
            }, 400);
        }

        // Floating Background Flowers Array
        const elements = ['🌸', '🌺', '🌹', '🌷', '💐', '✨', '💖', '🌼', '⭐'];

        function createFlower() {
            const flower = document.createElement('div');
            flower.classList.add('flower');
            flower.innerText = elements[Math.floor(Math.random() * elements.length)];
            flower.style.left = Math.random() * 95 + 'vw';
            flower.style.animationDuration = (Math.random() * 2 + 3) + 's';
            flower.style.fontSize = (Math.random() * 15 + 20) + 'px';
            
            document.getElementById('flower-field').appendChild(flower);

            setTimeout(() => {
                flower.remove();
            }, 5000);
        }

        // Keep continuous background flowers flow
        setInterval(createFlower, 350);

        // Magic Wand / Button Explosion Function
        function triggerMagicExplosion() {
            for(let i = 0; i < 35; i++) {
                setTimeout(createFlower, i * 40);
            }
        }
    </script>
</body>
</html>
