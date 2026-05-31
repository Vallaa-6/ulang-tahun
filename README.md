![alt text](https://github.com/Vallaa-6/ulang-tahun/blob/main/gambar/gambar_1.jpeg?raw=true)
![alt text](https://github.com/Vallaa-6/ulang-tahun/blob/main/gambar/gambar_2.jpeg?raw=true)

<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday - Premium Cake with Dense Confetti</title>
    <style>
        /* --- Reset & Background Hitam Pekat --- */
        body {
            margin: 0;
            padding: 0;
            background: #000000;
            min-height: 100vh;
            overflow-y: auto;
            overflow-x: hidden;
            display: flex;
            flex-direction: column;
            justify-content: flex-start;
            align-items: center;
            font-family: 'Courier New', Courier, monospace;
            perspective: 1500px;
            padding-bottom: 50px;
        }

        /* --- Animasi Teks Turun --- */
        .falling-text-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
            overflow: hidden;
        }

        .falling-word {
            position: absolute;
            color: #ffffff;
            font-size: 2.2rem;
            font-weight: bold;
            text-shadow: 0 0 8px #ff1493, 0 0 20px #ff69b4, 0 0 30px #ff69b4;
            letter-spacing: 5px;
            white-space: nowrap;
            opacity: 0;
            animation: fallAndFade 5s linear infinite;
        }

        .falling-word:nth-child(1) { left: 8%; animation-duration: 4.5s; animation-delay: 0s; }
        .falling-word:nth-child(2) { left: 30%; animation-duration: 6s; animation-delay: 1.5s; }
        .falling-word:nth-child(3) { left: 55%; animation-duration: 5s; animation-delay: 0.5s; }
        .falling-word:nth-child(4) { left: 78%; animation-duration: 5.5s; animation-delay: 2.2s; }
        .falling-word:nth-child(5) { left: 18%; animation-duration: 4s; animation-delay: 3s; }
        .falling-word:nth-child(6) { left: 90%; animation-duration: 6.5s; animation-delay: 1s; }

        @keyframes fallAndFade {
            0% { top: -10%; opacity: 0; transform: scale(0.8); }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { top: 110%; opacity: 0; transform: scale(1.1); }
        }

        /* --- Container Utama --- */
        .container {
            position: relative;
            z-index: 10;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            margin-top: 60px;
            width: 100%;
        }

        h1 {
            color: #fff;
            text-shadow: 0 0 10px #ff69b4, 0 0 20px #ff69b4;
            font-size: 2.2rem;
            margin-bottom: 30px;
            text-align: center;
            animation: pulse 2s infinite alternate;
        }

        /* --- Desain Kue 3 Tingkat --- */
        .cake-wrapper {
            width: 200px;
            height: 220px;
            position: relative;
            transform-style: preserve-3d;
            transform: rotateX(15deg); 
        }

        .layer {
            position: absolute;
            left: 50%;
            transform-style: preserve-3d;
            border-radius: 50%;
            box-shadow: inset 0 0 20px rgba(0,0,0,0.4), 0 10px 15px rgba(255,20,147,0.2);
            opacity: 0;
        }

        .layer::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 30px;
            background: #ffffff;
            border-radius: 50%;
            top: -15px;
            left: 0;
            box-shadow: inset 0 -3px 8px rgba(0,0,0,0.15);
        }

        .layer-bottom {
            width: 200px;
            height: 70px;
            background: #f190b7;
            bottom: 0;
            margin-left: -100px;
            animation: dropIn 1s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
            animation-delay: 0.5s;
        }

        .layer-middle {
            width: 150px;
            height: 60px;
            background: #ea639b;
            bottom: 60px;
            margin-left: -75px;
            z-index: 2;
            animation: dropIn 1s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
            animation-delay: 1.2s;
        }

        .layer-top {
            width: 100px;
            height: 50px;
            background: #d63384;
            bottom: 110px;
            margin-left: -50px;
            z-index: 3;
            animation: dropIn 1s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
            animation-delay: 1.9s;
        }

        /* --- Lilin & Api --- */
        .candle-container {
            position: absolute;
            width: 100%;
            bottom: 150px;
            left: 0;
            z-index: 10;
            transform-style: preserve-3d;
            opacity: 0;
            animation: fadeInCandle 0.8s ease-out forwards;
            animation-delay: 2.6s;
        }

        .candle {
            position: absolute;
            width: 8px;
            height: 45px;
            background: linear-gradient(to top, #e67e22, #f1c40f, #e67e22);
            left: calc(50% - 4px);
            bottom: 0;
            border-radius: 4px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.3);
        }

        .flame {
            position: absolute;
            width: 14px;
            height: 24px;
            background: radial-gradient(circle at bottom, #ffea00 20%, #ff5500 70%, transparent 100%);
            border-radius: 50% 50% 20% 20%;
            top: -26px;
            left: calc(50% - 7px);
            box-shadow: 0 0 15px #ffaa00, 0 0 30px #ff5500, 0 0 40px #ff0000;
            animation: flicker 0.12s ease-in-out infinite alternate;
            transform-origin: bottom center;
        }

        /* --- Nama --- */
        .name-tag {
            margin-top: 50px;
            color: #fff;
            font-size: 3rem;
            font-weight: bold;
            letter-spacing: 2px;
            text-shadow: 0 0 10px #e9fa00, 0 0 30px #ddff03;
            text-align: center;
            opacity: 0;
            animation: fadeInElement 1.5s ease-out forwards;
            animation-delay: 3s;
        }

        /* --- Galeri Polaroid (Ukurannya Dikunci Otomatis) --- */
        .photo-gallery {
            margin-top: 50px;
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            max-width: 600px;
            opacity: 0;
            animation: fadeInElement 1.5s ease-out forwards;
            animation-delay: 4.2s;
        }

        .polaroid {
            background: #ffffff;
            padding: 12px 12px 25px 12px;
            box-shadow: 0 15px 30px rgba(255, 105, 180, 0.2);
            border-radius: 4px;
            transform: rotate(-3deg);
            transition: transform 0.3s ease;
            width: 160px;
        }

        .polaroid:nth-child(2) { transform: rotate(4deg); }

        .polaroid:hover {
            transform: scale(1.05) rotate(0deg);
            box-shadow: 0 20px 40px rgba(0, 255, 255, 0.4);
        }

        /* Ukuran bingkai dikunci rapat di sini agar gambar pas dan proporsional */
        .polaroid img {
            width: 160px;
            height: 200px;
            object-fit: cover; 
            border: 1px solid #ddd;
            display: block;
        }

        .polaroid .caption {
            text-align: center;
            color: #333333;
            font-size: 0.9rem;
            font-weight: bold;
            margin-top: 12px;
            letter-spacing: 1px;
        }

        /* --- SISTEM LETUPAN KERTAS DENSE --- */
        .confetti-container {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
            z-index: 5;
        }

        .confetti {
            position: absolute;
            opacity: 0;
            bottom: -20px;
        }

        .confetti-left {
            left: -10px;
            animation: burstLeft 3s cubic-bezier(0.1, 0.8, 0.25, 1) infinite;
        }

        .confetti-right {
            right: -10px;
            animation: burstRight 3s cubic-bezier(0.1, 0.8, 0.25, 1) infinite;
        }

        .c1 { background: #ff1493; width: 12px; height: 12px; border-radius: 3px; }
        .c2 { background: #00ffff; width: 8px; height: 18px; border-radius: 1px; }
        .c3 { background: #ffff00; width: 14px; height: 10px; transform: rotate(15deg); }
        .c4 { background: #ff00ff; width: 10px; height: 15px; }
        .c5 { background: #39ff14; width: 11px; height: 11px; border-radius: 50%; }
        .c6 { background: #ff4500; width: 9px; height: 14px; }
        .c7 { background: #7b1fa2; width: 13px; height: 13px; transform: rotate(45deg); }

        @keyframes burstLeft {
            0% { bottom: -20px; left: -10px; opacity: 1; transform: scale(1) rotate(0deg); }
            70% { opacity: 1; }
            100% { bottom: var(--target-y, 80vh); left: var(--target-x, 45vw); opacity: 0; transform: scale(0.5) rotate(1080deg); }
        }

        @keyframes burstRight {
            0% { bottom: -20px; right: -10px; opacity: 1; transform: scale(1) rotate(0deg); }
            70% { opacity: 1; }
            100% { bottom: var(--target-y, 80vh); right: var(--target-x, 45vw); opacity: 0; transform: scale(0.5) rotate(-1080deg); }
        }

        /* Variasi Jarak Semburan */
        .l1  { --target-y: 85vh; --target-x: 35vw; animation-delay: 2.4s; animation-duration: 2.5s; }
        .l2  { --target-y: 75vh; --target-x: 20vw; animation-delay: 2.6s; animation-duration: 2.2s; }
        .l3  { --target-y: 90vh; --target-x: 50vw; animation-delay: 2.4s; animation-duration: 2.8s; }
        .l4  { --target-y: 65vh; --target-x: 40vw; animation-delay: 2.8s; animation-duration: 2.0s; }
        .l5  { --target-y: 80vh; --target-x: 15vw; animation-delay: 2.5s; animation-duration: 2.4s; }
        .l6  { --target-y: 88vh; --target-x: 48vw; animation-delay: 3.2s; animation-duration: 2.6s; }
        .l7  { --target-y: 70vh; --target-x: 30vw; animation-delay: 3.5s; animation-duration: 2.1s; }
        .l8  { --target-y: 92vh; --target-x: 55vw; animation-delay: 4.0s; animation-duration: 2.9s; }
        .l9  { --target-y: 78vh; --target-x: 25vw; animation-delay: 4.2s; animation-duration: 2.3s; }
        .l10 { --target-y: 83vh; --target-x: 42vw; animation-delay: 4.5s; animation-duration: 2.5s; }

        .r1  { --target-y: 85vh; --target-x: 35vw; animation-delay: 2.4s; animation-duration: 2.5s; }
        .r2  { --target-y: 75vh; --target-x: 20vw; animation-delay: 2.6s; animation-duration: 2.2s; }
        .r3  { --target-y: 90vh; --target-x: 50vw; animation-delay: 2.4s; animation-duration: 2.8s; }
        .r4  { --target-y: 65vh; --target-x: 40vw; animation-delay: 2.8s; animation-duration: 2.0s; }
        .r5  { --target-y: 80vh; --target-x: 15vw; animation-delay: 2.5s; animation-duration: 2.4s; }
        .r6  { --target-y: 88vh; --target-x: 48vw; animation-delay: 3.2s; animation-duration: 2.6s; }
        .r7  { --target-y: 70vh; --target-x: 30vw; animation-delay: 3.5s; animation-duration: 2.1s; }
        .r8  { --target-y: 92vh; --target-x: 55vw; animation-delay: 4.0s; animation-duration: 2.9s; }
        .r9  { --target-y: 78vh; --target-x: 25vw; animation-delay: 4.2s; animation-duration: 2.3s; }
        .r10 { --target-y: 83vh; --target-x: 42vw; animation-delay: 4.5s; animation-duration: 2.5s; }

        @keyframes dropIn {
            0% { transform: translateY(-200px) scale(0.3); opacity: 0; }
            70% { transform: translateY(10px) scale(1.05); opacity: 1; }
            100% { transform: translateY(0) scale(1); opacity: 1; }
        }

        @keyframes fadeInCandle {
            0% { transform: scale(0); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }

        @keyframes fadeInElement {
            0% { transform: translateY(20px); opacity: 0; }
            100% { transform: translateY(0); opacity: 1; }
        }

        @keyframes flicker {
            0% { transform: scale(1) rotate(-3deg); opacity: 0.85; }
            100% { transform: scale(1.15) rotate(3deg) translateY(-1px); opacity: 1; }
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            100% { transform: scale(1.03); }
        }
    </style>
</head>
<body>

    <div class="falling-text-container">
        <div class="falling-word">MABA UI</div>
        <div class="falling-word">MABA UI</div>
        <div class="falling-word">MABA UI</div>
        <div class="falling-word">MABA UI</div>
        <div class="falling-word">MABA UI</div>
        <div class="falling-word">MABA UI</div>
    </div>

    <div class="confetti-container">
        <div class="confetti confetti-left c1 l1"></div>
        <div class="confetti confetti-left c2 l2"></div>
        <div class="confetti confetti-left c3 l3"></div>
        <div class="confetti confetti-left c4 l4"></div>
        <div class="confetti confetti-left c5 l5"></div>
        <div class="confetti confetti-left c6 l6"></div>
        <div class="confetti confetti-left c7 l7"></div>
        <div class="confetti confetti-left c1 l8"></div>
        <div class="confetti confetti-left c3 l9"></div>
        <div class="confetti confetti-left c5 l10"></div>

        <div class="confetti confetti-right c3 r1"></div>
        <div class="confetti confetti-right c1 r2"></div>
        <div class="confetti confetti-right c5 r3"></div>
        <div class="confetti confetti-right c2 r4"></div>
        <div class="confetti confetti-right c4 r5"></div>
        <div class="confetti confetti-right c7 r6"></div>
        <div class="confetti confetti-right c6 r7"></div>
        <div class="confetti confetti-right c2 r8"></div>
    </div>

    <div class="container">
        <h1>Selamat Ulang Tahun! ✨
         <div>(02-06-2026)</div wight="16px">
        </h1>

        <div class="cake-wrapper">
            <div class="layer layer-bottom"></div>
            <div class="layer layer-middle"></div>
            <div class="layer layer-top"></div>
            <div class="candle-container">
                <div class="candle"><div class="flame"></div></div>
            </div>
        </div>

        <div class="name-tag">Denisa Alfia Rahma</div>

        <div class="photo-gallery">
            <div class="polaroid">
                <img src="gambar/gambar_2.jpeg" alt="Foto Polaroid 1">
                <div class="caption">✨ Semangat MABA UI Kriminologi</div>
            </div>
            <div class="polaroid">
                <img src="gambar/gambar_1.jpeg" alt="Foto Polaroid 2">
                <div class="caption">🤍 From me to you</div>
            </div>
        </div>
    </div>
</body>
</html>
