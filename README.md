<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Selamat Ulang Tahun Tergemas!</title>
    <link href="https://fonts.googleapis.com/css2?family=Indie+Flower&family=Pacifico&family=Cute+Font&display=swap" rel="stylesheet">
    <style>
        /* Variabel Warna untuk Kemudahan Modifikasi */
        :root {
            --soft-pink: #FFEDF3; /* Background utama */
            --light-pink: #FFDDEE; /* Background container */
            --dark-pink: #FF69B4; /* Aksen pink, tombol */
            --berry-pink: #D44287; /* Teks judul */
            --muted-red: #A52A2A; /* Teks paragraf */
            --white-translucent: rgba(255, 255, 255, 0.9);
            --shadow-color: rgba(255, 105, 180, 0.4);
            --heart-particle-color: #FF69B4; /* Warna hati yang bertebaran */
        }

        body {
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background-color: var(--soft-pink);
            font-family: 'Indie Flower', cursive;
            color: var(--muted-red);
            text-align: center;
            overflow: hidden;
            position: relative;
        }

        .container {
            width: 90vmin;
            max-width: 450px;
            background-color: var(--light-pink);
            padding: 30px;
            border-radius: 40px;
            box-shadow: 0 15px 40px var(--shadow-color);
            box-sizing: border-box;
            aspect-ratio: 9 / 16;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            align-items: center;
            position: relative;
            z-index: 1;
            overflow: hidden;
            animation: fadeIn 1.5s ease-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        h1 {
            font-family: 'Pacifico', cursive;
            color: var(--berry-pink);
            font-size: 3em;
            margin-bottom: 15px;
            text-shadow: 3px 3px 6px rgba(0,0,0,0.1);
            line-height: 1.2;
        }

        p {
            font-size: 1.3em;
            line-height: 1.6;
            margin-bottom: 25px;
            padding: 0 10px;
        }

        /* Dekorasi Emoji Background */
        .emoji-decoration {
            position: absolute;
            font-size: 3.5em;
            opacity: 0.5;
            animation: float 6s infinite ease-in-out alternate;
            filter: drop-shadow(0 0 5px rgba(255,255,255,0.7));
            z-index: 0;
        }

        /* Posisi emoji random agar aesthetic */
        .emoji-1 { top: 8%; left: 12%; animation-delay: 0s; transform: rotate(-5deg); }
        .emoji-2 { top: 22%; right: 8%; animation-delay: 1.2s; transform: rotate(10deg); }
        .emoji-3 { bottom: 10%; left: 18%; animation-delay: 2.5s; transform: rotate(3deg); }
        .emoji-4 { top: 3%; right: 25%; animation-delay: 0.7s; transform: rotate(-15deg); }
        .emoji-5 { bottom: 3%; right: 10%; animation-delay: 1.8s; }
        .emoji-6 { top: 35%; left: 4%; animation-delay: 3s; transform: rotate(20deg); }
        .emoji-7 { bottom: 25%; right: 4%; animation-delay: 0.3s; transform: rotate(-8deg); }
        .emoji-8 { top: 50%; left: 25%; animation-delay: 4s; transform: rotate(12deg); }
        .emoji-9 { bottom: 40%; right: 25%; animation-delay: 3.5s; transform: rotate(-20deg); }

        @keyframes float {
            0% { transform: translateY(0px) rotate(var(--initial-rotate, 0deg)); }
            50% { transform: translateY(-15px) rotate(calc(var(--initial-rotate, 0deg) + 5deg)); }
            100% { transform: translateY(0px) rotate(var(--initial-rotate, 0deg)); }
        }

        /* Tombol Lucu */
        .cute-button {
            background-color: var(--dark-pink);
            color: white;
            padding: 15px 30px;
            border: none;
            border-radius: 40px;
            font-size: 1.3em;
            font-family: 'Indie Flower', cursive;
            cursor: pointer;
            transition: transform 0.2s ease-in-out, background-color 0.2s, box-shadow 0.2s;
            box-shadow: 0 8px 20px var(--shadow-color);
            position: relative;
            overflow: hidden;
            z-index: 2;
        }

        .cute-button:hover {
            background-color: var(--berry-pink);
            transform: scale(1.08) rotate(2deg);
            box-shadow: 0 10px 25px rgba(255, 105, 180, 0.7);
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            z-index: 10;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.7);
            justify-content: center;
            align-items: center;
            overflow: hidden;
            backdrop-filter: blur(5px);
        }

        .modal-content {
            background-color: var(--white-translucent);
            padding: 35px;
            border-radius: 30px;
            width: 85%;
            max-width: 550px;
            text-align: center;
            box-shadow: 0 0 50px var(--shadow-color);
            position: relative;
            z-index: 11;
            transform: scale(0.8);
            animation: modalPopIn 0.3s cubic-bezier(0.68, -0.55, 0.27, 1.55) forwards;
        }

        @keyframes modalPopIn {
            from { transform: scale(0.8); opacity: 0; }
            to { transform: scale(1); opacity: 1; }
        }

        .close-button {
            color: var(--dark-pink);
            position: absolute;
            top: 15px;
            right: 20px;
            font-size: 35px;
            font-weight: bold;
            cursor: pointer;
            transition: transform 0.2s ease-in-out;
        }

        .close-button:hover,
        .close-button:focus {
            color: var(--berry-pink);
            transform: rotate(90deg);
        }

        /* Animasi Ledakan Hati (saat tombol ditekan) */
        .heart-particle {
            position: absolute;
            font-size: 1.8em;
            opacity: 0;
            animation: heartExplode 1.2s forwards;
            pointer-events: none;
            z-index: 5;
            text-shadow: 0 0 5px rgba(255,255,255,0.8);
        }

        @keyframes heartExplode {
            0% {
                transform: translate(0, 0) scale(0);
                opacity: 1;
            }
            20% {
                opacity: 1;
            }
            100% {
                transform: translate(var(--x), var(--y)) scale(2);
                opacity: 0;
            }
        }

        /* Animasi Kue Meledak */
        .cake-explosion {
            position: fixed;
            font-size: 7em;
            z-index: 12;
            pointer-events: none;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            filter: drop-shadow(0 0 15px rgba(255,255,255,0.9));
            animation: jumpAndExplode 2s cubic-bezier(0.68, -0.55, 0.27, 1.55) forwards; /* Cubic-bezier untuk efek pantulan */
        }

        @keyframes jumpAndExplode {
            0% {
                transform: translate(-50%, 150px) scale(0.2); /* Mulai jauh di bawah, kecil */
                opacity: 0;
            }
            30% {
                transform: translate(-50%, -80px) scale(1.5); /* Lompat tinggi, membesar cepat */
                opacity: 1;
            }
            60% {
                transform: translate(-50%, -10px) scale(1.8); /* Turun sedikit, lebih besar */
                opacity: 1;
            }
            80% {
                transform: translate(-50%, -150px) scale(2); /* Lompat lagi, puncak ledakan */
                opacity: 1;
                filter: blur(0px); /* Hapus blur sementara */
            }
            100% {
                transform: translate(-50%, -400px) scale(0.5) rotate(720deg); /* Meledak ke atas, mengecil, berputar */
                opacity: 0;
                filter: blur(10px); /* Blur kuat */
            }
        }

        /* Animasi Hati Bertebaran Menutupi Layar */
        .full-page-heart {
            position: fixed;
            font-size: 2em; /* Ukuran hati */
            opacity: 0;
            animation: floatAndFade 3s ease-out forwards; /* Animasi mengambang dan memudar */
            pointer-events: none;
            z-index: 100; /* Pastikan di atas semua */
            color: var(--heart-particle-color); /* Warna pink untuk hati */
            text-shadow: 0 0 3px rgba(255,255,255,0.7);
        }

        @keyframes floatAndFade {
            0% {
                transform: translate(0, 0) scale(0.5) rotate(var(--rotate-start, 0deg));
                opacity: 0.8;
            }
            100% {
                transform: translate(var(--endX), var(--endY)) scale(1.5) rotate(var(--rotate-end, 360deg));
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <div class="emoji-decoration emoji-1" style="--initial-rotate: -5deg;">💖</div>
    <div class="emoji-decoration emoji-2" style="--initial-rotate: 10deg;">✨</div>
    <div class="emoji-decoration emoji-3" style="--initial-rotate: 3deg;">😊</div>
    <div class="emoji-decoration emoji-4" style="--initial-rotate: -15deg;">❤️</div>
    <div class="emoji-decoration emoji-5" style="--initial-rotate: 0deg;">🌟</div>
    <div class="emoji-decoration emoji-6" style="--initial-rotate: 20deg;">🥳</div>
    <div class="emoji-decoration emoji-7" style="--initial-rotate: -8deg;">🥰</div>
    <div class="emoji-decoration emoji-8" style="--initial-rotate: 12deg;">💕</div>
    <div class="emoji-decoration emoji-9" style="--initial-rotate: -20deg;">🎀</div>

    <div class="container">
        <h1>🎉 Happy Birthday, Sayangku! 🎉</h1>
        <p>
            Di hari spesialmu ini, aku berharap semua impianmu menjadi kenyataan.
            Kamu adalah hadiah terindah dalam hidupku. Terima kasih sudah selalu ada!
            Semoga harimu penuh kebahagiaan, tawa, dan semua yang kamu inginkan.
            Aku sayang kamu banget! ❤️
        </p>
        <button id="openModalBtn" class="cute-button">💌 Buka Pesan Rahasia! 🤫</button>
    </div>

    <div id="secretModal" class="modal">
        <div class="modal-content">
            <span class="close-button" onclick="closeModal()">&times;</span>
            <h2>Untuk Kamu, Bidadariku...</h2>
            <p>
                Setiap detik bersamamu adalah anugerah. Kamu membuat duniaku lebih berwarna dan ceria.
                Akuu akann berusaha selalu membuatmu tersenyum dan mencintaimu sepenuh hatiku, hari ini dan selamanya.
                Kamu adalah ratu di hatiku! Selamat ulang tahun lagi, my loveee! duniaa kuu muachh muachh kuu 😘
            </p>
            <p>Dengan semua cintaku,</p>
            <p><strong>[DARI FERNANDES ORANG SPESIAL]</strong></p>
        </div>
    </div>

    <script>
        document.getElementById('openModalBtn').addEventListener('click', function() {
            openModal();
            createHeartExplosion(this);
        });

        function openModal() {
            document.getElementById('secretModal').style.display = 'flex';
        }

        function closeModal() {
            document.getElementById('secretModal').style.display = 'none';
            createCakeExplosion();
            createFullPageHearts(); // Panggil fungsi untuk hati bertebaran
        }

        function createHeartExplosion(button) {
            const numHearts = 25;
            const buttonRect = button.getBoundingClientRect();
            const containerRect = document.querySelector('.container').getBoundingClientRect();

            for (let i = 0; i < numHearts; i++) {
                const heart = document.createElement('div');
                heart.className = 'heart-particle';
                heart.innerHTML = '💖';

                const startX = (buttonRect.left + buttonRect.right) / 2 - containerRect.left;
                const startY = (buttonRect.top + buttonRect.bottom) / 2 - containerRect.top;

                heart.style.left = `${startX}px`;
                heart.style.top = `${startY}px`;

                const endX = (Math.random() - 0.5) * 300;
                const endY = (Math.random() - 0.5) * 300;

                heart.style.setProperty('--x', `${endX}px`);
                heart.style.setProperty('--y', `${endY}px`);

                document.querySelector('.container').appendChild(heart);

                heart.addEventListener('animationend', () => {
                    heart.remove();
                });
            }
        }

        function createCakeExplosion() {
            const cake = document.createElement('div');
            cake.className = 'cake-explosion';
            cake.innerHTML = '🎂';
            document.body.appendChild(cake);

            cake.addEventListener('animationend', () => {
                cake.remove();
            });
        }

        // Fungsi baru untuk hati bertebaran memenuhi layar
        function createFullPageHearts() {
            const numHearts = 50; // Jumlah hati yang bertebaran
            for (let i = 0; i < numHearts; i++) {
                const heart = document.createElement('div');
                heart.className = 'full-page-heart';
                heart.innerHTML = '❤️'; // Emoji hati merah
                document.body.appendChild(heart);

                // Posisi awal acak di atas atau bawah layar
                const startX = Math.random() * window.innerWidth;
                const startY = Math.random() < 0.5 ? -50 : window.innerHeight + 50; // Mulai dari atas atau bawah

                heart.style.left = `${startX}px`;
                heart.style.top = `${startY}px`;

                // Posisi akhir acak di seluruh layar
                const endX = Math.random() * window.innerWidth * 1.5 - (window.innerWidth * 0.25); // Menyebar lebih luas
                const endY = Math.random() * window.innerHeight * 1.5 - (window.innerHeight * 0.25);

                // Rotasi acak
                const rotateStart = Math.random() * 360;
                const rotateEnd = Math.random() * 720 + 360; // Berputar minimal satu kali

                heart.style.setProperty('--endX', `${endX}px`);
                heart.style.setProperty('--endY', `${endY}px`);
                heart.style.setProperty('--rotate-start', `${rotateStart}deg`);
                heart.style.setProperty('--rotate-end', `${rotateEnd}deg`);
                heart.style.animationDelay = `${Math.random() * 1.5}s`; // Delay acak untuk efek bertebaran
                heart.style.animationDuration = `${3 + Math.random() * 2}s`; // Durasi acak

                heart.addEventListener('animationend', () => {
                    heart.remove();
                });
            }
        }
    </script>
</body>
</html>
