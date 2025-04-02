# HappyAnniversary
for my love 
<!DOCTYPE html>
<html lang="th">
<head>
    <title>For My Love</title>
    <meta charset="UTF-8">
    <style>
        body {
            margin: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background: #ffe6e6;
            font-family: 'Kanit', sans-serif;
        }

        .heart-container {
            position: relative;
            width: 200px;
            height: 200px;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .heart {
            position: absolute;
            width: 100px;
            height: 100px;
            background: #ff4444;
            transform: rotate(45deg);
            top: 50px;
            left: 50px;
            animation: pulse 1.5s infinite;
            box-shadow: 0 0 30px rgba(255,68,68,0.3);
        }

        .heart:before,
        .heart:after {
            content: '';
            position: absolute;
            width: 100px;
            height: 100px;
            background: #ff4444;
            border-radius: 50%;
        }

        .heart:before {
            left: -50px;
        }

        .heart:after {
            top: -50px;
        }

        @keyframes pulse {
            0% { transform: rotate(45deg) scale(1); }
            50% { transform: rotate(45deg) scale(1.1); }
            100% { transform: rotate(45deg) scale(1); }
        }

        .card {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) scale(0);
            width: 800px;
            background: white;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 0 50px rgba(0,0,0,0.2);
            opacity: 0;
            transition: all 0.5s;
            z-index: 1000;
        }

        .card.show {
            transform: translate(-50%, -50%) scale(1);
            opacity: 1;
        }

        .message {
            text-align: center;
            line-height: 2;
            font-size: 24px;
        }

        .title {
            font-size: 40px;
            color: #ff4444;
            margin-bottom: 30px;
        }

        .close-btn {
            position: absolute;
            top: 20px;
            right: 20px;
            font-size: 24px;
            cursor: pointer;
            color: #ff4444;
        }

        .music-control {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: rgba(255, 255, 255, 0.9);
            padding: 15px;
            border-radius: 50%;
            cursor: pointer;
            z-index: 1000;
            box-shadow: 0 0 20px rgba(0,0,0,0.2);
        }

        .music-control img {
            width: 40px;
            height: 40px;
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400&display=swap" rel="stylesheet">
</head>
<body>
    <audio id="bgMusic" loop preload="auto">
        <source src="./still-love-you.mp3" type="audio/mpeg">
    </audio>

    <div class="music-control" onclick="toggleMusic()">
        <img src="https://cdn-icons-png.flaticon.com/512/7960/7960604.png" alt="music control" id="musicIcon">
    </div>

    <div class="heart-container" onclick="showCard()">
        <div class="heart"></div>
    </div>

    <div class="card" id="card">
        <div class="close-btn" onclick="hideCard()">×</div>
        <div class="message">
            <div class="title">Happy Anniversary</div>
            <p>For my Love ♥️</p>
            <p>สุขสันต์วันครบรอบ 7 เดือน ครับเบบี๋</p>
            <p>เค้าอยากขอบคุณและขอโทษบี๋ ที่บางครั้งเค้าทำตัวไม่น่ารักกับบี๋เลย</p>
            <p>แต่บี๋ไม่เคยโกรธ เค้าเลยสักครั้ง</p>
            <p>เค้ารักเบบี๋มากๆเลย เค้ารักที่สุด</p>
            <p>เค้าขอบคุณที่บี๋ไม่ทิ้งเค้านะ</p>
            <p>เค้ารักเธอที่สุด</p>
            <p>จุ๊บๆ 💕</p>
        </div>
    </div>

    <script>
        let isPlaying = false;
        const music = document.getElementById('bgMusic');
        const musicIcon = document.getElementById('musicIcon');
        const card = document.getElementById('card');

        function toggleMusic() {
            try {
                if (isPlaying) {
                    music.pause();
                } else {
                    music.play();
                }
                isPlaying = !isPlaying;
            } catch (e) {
                console.log("Error playing audio:", e);
            }
        }

        function showCard() {
            card.classList.add('show');
            if (!isPlaying) {
                toggleMusic();
            }
        }

        function hideCard() {
            card.classList.remove('show');
        }
    </script>
</body>
</html>
