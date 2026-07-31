<!DOCTYPE html>
<html lang="ur">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Cute Dil ❤️</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 99%, #feada6 100%);
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            color: #4a4a4a;
        }

        .card {
            background: rgba(255, 255, 255, 0.85);
            padding: 40px;
            border-radius: 25px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.15);
            text-align: center;
            max-width: 450px;
            width: 90%;
            backdrop-filter: blur(10px);
            animation: fadeIn 0.8s ease-in-out;
            position: relative;
            z-index: 10;
        }

        h1 {
            color: #d63384;
            margin-bottom: 15px;
            font-size: 2rem;
        }

        p {
            font-size: 1.2rem;
            margin-bottom: 25px;
            line-height: 1.5;
        }

        .btn-container {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        button {
            background: linear-gradient(45deg, #ff758c, #ff7eb3);
            border: none;
            padding: 12px 25px;
            color: white;
            font-size: 1.1rem;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(255, 117, 140, 0.4);
        }

        button:hover {
            transform: translateY(-3px) scale(1.03);
            box-shadow: 0 6px 20px rgba(255, 117, 140, 0.6);
        }

        .hidden {
            display: none;
        }

        /* Floating Flowers Effect */
        .flower {
            position: absolute;
            font-size: 24px;
            animation: float 4s linear infinite;
            z-index: 1;
        }

        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.9); }
            to { opacity: 1; transform: scale(1); }
        }
    </style>
</head>
<body>

    <!-- Floating Background Flowers -->
    <div id="flower-field"></div>

    <!-- Page 1: Welcome -->
    <div id="page1" class="card">
        <h1>Hey Dil! 🌸</h1>
        <p>Aap naraz ho na mujhse? Aise gussa achha nahi lagta... Ek choti si baat sunoge?</p>
        <button onclick="goToPage(2)">Haan, Suno! ✨</button>
    </div>

    <!-- Page 2: Interactive Options -->
    <div id="page2" class="card hidden">
        <h1>Suno Na Dil... 🥺</h1>
        <p>Aapko pata hai na aap mere liye kitne special ho? Ab gussa khatam bhi kar do na!</p>
        <div class="btn-container">
            <button onclick="goToPage(3, 'Maan Gaya! ❤️')">Chalo Maan Gaya! 🥰</button>
            <button onclick="goToPage(3, 'Thoda Aur Patao! 😉')">Pehle Thoda Aur Patao! 😜</button>
            <button onclick="goToPage(3, 'Khabardar Phir Se Gussa Kiya To!')">Aage Se Aisa Mat Karna! 💖</button>
        </div>
    </div>

    <!-- Page 3: Final Magical Celebration -->
    <div id="page3" class="card hidden">
        <h1 id="final-title">Yayyyy! 🎉</h1>
        <p id="final-message">Thank you Dil! Aapki smile sabse pyari hai. Humesha aise hi hasste raho! 🌺🌻🌸💐</p>
        <button onclick="createFlowerExplosion()">Magical Flowers Barsao! 🌸✨</button>
    </div>

    <script>
        function goToPage(pageNumber, optionText = '') {
            // Hide all pages
            document.getElementById('page1').classList.add('hidden');
            document.getElementById('page2').classList.add('hidden');
            document.getElementById('page3').classList.add('hidden');

            // Show selected page
            document.getElementById('page' + pageNumber).classList.remove('hidden');

            if(pageNumber === 3) {
                createFlowerExplosion();
            }
        }

        // Floating flowers background logic
        const flowers = ['🌸', '🌺', '🌹', '🌷', '💐', '✨', '💖'];
        function createFlower() {
            const flower = document.createElement('div');
            flower.classList.add('flower');
            flower.innerText = flowers[Math.floor(Math.random() * flowers.length)];
            flower.style.left = Math.random() * 100 + 'vw';
            flower.style.animationDuration = Math.random() * 2 + 3 + 's';
            document.getElementById('flower-field').appendChild(flower);

            setTimeout(() => {
                flower.remove();
            }, 5000);
        }

        setInterval(createFlower, 300);

        // Extra explosion on final step
        function createFlowerExplosion() {
            for(let i = 0; i < 30; i++) {
                setTimeout(createFlower, i * 50);
            }
        }
    </script>
</body>
</html>
