<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Philippine Artistry Art Gallery</title>
    <style>

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: #3e2723;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            background: linear-gradient(rgba(244, 236, 207, 0.85), rgba(244, 236, 207, 0.85)),
                        url('https://cdn.luxatic.com/wp-content/uploads/2019/02/Vincent-van-Gogh.jpg') no-repeat center center fixed;
            background-size: cover;
        }

        .nav {
            background-color: #5d4037;
            padding: 15px 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .nav-list {
            list-style: none;
            display: flex;
            justify-content: center;
            gap: 40px;
        }

        .nav-link {
            text-decoration: none;
            color: #efebe9;
            font-weight: bold;
            font-size: 1.1rem;
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .nav-link:hover,
        .nav-link.active {
            color: #ffcc80;
        }

        .side-menu {
            position: fixed;
            left: 0;
            top: 50%;
            transform: translateY(-50%);
            background-color: rgba(93, 64, 55, 0.9);
            padding: 20px 10px;
            border-radius: 0 10px 10px 0;
            display: flex;
            flex-direction: column;
            gap: 20px;
            box-shadow: 2px 0 10px rgba(0, 0, 0, 0.2);
            z-index: 999;
        }

        .side-link {
            writing-mode: vertical-rl;
            text-orientation: mixed;
            transform: rotate(180deg);
            color: #efebe9;
            text-decoration: none;
            font-size: 0.9rem;
            font-weight: bold;
            cursor: pointer;
            padding: 10px 5px;
            transition: all 0.3s ease;
            border-left: 3px solid transparent;
        }

        .side-link:hover {
            color: #ffcc80;
            border-left: 3px solid #ffcc80;
        }

        main {
            flex: 1;
            margin-left: 60px; 
        }

        .page-section {
            display: none;
            padding: 40px 20px;
            animation: fadeIn 0.5s ease;
        }

        .page-section.active {
            display: block;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .home-content {
            text-align: center;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .header-title {
            font-size: 3.5rem;
            margin-bottom: 5px;
            text-shadow: 1px 1px 3px rgba(255, 255, 255, 0.5);
        }

        .header-subtitle {
            font-size: 1.5rem;
            font-style: italic;
            color: #6d4c41;
            margin-bottom: 30px;
        }

        .login-card {
            background-color: rgba(255, 255, 255, 0.95);
            padding: 40px 30px;
            border-radius: 12px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            width: 100%;
            max-width: 400px;
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-input {
            width: 100%;
            padding: 12px;
            border: 2px solid #a1887f;
            border-radius: 6px;
            outline: none;
        }

        .login-button {
            width: 100%;
            padding: 12px;
            font-weight: bold;
            color: white;
            background-color: #5d4037;
            border: none;
            border-radius: 6px;
            cursor: pointer;
        }

        .tutorial-container {
            max-width: 900px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.9);
            padding: 30px;
            border-radius: 15px;
        }

        .tutorial-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 40px;
            color: #4e342e;
            border-bottom: 3px solid #5d4037;
            padding-bottom: 10px;
        }

        .tutorial-row {
            display: flex;
            gap: 20px;
            margin-bottom: 40px;
            align-items: center;
        }

        .video-link-wrapper {
            flex: 1;
            text-decoration: none;
        }

        .video-box {
            position: relative;
            height: 180px;
            background-color: #000;
            border: 3px solid #8d6e63;
            border-radius: 10px;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            transition: all 0.3s ease;
        }

        .video-box img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            opacity: 0.8;
        }

        .video-box::after {
            content: '▶';
            position: absolute;
            font-size: 3rem;
            color: white;
            background: rgba(93, 64, 55, 0.6);
            width: 60px;
            height: 60px;
            display: flex;
            justify-content: center;
            align-items: center;
            border-radius: 50%;
        }

        .video-box:hover {
            border-color: #ffcc80;
            transform: scale(1.03);
        }

        .text-box {
            flex: 1.5;
        }

        .text-box h3 {
            color: #bf360c;
            margin-bottom: 10px;
        }

        .text-box p {
            line-height: 1.6;
            color: #5d4037;
        }

        .footer {
            margin-top: auto;
            padding: 20px;
            text-align: center;
            background-color: rgba(244, 236, 207, 0.8);
            border-top: 1px solid #d7ccc8;
        }
    </style>
</head>
<body>
    <nav class="nav">
        <ul class="nav-list">
            <li><span class="nav-link" onclick="showPage('home')">Home</span></li>
            <li><span class="nav-link" onclick="showPage('tutorials')">Tutorials</span></li>
            <li><span class="nav-link">Arts & History</span></li>
        </ul>
    </nav>

    <aside class="side-menu">
        <div class="side-link" onclick="showPage('home')">Home</div>
        <div class="side-link" onclick="showPage('tutorials')">Tutorials</div>
        <div class="side-link">History</div>
    </aside>

    <main>
        <section id="home" class="page-section active">
            <div class="home-content">
                <h1 class="header-title">Welcome!</h1>
                <h2 class="header-subtitle">Philippine Artistry Art Gallery</h2>

                <div class="login-card">
                    <h3 style="margin-bottom: 20px;">Log-in</h3>
                    <form id="loginForm">
                        <div class="form-group">
                            <input type="text" id="user" class="form-input" placeholder="Username" required>
                        </div>
                        <div class="form-group">
                            <input type="password" id="pass" class="form-input" placeholder="Password" required>
                        </div>
                        <button type="submit" class="login-button">Log In</button>
                    </form>
                    <p style="margin-top: 15px; font-size: 0.9rem;">Sign-up here <a href="#" style="color: #bf360c;">click me</a></p>
                </div>
            </div>
        </section>

        <section id="tutorials" class="page-section">
            <div class="tutorial-container">
                <h1 class="tutorial-title">How to Improve Your Skills...</h1>

                <div class="tutorial-row">
                    <a href="https://youtu.be/aMlTKtmczzM?si=EVNKbFWa6zKxawEo" target="_blank" class="video-link-wrapper">
                        <div class="video-box">
                            <img src="https://img.youtube.com/vi/aMlTKtmczzM/mqdefault.jpg" alt="Solid Drawing">
                        </div>
                    </a>
                    <div class="text-box">
                        <h3>Foundations for Solid Drawing</h3>
                        <p>Master the essentials of line, shape, and form to describe 3D volumes effectively.</p>
                    </div>
                </div>

                <div class="tutorial-row">
                    <a href="https://youtu.be/pAK0cvVQr_4?si=Fu5_mJzzC8q5QUOE" target="_blank" class="video-link-wrapper">
                        <div class="video-box">
                            <img src="https://img.youtube.com/vi/pAK0cvVQr_4/mqdefault.jpg" alt="Color Theory">
                        </div>
                    </a>
                    <div class="text-box">
                        <h3>Color Theory & Harmony</h3>
                        <p>Learn how Value, Saturation, and Hue interact to set the mood for your artwork.</p>
                    </div>
                </div>

                <div class="tutorial-row">
                    <a href="https://youtu.be/qq8SO9tMI8k?si=nriXdUbPJSk87FDz" target="_blank" class="video-link-wrapper">
                        <div class="video-box">
                            <img src="https://img.youtube.com/vi/qq8SO9tMI8k/mqdefault.jpg" alt="Perspective">
                        </div>
                    </a>
                    <div class="text-box">
                        <h3>Perspective for Beginners</h3>
                        <p>Learn how to use horizon lines and vanishing points to give your art depth.</p>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer class="footer">
        <p><i>"Art isn't all about the details but on how you show your imagination"</i></p>
        <p style="font-size: 0.8rem; margin-top: 5px;">contact@philippineartistry.com | 09989980979</p>
    </footer>

    <script>
        function showPage(pageId) {
      
            document.querySelectorAll('.page-section').forEach(section => {
                section.classList.remove('active');
            });

            document.getElementById(pageId).classList.add('active');
        }

        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const username = document.getElementById('user').value;
            const password = document.getElementById('pass').value;
            if (username === 'admin' && password === 'password') {
                showPage('tutorials');
            } else {
                alert('Incorrect credentials. Try admin/password.');
            }
        });
    </script>
</body>
</html>
