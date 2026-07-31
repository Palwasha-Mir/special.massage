<!DOCTYPE html>
<html lang="ur">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Cute Golumolu Dil ❤️</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #fce4ec 0%, #ffe082 50%, #b2ebf2 100%);
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            color: #4a4a4a;
        }

        /* Card Container with Upgraded Zoom In/Out */
        .card {
            background: rgba(255, 255, 255, 0.9);
            padding: 25px 20px;
            border-radius: 30px;
            box-shadow: 0 15px 35px rgba(255, 105, 180, 0.3);
            text-align: center;
            max-width: 400px;
            width: 90%;
            backdrop-filter: blur(10px);
            position: relative;
            z-index: 10;
            border: 5px solid rgba(255, 255, 255, 0.7);
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        /* Upgraded Zoom Animations */
        .zoom-in {
            animation: cartoonZoomIn 0.7s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
        }

        .zoom-out {
            animation: cartoonZoomOut 0.5s ease-in forwards;
        }

        @keyframes cartoonZoomIn {
            0% { opacity: 0; transform: scale(0.1) rotate(-15deg); }
            100% { opacity: 1; transform: scale(1) rotate(0deg); }
        }

        @keyframes cartoonZoomOut {
            0% { opacity: 1; transform: scale(1); }
            100% { opacity: 0; transform: scale(2) rotate(15deg); }
        }

        /* Bubu Dudu Character Styling */
        .character-img {
            width: 100px;
            height: auto;
            margin-bottom: 10px;
            animation: characterBounce 2s infinite ease-in-out;
        }

        @keyframes characterBounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-15px) rotate(5deg); }
        }

        h1 {
            color: #ff4081;
            margin-bottom: 10px;
            font-size: 1.6rem;
            text-shadow: 2px 2px 0px rgba(255, 255, 255, 0.8);
        }

        p {
            font-size: 1.1rem;
            margin-bottom: 20px;
            line-height: 1.5;
            color: #555;
            padding: 0 10px;
        }

        .btn-container {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        /* Bouncy Buttons */
        button {
            background: linear-gradient(45deg, #ff8a80, #ff5252);
            border: none;
            padding: 12px 20px;
            color: white;
            font-size: 1.1rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 10px rgba(255, 82, 82, 0.4);
        }

        button:hover {
            transform: scale(1.1) rotate(3deg);
            box-shadow: 0 8px 20px rgba(255, 82, 82, 0.6);
            background: linear-gradient(45deg, #ff5252, #ff8a80);
        }

        .hidden {
            display: none !important;
        }

        /* Floating Items Background (Flowers + Cute stuff) */
        .cute-item {
            position: absolute;
            user-select: none;
            pointer-events: none;
            z-index: 1;
        }

        /* Keyframes for items coming from different sides */
        @keyframes floatUp {
            0% { transform: translateY(105vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        @keyframes floatRight {
            0% { transform: translateX(-10vw) translateY(50vh) rotate(0deg); opacity: 1; }
            100% { transform: translateX(110vw) translateY(-50vh) rotate(360deg); opacity: 0; }
        }

        @keyframes floatLeft {
            0% { transform: translateX(110vw) translateY(0vh) rotate(0deg); opacity: 1; }
            100% { transform: translateX(-10vw) translateY(100vh) rotate(360deg); opacity: 0; }
        }

        /* Special Floating Magic Wand Button */
        .magic-btn {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 50%;
            width: 60px;
            height: 60px;
            font-size: 30px;
            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: 0 5px 20px rgba(255, 105, 180, 0.5);
            cursor: pointer;
            z-index: 100;
            border: 3px solid #ff4081;
            transition: transform 0.3s ease;
        }

        .magic-btn:hover {
            transform: rotate(360deg) scale(1.3);
        }
    </style>
</head>
<body>

    <!-- Floating Background Items -->
    <div id="cute-field"></div>

    <!-- Magic Wand Button (Creates Instant Chaos Boom) -->
    <div class="magic-btn" onclick="triggerMagicExplosion()" title="Bubu Chaos!">🐼</div>

    <!-- Page 1: Magical Envelope -->
    <div id="page1" class="card zoom-in">
        <img src="https://media1.tenor.com/m/7aX-f4nJ88AAAAAC/peach-goma.gif" alt="Bubu Panda" class="character-img">
        <h1>Hey Dil! 🐼🌸</h1>
        <p>Aap naraz ho na? Mujhe is cute lifafe ko click karke maaf kar do, please! ✉️🥺</p>
        <button onclick="nextPage(2)">Lifafe par Click Karo! ✨</button>
    </div>

    <!-- Page 2: Complaint & Choice -->
    <div id="page2" class="card hidden">
        <img src="https://media1.tenor.com/m/X6o2M1b1tAAAAAAC/goma-goma-thinking.gif" alt="Thinking Panda" class="character-img">
        <h1>Suno Na Mere Dudu... 🥺</h1>
        <p>Mujhse galti ho gayi! Itna cute Panda kya apko bura lag sakta hai? Ek choti si smile to de do!</p>
        <div class="btn-container">
            <button onclick="nextPage(3)">Acha Thoda Sa Smile Kiya! 😊</button>
            <button onclick="nextPage(3)">Abhi Bhi Thoda Gussa Hoon! 😤</button>
        </div>
    </div>

    <!-- Page 3: Interactive Bargain Page -->
    <div id="page3" class="card hidden">
        <img src="https://media1.tenor.com/m/49m9A8m3C4kAAAAC/goma-love.gif" alt="Angry Love Panda" class="character-img">
        <h1>Maan Jao Na Please! 💐🍫</h1>
        <p>Agar aap maan gaye to aapko duniya ki sabse pyari chocolates aur Ice-cream milegi! 🍦✨</p>
        <div class="btn-container">
            <button onclick="nextPage(4)">Chalo Maan Gaya/Gayi! 🥰</button>
            <button onclick="nextPage(4)">Ab Phir se Gussa Mat Karna! 💖</button>
        </div>
    </div>

    <!-- Page 4: Final Celebration -->
    <div id="page4" class="card hidden">
        <img src="https://media.tenor.com/w2Yv2e8254IAAAAC/happy.gif" alt="Happy Bubu Dudu" class="character-img">
        <h1>Yayyyy! Dil Maan Gaya! 🎉✨🐼</h1>
        <p>Thank you Dil! Aapki smile se zyada pyari aur gulu-molu cheez koi nahi hai. Humesha aise hi khush raho! 🌺🍨💖</p>
        <button onclick="triggerMagicExplosion()">Ghar Bhar Kar Phool-Pande Barsao! 🌸🎆</button>
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

                // Extra chaos boom on final page or bargain page
                if(targetPage === 4 || targetPage === 3) {
                    triggerMagicExplosion();
                }
            }, 500);
        }

        // Floating Background Items Arrays
        const continuousItems = ['🌸', '🌺', '🌹', '✨', '💖', '🌼', '⭐', '🐼', '🐹'];
        const explosionItems = ['🍦', '🍫', '🍩', '🐼', '🐹', '🎉', '💖', '⭐', '🌺', '🍦'];

        function createItem(itemsArray, animationName) {
            const item = document.createElement('div');
            item.classList.add('cute-item');
            item.innerText = itemsArray[Math.floor(Math.random() * itemsArray.length)];
            item.style.fontSize = (Math.random() * 20 + 30) + 'px'; // Making them big
            item.style.animation = `${animationName} ${Math.random() * 3 + 4}s linear infinite`;
            
            // Randomly starting items on different positions for chaos
            if(animationName === 'floatUp') {
                item.style.left = Math.random() * 95 + 'vw';
            } else if(animationName === 'floatRight') {
                item.style.top = Math.random() * 95 + 'vh';
            } else {
                item.style.top = Math.random() * 95 + 'vh';
            }

            document.getElementById('cute-field').appendChild(item);

            setTimeout(() => {
                item.remove();
            }, 6000); // Remove after longer time
        }

        // Keep continuous background cute items flow from UP
        setInterval(() => createItem(continuousItems, 'floatUp'), 350);

        // Magic Wand / Button Explosion Function (Chaos Boom)
        function triggerMagicExplosion() {
            // Chaos 1: Items from LEFT
            for(let i = 0; i < 15; i++) {
                setTimeout(() => createItem(explosionItems, 'floatRight'), i * 80);
            }
            // Chaos 2: Items from RIGHT
            for(let i = 0; i < 15; i++) {
                setTimeout(() => createItem(explosionItems, 'floatLeft'), i * 80 + 100);
            }
            // Chaos 3: Items from UP (Fast)
            for(let i = 0; i < 20; i++) {
                setTimeout(() => createItem(explosionItems, 'floatUp'), i * 60 + 200);
            }
        }
    </script>
</body>
</html>
