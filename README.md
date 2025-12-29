import React from 'react';

export default function Home() {
    return (
        <div dangerouslySetInnerHTML={{ __html: `
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Exitless VR - Horror Multiplayer Backrooms Game</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            background: #000;
            color: #fff;
            overflow-x: hidden;
        }
        
        /* Hero Section */
        .hero {
            position: relative;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 80px 24px;
            overflow: hidden;
        }
        
        .hero-bg {
            position: absolute;
            inset: 0;
            background: linear-gradient(to bottom, #000, #09090b, #000);
        }
        
        .hero-glow-1 {
            position: absolute;
            top: 25%;
            left: 25%;
            width: 384px;
            height: 384px;
            background: rgba(120, 53, 15, 0.2);
            border-radius: 50%;
            filter: blur(80px);
            animation: pulse 3s ease-in-out infinite;
        }
        
        .hero-glow-2 {
            position: absolute;
            bottom: 25%;
            right: 25%;
            width: 320px;
            height: 320px;
            background: rgba(161, 98, 7, 0.1);
            border-radius: 50%;
            filter: blur(80px);
            animation: pulse 3s ease-in-out infinite 1s;
        }
        
        .hero-grid {
            position: absolute;
            inset: 0;
            opacity: 0.03;
            background-image: 
                linear-gradient(rgba(255,255,255,0.1) 1px, transparent 1px),
                linear-gradient(90deg, rgba(255,255,255,0.1) 1px, transparent 1px);
            background-size: 50px 50px;
        }
        
        .hero-content {
            position: relative;
            z-index: 10;
            max-width: 896px;
            text-align: center;
            animation: fadeInUp 1s ease-out;
        }
        
        .logo {
            width: 100%;
            max-width: 672px;
            margin: 0 auto 48px;
            filter: drop-shadow(0 25px 25px rgba(0, 0, 0, 0.5));
        }
        
        .tagline {
            color: rgba(254, 243, 199, 0.6);
            font-size: 14px;
            letter-spacing: 0.3em;
            text-transform: uppercase;
            margin-bottom: 32px;
            font-weight: 300;
        }
        
        .description {
            color: #d4d4d8;
            font-size: 20px;
            line-height: 1.75;
            max-width: 672px;
            margin: 0 auto;
            font-weight: 300;
        }
        
        .scroll-indicator {
            position: absolute;
            bottom: 32px;
            left: 50%;
            transform: translateX(-50%);
            animation: fadeIn 1s ease-out 1.5s both;
        }
        
        .scroll-box {
            width: 24px;
            height: 40px;
            border: 1px solid #3f3f46;
            border-radius: 12px;
            display: flex;
            justify-content: center;
            padding-top: 8px;
        }
        
        .scroll-dot {
            width: 4px;
            height: 8px;
            background: rgba(245, 158, 11, 0.5);
            border-radius: 2px;
            animation: scrollBounce 1.5s ease-in-out infinite;
        }
        
        /* Store Section */
        .store-section {
            position: relative;
            padding: 96px 24px;
            background: #09090b;
        }
        
        .store-gradient {
            position: absolute;
            inset: 0;
            background: linear-gradient(to bottom, rgba(0,0,0,0.5), transparent, rgba(0,0,0,0.5));
        }
        
        .store-content {
            position: relative;
            z-index: 10;
            max-width: 896px;
            margin: 0 auto;
            text-align: center;
            animation: fadeInUp 0.8s ease-out;
        }
        
        .section-title {
            font-size: 36px;
            font-weight: 300;
            color: #fff;
            margin-bottom: 16px;
            letter-spacing: 0.05em;
        }
        
        .section-subtitle {
            color: #a1a1aa;
            margin-bottom: 48px;
            font-size: 18px;
        }
        
        .meta-link {
            display: inline-flex;
            align-items: center;
            gap: 24px;
            background: linear-gradient(to right, #18181b, #27272a);
            border: 1px solid rgba(63, 63, 70, 0.5);
            border-radius: 16px;
            padding: 24px 32px;
            text-decoration: none;
            transition: all 0.3s;
        }
        
        .meta-link:hover {
            border-color: rgba(59, 130, 246, 0.3);
            box-shadow: 0 0 40px rgba(59, 130, 246, 0.1);
            transform: scale(1.02);
        }
        
        .meta-logo {
            width: 64px;
            height: auto;
        }
        
        .meta-text {
            text-align: left;
        }
        
        .meta-text-small {
            color: #a1a1aa;
            font-size: 14px;
            margin-bottom: 4px;
        }
        
        .meta-text-large {
            color: #fff;
            font-size: 20px;
            font-weight: 500;
            letter-spacing: 0.05em;
        }
        
        .arrow {
            color: #71717a;
            margin-left: 16px;
            transition: color 0.3s;
        }
        
        .meta-link:hover .arrow {
            color: #3b82f6;
        }
        
        /* Social Section */
        .social-section {
            padding: 80px 24px;
            background: #000;
        }
        
        .social-content {
            max-width: 896px;
            margin: 0 auto;
            text-align: center;
        }
        
        .social-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 24px;
            margin-top: 48px;
        }
        
        .social-link {
            position: relative;
            text-decoration: none;
            transition: transform 0.3s;
        }
        
        .social-link:hover {
            transform: translateY(-5px) scale(1.1);
        }
        
        .social-glow {
            position: absolute;
            inset: 0;
            background: rgba(245, 158, 11, 0.2);
            border-radius: 50%;
            filter: blur(24px);
            opacity: 0;
            transition: opacity 0.3s;
        }
        
        .social-link:hover .social-glow {
            opacity: 1;
        }
        
        .social-icon-wrapper {
            position: relative;
            width: 64px;
            height: 64px;
            border-radius: 50%;
            background: #18181b;
            border: 1px solid #27272a;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 8px;
            transition: border-color 0.3s;
        }
        
        .social-link:hover .social-icon-wrapper {
            border-color: #52525b;
        }
        
        .social-icon {
            width: 100%;
            height: 100%;
            object-fit: contain;
        }
        
        .social-name {
            color: #71717a;
            font-size: 12px;
            margin-top: 8px;
            transition: color 0.3s;
        }
        
        .social-link:hover .social-name {
            color: #d4d4d8;
        }
        
        /* Privacy Section */
        .privacy-section {
            padding: 96px 24px;
            background: #09090b;
        }
        
        .privacy-content {
            max-width: 768px;
            margin: 0 auto;
        }
        
        .privacy-container {
            background: rgba(24, 24, 27, 0.5);
            border: 1px solid rgba(39, 39, 42, 0.5);
            border-radius: 16px;
            padding: 32px;
            backdrop-filter: blur(8px);
        }
        
        .policy-item {
            border-bottom: 1px solid rgba(39, 39, 42, 0.5);
        }
        
        .policy-item:last-child {
            border-bottom: none;
        }
        
        .policy-header {
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 20px 0;
            background: none;
            border: none;
            color: #fff;
            font-size: 16px;
            font-weight: 500;
            cursor: pointer;
            text-align: left;
            transition: color 0.3s;
        }
        
        .policy-header:hover {
            color: #fef3c7;
        }
        
        .chevron {
            color: #71717a;
            transition: transform 0.3s, color 0.3s;
            flex-shrink: 0;
        }
        
        .policy-header:hover .chevron {
            color: #d4d4d8;
        }
        
        .policy-item.active .chevron {
            transform: rotate(180deg);
        }
        
        .policy-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
        }
        
        .policy-item.active .policy-content {
            max-height: 1000px;
        }
        
        .policy-text {
            color: #a1a1aa;
            font-size: 14px;
            line-height: 1.75;
            padding-bottom: 20px;
            white-space: pre-line;
        }
        
        .contact-info {
            text-align: center;
            margin-top: 32px;
            color: #71717a;
            font-size: 14px;
        }
        
        .contact-link {
            color: #fbbf24;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .contact-link:hover {
            color: #fcd34d;
        }
        
        /* Footer */
        .footer {
            padding: 48px 24px;
            background: #000;
            border-top: 1px solid #18181b;
        }
        
        .footer-content {
            max-width: 896px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: space-between;
            gap: 24px;
        }
        
        .footer-logo {
            display: flex;
            align-items: center;
            gap: 16px;
        }
        
        .footer-logo img {
            height: 32px;
            opacity: 0.7;
        }
        
        .footer-text {
            text-align: center;
        }
        
        .footer-copyright {
            color: #52525b;
            font-size: 14px;
            margin-bottom: 4px;
        }
        
        .footer-email {
            color: #71717a;
            font-size: 14px;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-email:hover {
            color: #d4d4d8;
        }
        
        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }
        
        @keyframes pulse {
            0%, 100% {
                opacity: 0.2;
            }
            50% {
                opacity: 0.4;
            }
        }
        
        @keyframes scrollBounce {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(8px);
            }
        }
        
        /* Responsive */
        @media (min-width: 768px) {
            .section-title {
                font-size: 48px;
            }
            
            .footer-content {
                flex-direction: row;
            }
            
            .footer-text {
                text-align: right;
            }
            
            .social-icon-wrapper {
                width: 72px;
                height: 72px;
            }
        }
    </style>
</head>
<body>
    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-bg"></div>
        <div class="hero-glow-1"></div>
        <div class="hero-glow-2"></div>
        <div class="hero-grid"></div>
        
        <div class="hero-content">
            <img src="https://qtrypzzcjebvfcihiynt.supabase.co/storage/v1/object/public/base44-prod/public/user_6951b6efba8f538db0b3406f/49862c412_Exitless.png" alt="Exitless" class="logo">
            
            <p class="tagline">Horror Multiplayer VR Experience</p>
            
            <p class="description">
                Exitless is a horror multiplayer VR game, based on the backrooms. 
                Gather a team and take on the backrooms toe to toe, explore many levels, 
                and avoid many monsters, everything that happens here is for a reason . . .
            </p>
        </div>
        
        <div class="scroll-indicator">
            <div class="scroll-box">
                <div class="scroll-dot"></div>
            </div>
        </div>
    </section>

    <!-- Store Section -->
    <section class="store-section">
        <div class="store-gradient"></div>
        
        <div class="store-content">
            <h2 class="section-title">Enter the Backrooms</h2>
            <p class="section-subtitle">Available now on Meta Quest</p>
            
            <a href="https://www.meta.com/experiences/exitless/10068125866566821/" target="_blank" rel="noopener noreferrer" class="meta-link">
                <img src="https://qtrypzzcjebvfcihiynt.supabase.co/storage/v1/object/public/base44-prod/public/user_6951b6efba8f538db0b3406f/5ffcc3c0f_Meta-Emblem.png" alt="Meta Quest" class="meta-logo">
                <div class="meta-text">
                    <p class="meta-text-small">Get it on</p>
                    <p class="meta-text-large">Meta Quest Store</p>
                </div>
                <span class="arrow">→</span>
            </a>
        </div>
    </section>

    <!-- Social Section -->
    <section class="social-section">
        <div class="social-content">
            <h2 class="section-title">Join the Community</h2>
            <p class="section-subtitle">Stay connected and follow our journey</p>
            
            <div class="social-grid">
                <a href="https://www.youtube.com/channel/UChncejrQLbkYtYn0QJL6fzw" target="_blank" rel="noopener noreferrer" class="social-link">
                    <div class="social-glow"></div>
                    <div class="social-icon-wrapper">
                        <img src="https://qtrypzzcjebvfcihiynt.supabase.co/storage/v1/object/public/base44-prod/public/user_6951b6efba8f538db0b3406f/7cab6b2e2_social-youtube-circle-512.png" alt="YouTube" class="social-icon">
                    </div>
                    <p class="social-name">YouTube</p>
                </a>
                
                <a href="https://www.tiktok.com/@exitlessofficial?lang=en" target="_blank" rel="noopener noreferrer" class="social-link">
                    <div class="social-glow"></div>
                    <div class="social-icon-wrapper">
                        <img src="https://qtrypzzcjebvfcihiynt.supabase.co/storage/v1/object/public/base44-prod/public/user_6951b6efba8f538db0b3406f/712b7c0f5_tiktok-icon-free-png.png" alt="TikTok" class="social-icon">
                    </div>
                    <p class="social-name">TikTok</p>
                </a>
                
                <a href="https://x.com/ExitlessVR" target="_blank" rel="noopener noreferrer" class="social-link">
                    <div class="social-glow"></div>
                    <div class="social-icon-wrapper">
                        <img src="https://qtrypzzcjebvfcihiynt.supabase.co/storage/v1/object/public/base44-prod/public/user_6951b6efba8f538db0b3406f/cf315002c_2048px-X_iconsvg.png" alt="X (Twitter)" class="social-icon">
                    </div>
                    <p class="social-name">X (Twitter)</p>
                </a>
                
                <a href="#" target="_blank" rel="noopener noreferrer" class="social-link">
                    <div class="social-glow"></div>
                    <div class="social-icon-wrapper">
                        <img src="https://qtrypzzcjebvfcihiynt.supabase.co/storage/v1/object/public/base44-prod/public/user_6951b6efba8f538db0b3406f/2f6b16c1d_bbW4u80g7yIVxsphv9diNw.png" alt="Discord" class="social-icon">
                    </div>
                    <p class="social-name">Discord</p>
                </a>
                
                <a href="https://www.reddit.com/r/Exitless" target="_blank" rel="noopener noreferrer" class="social-link">
                    <div class="social-glow"></div>
                    <div class="social-icon-wrapper">
                        <img src="https://qtrypzzcjebvfcihiynt.supabase.co/storage/v1/object/public/base44-prod/public/user_6951b6efba8f538db0b3406f/0f3cd86f8_free-reddit-logo-icon-2436-thumb.png" alt="Reddit" class="social-icon">
                    </div>
                    <p class="social-name">Reddit</p>
                </a>
            </div>
        </div>
    </section>

    <!-- Privacy Policy Section -->
    <section class="privacy-section" id="privacy">
        <div class="privacy-content">
            <div style="text-align: center; margin-bottom: 48px;">
                <h2 class="section-title">Privacy Policy</h2>
                <p class="section-subtitle">Your privacy matters to us</p>
            </div>
            
            <div class="privacy-container">
                <div class="policy-item">
                    <button class="policy-header" onclick="togglePolicy(this)">
                        <span>1. Data Collection</span>
                        <span class="chevron">▼</span>
                    </button>
                    <div class="policy-content">
                        <p class="policy-text">We collect your Meta Quest profile information, including your user ID, to track invites and assign you to specific game servers when needed. We also collect your username and profile picture for future friend system features.

The list of things we collect from you:
• User ID
• User profile
• Friends
• Blocked users

Additionally, we track your in-game progression — such as your current level, items, and server location — to provide a seamless and personalized gameplay experience.</p>
                    </div>
                </div>
                
                <div class="policy-item">
                    <button class="policy-header" onclick="togglePolicy(this)">
                        <span>2. How We Use Your Data</span>
                        <span class="chevron">▼</span>
                    </button>
                    <div class="policy-content">
                        <p class="policy-text">We use your data to maintain and update your in-game save file, including tracking strikes based on player reports and your in-game communication (voice or gestures).

No additional data is requested or required. This information helps us ensure a safe and enjoyable environment for you and all players.</p>
                    </div>
                </div>
                
                <div class="policy-item">
                    <button class="policy-header" onclick="togglePolicy(this)">
                        <span>3. Data Sharing</span>
                        <span class="chevron">▼</span>
                    </button>
                    <div class="policy-content">
                        <p class="policy-text">We do not sell, rent, or share your personal data with any third parties — including Meta, websites, or businesses.</p>
                    </div>
                </div>
                
                <div class="policy-item">
                    <button class="policy-header" onclick="togglePolicy(this)">
                        <span>4. Data Retention</span>
                        <span class="chevron">▼</span>
                    </button>
                    <div class="policy-content">
                        <p class="policy-text">We retain only the data necessary for gameplay, legal compliance, or internal analytics.

You may request deletion of your data at any time by contacting us at: exitlessvr@gmail.com

Note: Other contact methods may not be monitored.</p>
                    </div>
                </div>
                
                <div class="policy-item">
                    <button class="policy-header" onclick="togglePolicy(this)">
                        <span>5. Your Rights</span>
                        <span class="chevron">▼</span>
                    </button>
                    <div class="policy-content">
                        <p class="policy-text">Depending on your location, you may have the right to:
• Access or download your personal data
• Request correction or deletion of your data
• Withdraw consent for data processing
• File a complaint with your local data protection authority</p>
                    </div>
                </div>
                
                <div class="policy-item">
                    <button class="policy-header" onclick="togglePolicy(this)">
                        <span>6. Security</span>
                        <span class="chevron">▼</span>
                    </button>
                    <div class="policy-content">
                        <p class="policy-text">We implement reasonable technical and organizational measures to protect your data from unauthorized access, loss, or misuse.</p>
                    </div>
                </div>
                
                <div class="policy-item">
                    <button class="policy-header" onclick="togglePolicy(this)">
                        <span>7. Children's Privacy</span>
                        <span class="chevron">▼</span>
                    </button>
                    <div class="policy-content">
                        <p class="policy-text">Our game is not directed to children under 16. We do not knowingly collect personal information from children. If you believe we have collected such data, please contact us immediately to have it removed.</p>
                    </div>
                </div>
            </div>
            
            <div class="contact-info">
                <p>Have questions? Contact us at: <a href="mailto:exitlessvr@gmail.com" class="contact-link">exitlessvr@gmail.com</a></p>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="footer-content">
            <div class="footer-logo">
                <img src="https://qtrypzzcjebvfcihiynt.supabase.co/storage/v1/object/public/base44-prod/public/user_6951b6efba8f538db0b3406f/49862c412_Exitless.png" alt="Exitless">
            </div>
            
            <div class="footer-text">
                <p class="footer-copyright">© 2024 Exitless VR. All rights reserved.</p>
                <a href="mailto:exitlessvr@gmail.com" class="footer-email">exitlessvr@gmail.com</a>
            </div>
        </div>
    </footer>

    <script>
        function togglePolicy(button) {
            const item = button.parentElement;
            const isActive = item.classList.contains('active');
            
            // Close all items
            document.querySelectorAll('.policy-item').forEach(el => {
                el.classList.remove('active');
            });
            
            // Open clicked item if it wasn't active
            if (!isActive) {
                item.classList.add('active');
            }
        }
    </script>
</body>
</html>
        ` }} />
    );
}
