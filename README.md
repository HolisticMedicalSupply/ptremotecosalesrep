<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <meta name="theme-color" content="#0a0a0a">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <title>Holistic Medical Supply — Elite Sales Program</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:ital,wght@0,400;0,500;0,600;0,700;1,400&display=swap" rel="stylesheet">
    <style>
        :root {
            --ink: #0a0a0a;
            --paper: #fafaf8;
            --accent: #00c896;
            --accent-dark: #00a87a;
            --gold: #c9a227;
            --gold-light: #e8d47a;
            --muted: #6b6b6b;
            --divider: #e5e5e5;
            --glass: rgba(255,255,255,0.85);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
            height: -webkit-fill-available;
        }

        body {
            font-family: 'DM Sans', -apple-system, sans-serif;
            background: var(--paper);
            color: var(--ink);
            line-height: 1.6;
            overflow-x: hidden;
            min-height: 100vh;
            min-height: -webkit-fill-available;
            padding: env(safe-area-inset-top) env(safe-area-inset-right) env(safe-area-inset-bottom) env(safe-area-inset-left);
        }

        /* Noise texture overlay */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)'/%3E%3C/svg%3E");
            opacity: 0.03;
            pointer-events: none;
            z-index: 1000;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            min-height: 100dvh; /* Dynamic viewport height for mobile */
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 2rem;
            position: relative;
            background: linear-gradient(135deg, var(--ink) 0%, #1a1a2e 50%, #16213e 100%);
            overflow: hidden;
        }

        @supports (-webkit-touch-callout: none) {
            .hero {
                min-height: -webkit-fill-available;
            }
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(ellipse at 30% 20%, rgba(0, 200, 150, 0.15) 0%, transparent 50%),
                        radial-gradient(ellipse at 70% 80%, rgba(201, 162, 39, 0.1) 0%, transparent 40%);
            animation: aurora 20s ease-in-out infinite;
        }

        @keyframes aurora {
            0%, 100% { transform: translate(0, 0) rotate(0deg); }
            50% { transform: translate(-5%, 5%) rotate(5deg); }
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 900px;
        }

        .hero-badge {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.5rem 1.25rem;
            background: rgba(255,255,255,0.08);
            border: 1px solid rgba(255,255,255,0.15);
            border-radius: 100px;
            color: var(--accent);
            font-size: 0.85rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            margin-bottom: 2rem;
            animation: fadeUp 0.8s ease-out;
        }

        .hero-badge::before {
            content: '';
            width: 8px;
            height: 8px;
            background: var(--accent);
            border-radius: 50%;
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; transform: scale(1); }
            50% { opacity: 0.5; transform: scale(1.2); }
        }

        .hero h1 {
            font-family: 'Bebas Neue', sans-serif;
            font-size: clamp(4rem, 12vw, 10rem);
            line-height: 0.9;
            color: white;
            letter-spacing: -0.02em;
            margin-bottom: 1.5rem;
            animation: fadeUp 0.8s ease-out 0.1s backwards;
        }

        .hero h1 span {
            display: block;
            background: linear-gradient(90deg, var(--accent), var(--gold-light));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero-subtitle {
            font-size: 1.25rem;
            color: rgba(255,255,255,0.7);
            max-width: 600px;
            margin: 0 auto 3rem;
            animation: fadeUp 0.8s ease-out 0.2s backwards;
        }

        .hero-stats {
            display: flex;
            justify-content: center;
            gap: 4rem;
            flex-wrap: wrap;
            animation: fadeUp 0.8s ease-out 0.3s backwards;
        }

        .stat {
            text-align: center;
        }

        .stat-value {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 3.5rem;
            color: white;
            line-height: 1;
        }

        .stat-value.accent { color: var(--accent); }
        .stat-value.gold { color: var(--gold-light); }

        .stat-label {
            font-size: 0.85rem;
            color: rgba(255,255,255,0.5);
            text-transform: uppercase;
            letter-spacing: 0.1em;
            margin-top: 0.25rem;
        }

        @keyframes fadeUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .scroll-indicator {
            position: absolute;
            bottom: 2rem;
            left: 50%;
            transform: translateX(-50%);
            color: rgba(255,255,255,0.4);
            animation: bounce 2s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateX(-50%) translateY(0); }
            50% { transform: translateX(-50%) translateY(10px); }
        }

        /* Navigation */
        .nav {
            position: sticky;
            top: 0;
            z-index: 100;
            background: var(--glass);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border-bottom: 1px solid var(--divider);
            padding: 1rem 2rem;
        }

        .nav-inner {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: center;
            gap: 0.5rem;
            flex-wrap: wrap;
            overflow-x: auto;
            -webkit-overflow-scrolling: touch;
            scrollbar-width: none;
            -ms-overflow-style: none;
        }

        .nav-inner::-webkit-scrollbar {
            display: none;
        }

        .nav a {
            padding: 0.5rem 1rem;
            color: var(--muted);
            text-decoration: none;
            font-size: 0.875rem;
            font-weight: 500;
            border-radius: 6px;
            transition: all 0.2s ease;
        }

        .nav a:hover {
            color: var(--ink);
            background: rgba(0,0,0,0.05);
        }

        /* Main Content */
        main {
            max-width: 1200px;
            margin: 0 auto;
            padding: 4rem 2rem;
        }

        /* Section Headers */
        .section-header {
            display: flex;
            align-items: center;
            gap: 1.5rem;
            margin-bottom: 3rem;
            padding-top: 2rem;
        }

        .section-number {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 4rem;
            color: var(--divider);
            line-height: 1;
        }

        .section-title {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 2.5rem;
            letter-spacing: 0.02em;
        }

        /* Cards */
        .card-grid {
            display: grid;
            gap: 1.5rem;
            margin-bottom: 4rem;
        }

        .card-grid.cols-2 {
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        }

        .card-grid.cols-3 {
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
        }

        .card {
            background: white;
            border-radius: 16px;
            padding: 2rem;
            border: 1px solid var(--divider);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .card:hover {
            transform: translateY(-4px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.08);
        }

        .card.featured {
            background: linear-gradient(135deg, var(--ink) 0%, #1a1a2e 100%);
            color: white;
            border: none;
        }

        .card.featured .card-label { color: var(--accent); }

        .card.accent-border {
            border-left: 4px solid var(--accent);
            border-radius: 0 16px 16px 0;
        }

        .card.gold-border {
            border-left: 4px solid var(--gold);
            border-radius: 0 16px 16px 0;
        }

        .card-icon {
            width: 48px;
            height: 48px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            margin-bottom: 1.25rem;
        }

        .card-icon.green { background: rgba(0, 200, 150, 0.12); }
        .card-icon.gold { background: rgba(201, 162, 39, 0.12); }
        .card-icon.blue { background: rgba(59, 130, 246, 0.12); }

        .card-label {
            font-size: 0.75rem;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            color: var(--muted);
            margin-bottom: 0.5rem;
        }

        .card-title {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 1.75rem;
            letter-spacing: 0.02em;
            margin-bottom: 0.75rem;
        }

        .card-value {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 3rem;
            color: var(--accent);
            line-height: 1;
        }

        .card.featured .card-value { color: var(--gold-light); }

        .card-description {
            color: var(--muted);
            font-size: 0.95rem;
            line-height: 1.7;
        }

        .card.featured .card-description { color: rgba(255,255,255,0.7); }

        /* Commission Table */
        .commission-table {
            width: 100%;
            border-collapse: collapse;
            margin: 2rem 0;
            background: white;
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 4px 20px rgba(0,0,0,0.06);
        }

        .commission-table th,
        .commission-table td {
            padding: 1.25rem 1.5rem;
            text-align: left;
            border-bottom: 1px solid var(--divider);
        }

        .commission-table th {
            background: var(--ink);
            color: white;
            font-weight: 600;
            font-size: 0.85rem;
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }

        .commission-table tr:last-child td {
            border-bottom: none;
        }

        .commission-table tr:hover td {
            background: rgba(0, 200, 150, 0.04);
        }

        .rate-badge {
            display: inline-flex;
            align-items: center;
            padding: 0.35rem 0.75rem;
            background: linear-gradient(135deg, var(--accent), var(--accent-dark));
            color: white;
            font-weight: 700;
            border-radius: 6px;
            font-size: 0.95rem;
        }

        /* Info Blocks */
        .info-block {
            background: linear-gradient(135deg, rgba(0, 200, 150, 0.05) 0%, rgba(201, 162, 39, 0.05) 100%);
            border-radius: 16px;
            padding: 2rem;
            margin: 2rem 0;
            border: 1px solid var(--divider);
        }

        .info-block h4 {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .info-block p {
            color: var(--muted);
            line-height: 1.7;
        }

        /* List Styles */
        .check-list {
            list-style: none;
            margin: 1.5rem 0;
        }

        .check-list li {
            padding: 0.75rem 0;
            padding-left: 2rem;
            position: relative;
            border-bottom: 1px solid var(--divider);
        }

        .check-list li:last-child {
            border-bottom: none;
        }

        .check-list li::before {
            content: '✓';
            position: absolute;
            left: 0;
            color: var(--accent);
            font-weight: 700;
        }

        /* Timeline */
        .timeline {
            position: relative;
            margin: 2rem 0;
            padding-left: 2rem;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(to bottom, var(--accent), var(--gold));
        }

        .timeline-item {
            position: relative;
            padding: 1.5rem 0;
            padding-left: 2rem;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -2rem;
            top: 1.75rem;
            width: 12px;
            height: 12px;
            background: var(--accent);
            border-radius: 50%;
            transform: translateX(-5px);
        }

        .timeline-title {
            font-weight: 600;
            margin-bottom: 0.5rem;
        }

        .timeline-content {
            color: var(--muted);
            font-size: 0.95rem;
        }

        /* Callout */
        .callout {
            background: var(--ink);
            color: white;
            border-radius: 20px;
            padding: 3rem;
            margin: 4rem 0;
            position: relative;
            overflow: hidden;
        }

        .callout::before {
            content: '';
            position: absolute;
            top: -100px;
            right: -100px;
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(0, 200, 150, 0.3) 0%, transparent 70%);
        }

        .callout-content {
            position: relative;
            z-index: 2;
        }

        .callout h3 {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .callout p {
            color: rgba(255,255,255,0.7);
            font-size: 1.1rem;
            max-width: 600px;
        }

        /* Footer */
        footer {
            background: var(--ink);
            color: white;
            padding: 4rem 2rem;
            text-align: center;
        }

        .footer-logo {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 2rem;
            margin-bottom: 1rem;
        }

        .footer-address {
            color: rgba(255,255,255,0.5);
            font-size: 0.9rem;
            margin-bottom: 2rem;
        }

        .footer-cta {
            display: inline-flex;
            align-items: center;
            gap: 0.75rem;
            padding: 1rem 2rem;
            background: linear-gradient(135deg, var(--accent), var(--accent-dark));
            color: white;
            text-decoration: none;
            font-weight: 600;
            border-radius: 100px;
            transition: all 0.3s ease;
        }

        .footer-cta:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 30px rgba(0, 200, 150, 0.3);
        }

        /* Warning Box */
        .warning-box {
            background: rgba(201, 162, 39, 0.1);
            border: 1px solid rgba(201, 162, 39, 0.3);
            border-radius: 12px;
            padding: 1.5rem;
            margin: 1.5rem 0;
        }

        .warning-box strong {
            color: var(--gold);
        }

        /* Responsive - Tablet */
        @media (max-width: 1024px) {
            main {
                padding: 3rem 1.5rem;
            }

            .callout {
                padding: 2.5rem;
            }

            .card-grid.cols-3 {
                grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            }
        }

        /* Responsive - Mobile */
        @media (max-width: 768px) {
            .hero {
                min-height: 100svh; /* Use small viewport height for mobile browsers */
                padding: 1.5rem;
                padding-top: 3rem;
            }

            .hero h1 {
                font-size: clamp(3rem, 15vw, 5rem);
            }

            .hero-subtitle {
                font-size: 1rem;
                margin-bottom: 2rem;
            }

            .hero-stats {
                gap: 1.5rem;
                width: 100%;
            }

            .stat {
                flex: 1;
                min-width: 80px;
            }

            .stat-value {
                font-size: 2.5rem;
            }

            .stat-label {
                font-size: 0.7rem;
            }

            .hero-badge {
                font-size: 0.75rem;
                padding: 0.4rem 1rem;
            }

            /* Navigation Mobile */
            .nav {
                padding: 0.75rem 1rem;
            }

            .nav-inner {
                gap: 0.25rem;
            }

            .nav a {
                padding: 0.4rem 0.6rem;
                font-size: 0.75rem;
            }

            /* Main Content Mobile */
            main {
                padding: 2rem 1rem;
            }
            
            .section-header {
                flex-direction: column;
                align-items: flex-start;
                gap: 0.25rem;
                margin-bottom: 2rem;
            }

            .section-number {
                font-size: 2rem;
            }

            .section-title {
                font-size: 1.75rem;
            }

            /* Cards Mobile */
            .card-grid {
                gap: 1rem;
            }

            .card-grid.cols-2,
            .card-grid.cols-3 {
                grid-template-columns: 1fr;
            }

            .card {
                padding: 1.5rem;
            }

            .card-title {
                font-size: 1.5rem;
            }

            .card-value {
                font-size: 2.5rem;
            }

            /* Commission Table Mobile */
            .commission-table {
                font-size: 0.8rem;
                display: block;
                overflow-x: auto;
                -webkit-overflow-scrolling: touch;
            }

            .commission-table th,
            .commission-table td {
                padding: 0.875rem 0.75rem;
                white-space: nowrap;
            }

            .rate-badge {
                padding: 0.25rem 0.5rem;
                font-size: 0.85rem;
            }

            /* Info Block Mobile */
            .info-block {
                padding: 1.5rem;
            }

            .info-block h4 {
                font-size: 1.25rem;
            }

            /* Timeline Mobile */
            .timeline {
                padding-left: 1.5rem;
            }

            .timeline-item {
                padding-left: 1.5rem;
            }

            .timeline-item::before {
                left: -1.5rem;
                width: 10px;
                height: 10px;
                transform: translateX(-4px);
            }

            .timeline-title {
                font-size: 0.95rem;
            }

            .timeline-content {
                font-size: 0.875rem;
            }

            /* Callout Mobile */
            .callout {
                padding: 2rem 1.5rem;
                margin: 3rem 0;
                border-radius: 16px;
            }

            .callout h3 {
                font-size: 1.75rem;
            }

            .callout p {
                font-size: 1rem;
            }

            /* Transition Visual Mobile */
            .transition-visual {
                flex-wrap: wrap;
                gap: 0.5rem;
            }

            .transition-month {
                flex: 1 1 calc(50% - 0.5rem);
                min-width: calc(50% - 0.5rem);
                padding: 1rem 0.75rem;
            }

            .transition-value {
                font-size: 1.5rem;
            }

            /* Quick Facts Mobile */
            .quick-facts {
                grid-template-columns: repeat(2, 1fr);
                margin: 2rem 0;
            }

            .quick-fact {
                padding: 1rem;
            }

            .quick-fact-value {
                font-size: 1.25rem;
            }

            /* Check List Mobile */
            .check-list li {
                padding: 0.6rem 0;
                padding-left: 1.75rem;
                font-size: 0.9rem;
            }

            /* Warning Box Mobile */
            .warning-box {
                padding: 1.25rem;
                font-size: 0.9rem;
            }

            /* Footer Mobile */
            footer {
                padding: 3rem 1.5rem;
            }

            .footer-logo {
                font-size: 1.5rem;
            }

            .footer-cta {
                padding: 0.875rem 1.5rem;
                font-size: 0.9rem;
            }

            .scroll-indicator {
                bottom: 1.5rem;
            }
        }

        /* Small Mobile */
        @media (max-width: 380px) {
            .hero h1 {
                font-size: 2.5rem;
            }

            .hero-stats {
                flex-direction: column;
                gap: 1rem;
            }

            .stat {
                display: flex;
                align-items: center;
                gap: 1rem;
            }

            .stat-value {
                font-size: 2rem;
            }

            .stat-label {
                text-align: left;
            }

            .quick-facts {
                grid-template-columns: 1fr;
            }

            .transition-month {
                flex: 1 1 100%;
            }

            .nav-inner {
                justify-content: flex-start;
                overflow-x: auto;
                -webkit-overflow-scrolling: touch;
                flex-wrap: nowrap;
                padding-bottom: 0.5rem;
            }

            .nav a {
                flex-shrink: 0;
            }
        }

        /* Landscape Mobile */
        @media (max-height: 500px) and (orientation: landscape) {
            .hero {
                min-height: auto;
                padding: 2rem;
            }

            .hero h1 {
                font-size: 3rem;
            }

            .hero-stats {
                margin-top: 1rem;
            }

            .scroll-indicator {
                display: none;
            }
        }

        /* Large Desktop */
        @media (min-width: 1400px) {
            main {
                max-width: 1400px;
            }

            .hero h1 {
                font-size: 12rem;
            }

            .hero-subtitle {
                font-size: 1.4rem;
            }

            .stat-value {
                font-size: 4.5rem;
            }

            .section-title {
                font-size: 3rem;
            }

            .card-grid.cols-3 {
                grid-template-columns: repeat(3, 1fr);
            }
        }

        /* Ultra Wide */
        @media (min-width: 1800px) {
            .hero-content {
                max-width: 1100px;
            }

            main {
                max-width: 1600px;
            }
        }

        /* Transition Percentages Visual */
        .transition-visual {
            display: flex;
            gap: 0.5rem;
            margin: 2rem 0;
        }

        .transition-month {
            flex: 1;
            background: white;
            border-radius: 12px;
            padding: 1.5rem 1rem;
            text-align: center;
            border: 1px solid var(--divider);
        }

        .transition-month.current {
            background: linear-gradient(135deg, var(--accent), var(--accent-dark));
            color: white;
            border: none;
        }

        .transition-label {
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            margin-bottom: 0.5rem;
            opacity: 0.7;
        }

        .transition-value {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 1.75rem;
        }

        /* Quick Facts Strip */
        .quick-facts {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1px;
            background: var(--divider);
            border-radius: 16px;
            overflow: hidden;
            margin: 3rem 0;
        }

        .quick-fact {
            background: white;
            padding: 1.5rem;
            text-align: center;
        }

        .quick-fact-label {
            font-size: 0.75rem;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            color: var(--muted);
            margin-bottom: 0.5rem;
        }

        .quick-fact-value {
            font-family: 'Bebas Neue', sans-serif;
            font-size: 1.5rem;
        }
    </style>
</head>
<body>
    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <div class="hero-badge">
                <span>Now Recruiting</span>
            </div>
            <h1>
                BUILD YOUR<br>
                <span>EMPIRE</span>
            </h1>
            <p class="hero-subtitle">
                Uncapped commissions. Remote flexibility. A healthcare industry ripe for disruption. 
                Join the DME sales team that rewards performers without limits.
            </p>
            <div class="hero-stats">
                <div class="stat">
                    <div class="stat-value accent">4%</div>
                    <div class="stat-label">Starting Commission</div>
                </div>
                <div class="stat">
                    <div class="stat-value">$50K</div>
                    <div class="stat-label">Facility Bonus</div>
                </div>
                <div class="stat">
                    <div class="stat-value gold">∞</div>
                    <div class="stat-label">No Cap Ever</div>
                </div>
            </div>
        </div>
        <div class="scroll-indicator">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M12 5v14M5 12l7 7 7-7"/>
            </svg>
        </div>
    </section>

    <!-- Navigation -->
    <nav class="nav">
        <div class="nav-inner">
            <a href="#compensation">Compensation</a>
            <a href="#bonus">Facility Bonus</a>
            <a href="#accounts">Account Ownership</a>
            <a href="#protection">Your Protection</a>
            <a href="#rules">The Rules</a>
            <a href="#expectations">Expectations</a>
        </div>
    </nav>

    <!-- Main Content -->
    <main>
        <!-- Quick Facts -->
        <div class="quick-facts">
            <div class="quick-fact">
                <div class="quick-fact-label">Employment Type</div>
                <div class="quick-fact-value">W-2 Part-Time</div>
            </div>
            <div class="quick-fact">
                <div class="quick-fact-label">Location</div>
                <div class="quick-fact-value">100% Remote</div>
            </div>
            <div class="quick-fact">
                <div class="quick-fact-label">Base Salary</div>
                <div class="quick-fact-value">Commission Only</div>
            </div>
            <div class="quick-fact">
                <div class="quick-fact-label">Plan Lock</div>
                <div class="quick-fact-value">18 Months</div>
            </div>
        </div>

        <!-- Section 1: Compensation -->
        <section id="compensation">
            <div class="section-header">
                <span class="section-number">01</span>
                <h2 class="section-title">UNCAPPED COMMISSION STRUCTURE</h2>
            </div>

            <p style="font-size: 1.1rem; margin-bottom: 2rem; max-width: 700px;">
                No base salary means no ceiling. Your earnings are directly tied to your performance. 
                The more you sell, the more you earn—simple as that. Commission is earned when product ships, 
                <strong>not when the payor pays.</strong>
            </p>

            <table class="commission-table">
                <thead>
                    <tr>
                        <th>Annual Gross Sales</th>
                        <th>Commission Rate</th>
                        <th>Your Take on Each Tier</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>$0 – $1,000,000</td>
                        <td><span class="rate-badge">4%</span></td>
                        <td>Up to $40,000</td>
                    </tr>
                    <tr>
                        <td>$1M – $2,000,000</td>
                        <td><span class="rate-badge">3%</span></td>
                        <td>Additional $30,000</td>
                    </tr>
                    <tr>
                        <td>$2M – $5,000,000</td>
                        <td><span class="rate-badge">2%</span></td>
                        <td>Additional $60,000</td>
                    </tr>
                    <tr>
                        <td>$5M+</td>
                        <td><span class="rate-badge">1%</span></td>
                        <td><strong>Unlimited</strong></td>
                    </tr>
                </tbody>
            </table>

            <div class="info-block">
                <h4>💰 Example: $3M Annual Sales</h4>
                <p>
                    First $1M at 4% = $40,000 + Next $1M at 3% = $30,000 + Next $1M at 2% = $20,000 
                    = <strong>$90,000 annual commission</strong>. Beat $5M? Keep earning 1% on every dollar beyond—forever.
                </p>
            </div>
        </section>

        <!-- Section 2: Facility Bonus -->
        <section id="bonus">
            <div class="section-header">
                <span class="section-number">02</span>
                <h2 class="section-title">THE $50K FACILITY BONUS</h2>
            </div>

            <div class="card-grid cols-2">
                <div class="card featured">
                    <div class="card-label">One-Time Bonus</div>
                    <div class="card-value">$50,000</div>
                    <p class="card-description" style="margin-top: 1rem;">
                        Open a new facility and drive $3M in gross sales within 12 months from that location. 
                        This is <em>in addition</em> to your regular commissions.
                    </p>
                </div>
                <div class="card accent-border">
                    <div class="card-icon green">🏥</div>
                    <div class="card-title">How It Works</div>
                    <p class="card-description">
                        You're credited as the "Facility Opener" when you register the first prescriber at a new facility 
                        AND close the first order. All sales from that facility—even from other reps' prescribers—count 
                        toward your $3M threshold.
                    </p>
                </div>
            </div>

            <div class="warning-box">
                <strong>⚠️ Key Detail:</strong> Other reps who add prescribers at your facility earn their 
                commissions on those accounts, but <em>you</em> get the $50K bonus if the facility hits $3M.
            </div>
        </section>

        <!-- Section 3: Account Ownership -->
        <section id="accounts">
            <div class="section-header">
                <span class="section-number">03</span>
                <h2 class="section-title">ACCOUNT OWNERSHIP RULES</h2>
            </div>

            <p style="font-size: 1.1rem; margin-bottom: 2rem; max-width: 700px;">
                An "Account" = a specific <strong>prescriber + facility combination</strong>. 
                Dr. Smith at Hospital A and Dr. Smith at Clinic B are two separate accounts you can claim.
            </p>

            <div class="card-grid cols-3">
                <div class="card">
                    <div class="card-icon green">📝</div>
                    <div class="card-title">Register Fast</div>
                    <p class="card-description">
                        Log every prospect in the CRM within 48 hours of first contact. Include prescriber, facility, 
                        contact details, and conversation notes.
                    </p>
                </div>
                <div class="card">
                    <div class="card-icon gold">🤝</div>
                    <div class="card-title">Engagement Wins</div>
                    <p class="card-description">
                        Registration alone doesn't lock an account. You need documented responses and meaningful engagement. 
                        If you go silent for 30 days, the account opens up.
                    </p>
                </div>
                <div class="card">
                    <div class="card-icon blue">📦</div>
                    <div class="card-title">First Order Locks It</div>
                    <p class="card-description">
                        The rep who closes the first order from a prescriber-facility combo is formally assigned 
                        that account—subject to performance requirements.
                    </p>
                </div>
            </div>
        </section>

        <!-- Callout: Competitive Environment -->
        <div class="callout">
            <div class="callout-content">
                <h3>THIS IS A MERITOCRACY</h3>
                <p>
                    Accounts can be reassigned. If you're not performing, a hungrier rep can claim your territory. 
                    That's not a bug—it's the system working. We reward results, not tenure.
                </p>
            </div>
        </div>

        <!-- Section 4: Protection -->
        <section id="protection">
            <div class="section-header">
                <span class="section-number">04</span>
                <h2 class="section-title">YOUR PROTECTIONS</h2>
            </div>

            <div class="card-grid cols-2">
                <div class="card gold-border">
                    <div class="card-title">18-Month Rate Lock</div>
                    <p class="card-description">
                        Your commission rates and bonus structure are guaranteed for 18 months from your start date. 
                        Auto-renews annually unless either party gives 30 days notice.
                    </p>
                </div>
                <div class="card gold-border">
                    <div class="card-title">Trailing Commissions</div>
                    <p class="card-description">
                        Leave on good terms with 30 days notice? You earn commissions on your accounts for 12 more months. 
                        Laid off without cause? 24 months of trailing commissions.
                    </p>
                </div>
            </div>

            <h3 style="font-family: 'Bebas Neue'; font-size: 1.75rem; margin: 3rem 0 1.5rem;">When Accounts Get Reassigned</h3>

            <p style="margin-bottom: 1.5rem;">You don't just lose accounts—you get a transition period with declining commission share:</p>

            <div class="transition-visual">
                <div class="transition-month current">
                    <div class="transition-label">Month 1</div>
                    <div class="transition-value">75%</div>
                </div>
                <div class="transition-month">
                    <div class="transition-label">Month 2</div>
                    <div class="transition-value">50%</div>
                </div>
                <div class="transition-month">
                    <div class="transition-label">Month 3</div>
                    <div class="transition-value">25%</div>
                </div>
                <div class="transition-month">
                    <div class="transition-label">Month 4+</div>
                    <div class="transition-value">0%</div>
                </div>
            </div>

            <div class="info-block">
                <h4>🛡️ Protected Account Status</h4>
                <p>
                    If your prescriber retires, relocates, or the facility closes—factors outside your control—you 
                    can apply for Protected Status. This shields you from performance-based reassignment for 120 days.
                </p>
            </div>
        </section>

        <!-- Section 5: The Rules -->
        <section id="rules">
            <div class="section-header">
                <span class="section-number">05</span>
                <h2 class="section-title">REASSIGNMENT TRIGGERS</h2>
            </div>

            <p style="font-size: 1.1rem; margin-bottom: 2rem; max-width: 700px;">
                Know the five ways an account can change hands. Play by these rules and you'll thrive.
            </p>

            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-title">1. Prescriber/Facility Request</div>
                    <div class="timeline-content">
                        The customer asks for a different rep in writing. Immediate transfer, no trailing commission, no appeal.
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-title">2. Mutual Agreement</div>
                    <div class="timeline-content">
                        You and another rep agree in writing to swap accounts. Terms are negotiable.
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-title">3. Performance Decline (35%+ drop for 90 days)</div>
                    <div class="timeline-content">
                        If an account's revenue drops 35%+ for 90 consecutive days, it's flagged. You get 30-60 days notice 
                        and 3-month trailing commission. You can appeal within 90 days.
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-title">4. Competitive Takeover</div>
                    <div class="timeline-content">
                        After an account is flagged for performance decline, another rep can claim it by documenting 
                        new contacts and driving 35%+ revenue improvement. Requires manager approval.
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-title">5. Abandonment (90 days no CRM activity)</div>
                    <div class="timeline-content">
                        No logged contacts in CRM for 90 days = abandoned. Account goes open, no trailing commission. 
                        First rep to close a new order claims it.
                    </div>
                </div>
            </div>

            <div class="warning-box">
                <strong>🚫 No Gaming the System:</strong> Artificial inflation, manipulation of assignments, 
                CRM misrepresentation = termination for cause and forfeiture of all unpaid commissions.
            </div>
        </section>

        <!-- Section 6: Expectations -->
        <section id="expectations">
            <div class="section-header">
                <span class="section-number">06</span>
                <h2 class="section-title">WHAT WE EXPECT FROM YOU</h2>
            </div>

            <div class="card-grid cols-2">
                <div class="card">
                    <div class="card-title">Your Core Duties</div>
                    <ul class="check-list">
                        <li>Develop referral relationships with physicians, clinics, hospitals, and home health agencies</li>
                        <li>Promote and sell Company DME products and services</li>
                        <li>Maintain accurate CRM records—contacts, activities, orders</li>
                        <li>Full compliance with HIPAA, Anti-Kickback, and healthcare regulations</li>
                    </ul>
                </div>
                <div class="card">
                    <div class="card-title">What We Provide</div>
                    <ul class="check-list">
                        <li>Complete remote flexibility—work from anywhere</li>
                        <li>Part-time structure with mutually agreed workload</li>
                        <li>W-2 employment with proper tax handling</li>
                        <li>CRM and tools to manage your territory</li>
                        <li>Clear, fair rules documented in writing</li>
                    </ul>
                </div>
            </div>

            <div class="info-block" style="margin-top: 2rem;">
                <h4>📋 Compliance is Non-Negotiable</h4>
                <p>
                    You'll sign a HIPAA Workforce Agreement. Violations of HIPAA, confidentiality, or non-solicitation 
                    = immediate termination for cause and forfeiture of all trailing commissions. Healthcare sales 
                    requires absolute integrity.
                </p>
            </div>

            <h3 style="font-family: 'Bebas Neue'; font-size: 1.75rem; margin: 3rem 0 1.5rem;">After You Leave</h3>

            <div class="card-grid cols-2">
                <div class="card accent-border">
                    <div class="card-label">What's Allowed</div>
                    <div class="card-title">No Non-Compete</div>
                    <p class="card-description">
                        After leaving, you're free to work anywhere in DME or healthcare. We don't restrict your career.
                    </p>
                </div>
                <div class="card gold-border">
                    <div class="card-label">What's Restricted</div>
                    <div class="card-title">12-Month Non-Solicitation</div>
                    <p class="card-description">
                        You can't poach your former accounts or Company employees for competing DME sales for 12 months.
                    </p>
                </div>
            </div>
        </section>

        <!-- Final Callout -->
        <div class="callout" style="text-align: center; margin-top: 4rem;">
            <div class="callout-content">
                <h3>READY TO BUILD SOMETHING?</h3>
                <p style="margin: 0 auto 2rem; text-align: center;">
                    This isn't a job for everyone. It's for hunters who want ownership of their results 
                    and earnings that scale with their ambition. No ceiling. No excuses.
                </p>
            </div>
        </div>
    </main>

    <!-- Footer -->
    <footer>
        <div class="footer-logo">HOLISTIC MEDICAL SUPPLY</div>
        <p class="footer-address">
            1170 Port Washington Blvd, Port Washington, NY 11050<br>
            Part of Holistec Holdings
        </p>
        <a href="/cdn-cgi/l/email-protection#7c1f1d0e19190e0f3c141310150f08151f111918151f1d100f090c0c1005521f1311" class="footer-cta">
            Apply Now
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M5 12h14M12 5l7 7-7 7"/>
