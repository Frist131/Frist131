<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hacker Portfolio</title>
    <!-- Import Font -->
    <link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@400;500;600;700&display=swap" rel="stylesheet">
    <!-- Import Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --bg-color: #030812;
            --main-blue: #0055ff;
            --neon-blue: #00f0ff;
            --neon-green: #00ff88;
            --neon-yellow: #ffcc00;
            --neon-red: #ff0033;
            --neon-purple: #b000ff;
            --text-main: #e0e0e0;
            --text-dim: #8b9bb4;
        }

   {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: #000;
            font-family: 'Rajdhani', sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 20px;
        }

        /* KOTAK UTAMA */
        .container {
            width: 100%;
            max-width: 800px;
            background-color: var(--bg-color);
            border: 2px solid var(--main-blue);
            border-radius: 15px;
            box-shadow: 0 0 20px rgba(0, 85, 255, 0.5), inset 0 0 20px rgba(0, 85, 255, 0.2);
            padding: 20px;
            position: relative;
            overflow: hidden;
        }

        /* CUSTOM BANNER (GANTI GAMBAR DI SINI) */
        .custom-banner {
            width: 100%;
            height: auto;
            border: 1px solid var(--main-blue);
            border-radius: 10px;
            margin-bottom: 20px;
            display: block;
            box-shadow: 0 0 10px rgba(0, 85, 255, 0.3);
            object-fit: cover;
        }

        /* TERMINAL BAR */
        .terminal-bar {
            display: flex;
            align-items: center;
            background: #09101e;
            border: 1px solid #1a2d4f;
            border-radius: 8px;
            padding: 10px 15px;
            margin-bottom: 25px;
            font-family: monospace;
        }

        .dots {
            display: flex;
            gap: 6px;
            margin-right: 15px;
        }

        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
        }
        .dot.red { background: #ff5f56; }
        .dot.yellow { background: #ffbd2e; }
        .dot.green { background: #27c93f; }

        .terminal-input {
            color: var(--neon-green);
            font-size: 16px;
            font-weight: bold;
        }

        .cursor {
            display: inline-block;
            width: 8px;
            height: 15px;
            background: var(--neon-green);
            animation: blink 1s step-end infinite;
        }
        @keyframes blink { 50% { opacity: 0; } }

        .sound-wave {
            margin-left: auto;
            display: flex;
            gap: 3px;
            align-items: flex-end;
            height: 15px;
        }
        .bar {
            width: 3px;
            background: var(--main-blue);
            animation: bounce 1s ease-in-out infinite alternate;
        }
        .bar:nth-child(1) { height: 50%; animation-delay: 0.1s; }
        .bar:nth-child(2) { height: 100%; animation-delay: 0.2s; }
        .bar:nth-child(3) { height: 70%; animation-delay: 0.3s; }
        .bar:nth-child(4) { height: 40%; animation-delay: 0.4s; }
        .bar:nth-child(5) { height: 90%; animation-delay: 0.5s; }
        .bar:nth-child(6) { height: 60%; animation-delay: 0.6s; }
        @keyframes bounce { 100% { height: 20%; } }

        /* SECTION TITLE */
        .section-title {
            color: #fff;
            font-size: 18px;
            font-weight: 600;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .section-title i { color: var(--neon-blue); }

        /* DESKRIPSI */
        .desc-section {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            gap: 20px;
        }

        .desc-text {
            flex: 1;
            color: var(--text-main);
            font-size: 15px;
            line-height: 1.6;
        }
        .desc-text span { color: var(--neon-blue); font-weight: 600; }

        /* KOTAK GAMBAR CUSTOM KANAN (SHIELD) */
        .desc-image {
            width: 250px;
            height: 140px;
            border: 2px dashed var(--main-blue);
            border-radius: 10px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: var(--text-dim);
            font-size: 14px;
            overflow: hidden; /* Biar gambar gak keluar kotak */
        }
        .desc-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        /* KEAHLIAN & TOOLS GRID */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 12px;
            margin-bottom: 30px;
        }

        .skill-item {
            display: flex;
            align-items: center;
            gap: 10px;
            padding: 8px 15px;
            border-radius: 20px;
            font-size: 14px;
            font-weight: 500;
            border: 1px solid;
            background: rgba(255, 255, 255, 0.02);
            transition: 0.3s;
        }

        .skill-item i { font-size: 16px; }

        /* Warna Spesifik Skill */
        .s-blue { border-color: var(--neon-blue); color: var(--neon-blue); box-shadow: 0 0 8px rgba(0, 240, 255, 0.2); }
        .s-yellow { border-color: var(--neon-yellow); color: var(--neon-yellow); box-shadow: 0 0 8px rgba(255, 204, 0, 0.2); }
        .s-green { border-color: var(--neon-green); color: var(--neon-green); box-shadow: 0 0 8px rgba(0, 255, 136, 0.2); }
        .s-purple { border-color: var(--neon-purple); color: var(--neon-purple); box-shadow: 0 0 8px rgba(176, 0, 255, 0.2); }
        .s-red { border-color: var(--neon-red); color: var(--neon-red); box-shadow: 0 0 8px rgba(255, 0, 51, 0.2); }

        /* CERTIFICATIONS (GANTI GAMBAR DI SINI) */
        .certs-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-bottom: 30px;
        }

        .cert-img {
            width: 100%;
            height: auto;
            border-radius: 10px;
            border: 2px solid;
            display: block;
            object-fit: cover;
        }

        .cert-thm-img { border-color: var(--neon-blue); box-shadow: 0 0 10px rgba(0, 240, 255, 0.2); }
        .cert-htb-img { border-color: var(--neon-green); box-shadow: 0 0 10px rgba(0, 255, 136, 0.2); }

        /* QUOTE */
        .quote-box {
            border: 1px solid var(--main-blue);
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            margin-bottom: 30px;
            background: rgba(0, 85, 255, 0.05);
        }
        .quote-box p {
            color: #fff;
            font-style: italic;
            font-size: 16px;
            margin-bottom: 10px;
        }
        .quote-box span {
            color: var(--main-blue);
            font-size: 14px;
        }
        .quote-icon {
            color: var(--neon-blue);
            font-size: 20px;
            margin-right: 10px;
        }

        /* PACMAN ROW */
        .pacman-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border: 1px solid #1a2d4f;
            border-radius: 10px;
            padding: 10px 20px;
            margin-bottom: 30px;
            background: #050a14;
        }
        .pacman-row span { font-size: 20px; }
        .dot-line { color: #ffcc00; font-size: 10px; letter-spacing: 5px;}

        /* SOCIAL MEDIA */
        .social-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
        }
        
        .social-btn {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            padding: 12px;
            border: 1px solid var(--main-blue);
            border-radius: 25px;
            color: #fff;
            text-decoration: none;
            font-weight: 500;
            background: rgba(0, 85, 255, 0.1);
            transition: 0.3s;
        }
        .social-btn:hover { background: var(--main-blue); box-shadow: 0 0 15px var(--main-blue); }
        .social-btn i { font-size: 18px; }
        
        .social-btn.linkedin i { color: #0077b5; }
        .social-btn.email i { color: #fff; }
        .social-btn.twitter i { color: #fff; }
        .social-btn:hover i { color: #fff; }

    </style>
</head>
<body>

    <div class="container">
        
        <!-- 1. BANNER ATAS (Ganti LINK_GAMBAR_BANNER dengan file gambar kamu) -->
        <img src="LINK_GAMBAR_BANNER.png" alt="Custom Banner" class="custom-banner">

        <!-- Terminal Bar -->
        <div class="terminal-bar">
            <div class="dots">
                <div class="dot red"></div>
                <div class="dot yellow"></div>
                <div class="dot green"></div>
            </div>
            <div class="terminal-input">> whoami <span class="cursor"></span></div>
            <div class="sound-wave">
                <div class="bar"></div><div class="bar"></div><div class="bar"></div>
                <div class="bar"></div><div class="bar"></div><div class="bar"></div>
            </div>
        </div>

        <!-- Deskripsi -->
        <div class="section-title"><i class="fa-solid fa-desktop"></i> Deskripsi</div>
        <div class="desc-section">
            <div class="desc-text">
                Seorang <span>Pentester</span> yang tertarik pada keamanan siber, analisis kerentanan, dan eksploitasi sistem untuk membangun pertahanan lebih kuat.
            </div>
            <!-- KOTAK GAMBAR KANAN (Ganti LINK_GAMBAR_SHIELD dengan gambar custom kamu, atau biarkan kosong jika hanya teks) -->
            <div class="desc-image">
                <img src="LINK_GAMBAR_SHIELD.png" alt="Custom Gambar" onerror="this.style.display='none'; this.parentElement.innerHTML='<i class=\'fa-solid fa-shield-halved\' style=\'font-size:40px;color:var(--neon-blue);margin-bottom:10px;text-shadow:0 0 10px var(--neon-blue);\'></i><span>Gambar custom</span>';">
            </div>
        </div>

        <!-- Keahlian Pentest -->
        <div class="section-title"><i class="fa-solid fa-shield-virus"></i> Keahlian Pentest</div>
        <div class="skills-grid">
            <div class="skill-item s-blue"><i class="fa-solid fa-magnifying-glass"></i> Reconnaissance</div>
            <div class="skill-item s-yellow"><i class="fa-solid fa-bug"></i> Vulnerability Assessment</div>
            <div class="skill-item s-green"><i class="fa-solid fa-terminal"></i> Exploitation</div>
            <div class="skill-item s-blue"><i class="fa-solid fa-box-open"></i> Post-Exploitation</div>
            <div class="skill-item s-purple"><i class="fa-solid fa-users"></i> Red Teaming</div>
            <div class="skill-item s-red"><i class="fa-solid fa-file-lines"></i> Reporting</div>
        </div>

        <!-- Tools & Frameworks -->
        <div class="section-title"><i class="fa-solid fa-screwdriver-wrench"></i> Tools & Frameworks</div>
        <div class="skills-grid">
            <div class="skill-item s-blue"><i class="fa-solid fa-dragon"></i> Kali Linux</div>
            <div class="skill-item s-blue"><i class="fa-solid fa-m"></i> Metasploit</div>
            <div class="skill-item s-green"><i class="fa-solid fa-eye"></i> Nmap</div>
            <div class="skill-item s-red"><i class="fa-solid fa-bolt"></i> Burp Suite</div>
            <div class="skill-item s-blue"><i class="fa-solid fa-water"></i> Wireshark</div>
            <div class="skill-item s-green"><i class="fa-solid fa-certificate"></i> Nessus</div>
            <div class="skill-item s-red"><i class="fa-solid fa-hat-cowboy"></i> John the Ripper</div>
            <div class="skill-item s-purple"><i class="fa-solid fa-ellipsis"></i> Others...</div>
        </div>

        <!-- Certifications & Achievements -->
        <div class="section-title"><i class="fa-solid fa-trophy"></i> Certifications & Achievements</div>
        <div class="certs-grid">
            <!-- 2. GAMBAR SERTIFIKAT THM (Ganti LINK_GAMBAR_THM dengan file gambar kamu) -->
            <img src="LINK_GAMBAR_THM.png" alt="TryHackMe Certificate" class="cert-img cert-thm-img">
            
            <!-- 3. GAMBAR SERTIFIKAT HTB (Ganti LINK_GAMBAR_HTB dengan file gambar kamu) -->
            <img src="LINK_GAMBAR_HTB.png" alt="HackTheBox Certificate" class="cert-img cert-htb-img">
        </div>

        <!-- Quote -->
        <div class="quote-box">
            <p><i class="fa-solid fa-quote-left quote-icon"></i>"Keamanan bukan tentang siapa yang paling kuat, tapi siapa yang paling siap."</p>
            <span>— Anonymous</span>
        </div>

        <!-- Pacman Row -->
        <div class="pacman-row">
            <span>🟡</span>
            <span class="dot-line">. . . . . .</span>
            <span>👻</span>
            <span class="dot-line">.</span>
            <span>👻</span>
            <span class="dot-line">.</span>
            <span>👻</span>
            <span class="dot-line">.</span>
            <span>👻</span>
            <span class="dot-line">. .</span>
            <span>🍒</span>
        </div>

        <!-- Social Media -->
        <div class="section-title"><i class="fa-solid fa-share-nodes"></i> Sosial media</div>
        <div class="social-grid">
            <a href="#" class="social-btn linkedin"><i class="fa-brands fa-linkedin"></i> LinkedIn</a>
            <a href="#" class="social-btn email"><i class="fa-solid fa-envelope"></i> Email</a>
            <a href="#" class="social-btn twitter"><i class="fa-brands fa-x-twitter"></i> Twitter/X</a>
        </div>

    </div>

</body>
</html>
