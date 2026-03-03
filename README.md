# Special-one-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Ivana - Eternal Love 🌹✨</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&family=Sacramento&family=Poppins:wght@300;600&display=swap');
        
        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        body {
            font-family: 'Poppins', sans-serif;
            overflow: hidden;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            background: radial-gradient(ellipse at bottom, #1e3c72 0%, #2a5298 50%, #000428 100%);
        }
        
        #stars { position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 1; }
        #petals { position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 2; }
        #fireworks { position: absolute; top: 0; left: 0; width: 100%; height: 100%; z-index: 3; }
        
        .container {
            text-align: center;
            z-index: 10;
            position: relative;
            max-width: 900px;
            padding: 40px;
            background: rgba(255,255,255,0.1);
            backdrop-filter: blur(20px);
            border-radius: 30px;
            border: 1px solid rgba(255,255,255,0.2);
            box-shadow: 0 25px 50px rgba(0,0,0,0.5);
        }
        
        h1 {
            font-family: 'Sacramento', cursive;
            font-size: 5rem;
            background: linear-gradient(45deg, #ff6b9d, #ffd93d, #6bcf7f, #4ecdc4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 40px rgba(255,255,255,0.5);
            margin-bottom: 20px;
            animation: rainbow 3s ease infinite;
        }
        
        @keyframes rainbow {
            0%, 100% { filter: hue-rotate(0deg); }
            50% { filter: hue-rotate(180deg); }
        }
        
        .subtitle {
            font-family: 'Dancing Script', cursive;
            font-size: 2rem;
            color: #ffd93d;
            margin-bottom: 30px;
            text-shadow: 0 0 20px #ffd93d;
            animation: float 4s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }
        
        .message {
            font-size: 1.4rem;
            color: #fff;
            line-height: 1.7;
            margin-bottom: 40px;
            opacity: 0;
            animation: fadeInUp 1.5s ease 0.5s forwards;
            text-shadow: 0 2px 10px rgba(0,0,0,0.5);
        }
        
        @keyframes fadeInUp {
            to { opacity: 1; transform: translateY(0); }
        }
        
        .flower { font-size: 4rem; animation: bloom 2s ease-in-out infinite; margin: 0 15px; }
        @keyframes bloom {
            0%, 100% { transform: scale(1) rotate(0deg); }
            50% { transform: scale(1.3) rotate(180deg); }
        }
        
        .btn {
            background: linear-gradient(45deg, #ff6b9d, #4ecdc4, #ffd93d, #6bcf7f);
            background-size: 300% 300%;
            color: white;
            border: none;
            padding: 20px 50px;
            font-size: 1.5rem;
            border-radius: 50px;
            cursor: pointer;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 2px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
            animation: gradientShift 4s ease infinite;
        }
        
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        .btn:hover {
            transform: translateY(-10px) scale(1.05);
            box-shadow: 0 30px 60px rgba(255,107,157,0.6);
        }
        
        .silhouette {
            position: absolute;
            bottom: -100px;
            right: 10%;
            font-size: 200px;
            opacity: 0.1;
            animation: sway 6s ease-in-out infinite;
            z-index: 0;
        }
        
        @keyframes sway {
            0%, 100% { transform: rotate(-2deg); }
            50% { transform: rotate(2deg); }
        }
    </style>
</head>
<body>
    <canvas id="stars"></canvas>
    <canvas id="petals"></canvas>
    <canvas id="fireworks"></canvas>
    
    <div class="silhouette">💃</div>
    
    <div class="container">
        <h1>Happy Birthday Ivana! 🌸</h1>
        <p class="subtitle">My Eternal Blossom of Love 💖</p>
        <p class="message">
            In this enchanted garden under the stars, every petal whispers your name. 
            You've painted my life with colors I never knew existed. 
            Today, the universe celebrates YOU—my forever love, my everything. 
            Here's to growing old together, petal by petal. 🌺✨
        </p>
        <div>
            <span class="flower">🌺</span>
            <span class="flower">🌹</span>
            <span class="flower">🌸</span>
        </div>
        <br>
        <button class="btn" onclick="magicalCelebration()">🌟 Light Up the Sky! 🌟</button>
    </div>

    <script>
        // Stars twinkling
        const starsCanvas = document.getElementById('stars');
        const starsCtx = starsCanvas.getContext('2d');
        starsCanvas.width = window.innerWidth;
        starsCanvas.height = window.innerHeight;
        
        const stars = [];
        for(let i = 0; i < 200; i++) {
            stars.push({
                x: Math.random() * starsCanvas.width,
                y: Math.random() * starsCanvas.height * 0.7,
                radius: Math.random() * 2,
                alpha: Math.random(),
                twinkle: Math.random() * Math.PI * 2
            });
        }
        
        function animateStars() {
            starsCtx.clearRect(0, 0, starsCanvas.width, starsCanvas.height);
            stars.forEach(s => {
                s.twinkle += 0.05;
                s.alpha = Math.sin(s.twinkle) * 0.5 + 0.5;
                
                starsCtx.save();
                starsCtx.globalAlpha = s.alpha;
                starsCtx.fillStyle = '#fff';
                starsCtx.beginPath();
                starsCtx.arc(s.x, s.y, s.radius, 0, Math.PI * 2);
                starsCtx.fill();
                starsCtx.restore();
            });
            requestAnimationFrame(animateStars);
        }
        animateStars();

        // Floating rose petals
        const petalsCanvas = document.getElementById('petals');
        const petalsCtx = petalsCanvas.getContext('2d');
        petalsCanvas.width = window.innerWidth;
        petalsCanvas.height = window.innerHeight;
        
        function createPetals() {
            for(let i = 0; i < 5; i++) {
                setTimeout(() => {
                    const petal = {
                        x: Math.random() * petalsCanvas.width,
                        y: -50,
                        vx: (Math.random() - 0.5) * 2,
                        vy: Math.random() * 3 + 2,
                        rotation: 0,
                        rotSpeed: (Math.random() - 0.5) * 0.1,
                        size: Math.random() * 15 + 10,
                        color: ['#ff69b4', '#ff1493', '#db7093', '#ffc0cb'][Math.floor(Math.random()*4)]
                    };
                    
                    function updatePetal() {
                        petal.x += petal.vx;
                        petal.y += petal.vy;
                        petal.rotation += petal.rotSpeed;
                        petal.vy += 0.02;
                        
                        if(petal.y > petalsCanvas.height) return;
                        
                        petalsCtx.save();
                        petalsCtx.translate(petal.x, petal.y);
                        petalsCtx.rotate(petal.rotation);
                        petalsCtx.fillStyle = petal.color;
                        petalsCtx.fillRect(-petal.size/2, -petal.size/4, petal.size, petal.size/2);
                        petalsCtx.fillRect(-petal.size/3, 0, petal.size/1.5, petal.size/4);
                        petalsCtx.restore();
                        
                        requestAnimationFrame(updatePetal);
                    }
                    updatePetal();
                }, i * 200);
            }
        }
        setInterval(createPetals, 3000);

        // MAGICAL Fireworks + Flowers Explosion!
        function magicalCelebration() {
            const fwCanvas = document.getElementById('fireworks');
            const fwCtx = fwCanvas.getContext('2d');
            fwCanvas.width = window.innerWidth;
            fwCanvas.height = window.innerHeight;
            
            function createEpicFirework(x, y, colorSet) {
                const particles = [];
                for(let i = 0; i < 80; i++) {
                    particles.push({
                        x, y,
                        vx: (Math.random() - 0.5) * 15,
                        vy: (Math.random() - 0.5) * 15,
                        alpha: 1,
                        life: 90,
                        size: Math.random() * 8 + 3,
                        type: Math.random() > 0.5 ? 'firework' : 'flower',
                        color: colorSet[Math.floor(Math.random() * colorSet.length)]
                    });
                }
                
                function updateExplosion() {
                    fwCtx.clearRect(0, 0, fwCanvas.width, fwCanvas.height);
                    
                    particles.forEach((p, i) => {
                        p.x += p.vx;
                        p.y += p.vy;
                        p.vy += 0.15;
                        p.alpha -= 1 / p.life;
                        p.life--;
                        p.size *= 0.995;
                        
                        if(p.life <= 0) {
                            particles.splice(i, 1);
                            return;
                        }
                        
                        fwCtx.save();
                        fwCtx.globalAlpha = p.alpha;
                        fwCtx.fillStyle = p.color;
                        
                        if(p.type === 'flower') {
                            // Flower petal shape
                            fwCtx.save();
                            fwCtx.translate(p.x, p.y);
                            for(let j = 0; j < 5; j++) {
                                fwCtx.rotate(Math.PI * 2 / 5);
                                fwCtx.beginPath();
                                fwCtx.arc(0, -p.size, p.size/2, 0, Math.PI);
                                fwCtx.fill();
                            }
                            fwCtx.restore();
                        } else {
                            // Spark
                            fwCtx.beginPath();
                            fwCtx.arc(p.x, p.y, p.size, 0, Math.PI * 2);
                            fwCtx.fill();
                        }
                        fwCtx.restore();
                    });
                    
                    if(particles.length > 0) requestAnimationFrame(updateExplosion);
                }
                updateExplosion();
            }
            
            // Launch 8 synchronized fireworks with flower explosions
            const colors = [
                ['#ff6b9d', '#ff1493', '#ffc0cb'], // Pink
                ['#ffd93d', '#ff8c00', '#ffed4e'], // Gold/Orange  
                ['#6bcf7f', '#32cd32', '#90ee90'], // Green
                ['#4ecdc4', '#00ced1', '#87cefa']  // Cyan/Blue
            ];
            
            for(let i = 0; i < 8; i++) {
                setTimeout(() => {
                    createEpicFirework(
                        (fwCanvas.width * 0.2) + (i * fwCanvas.width * 0.12),
                        fwCanvas.height * 0.3,
                        colors[Math.floor(Math.random() * colors.length)]
                    );
                }, i * 400);
            }
        }

        window.addEventListener('resize', () => {
            starsCanvas.width = petalsCanvas.width = document.getElementById('fireworks').width = window.innerWidth;
            starsCanvas.height = petalsCanvas.height = document.getElementById('fireworks').height = window.innerHeight;
        });
    </script>
</body>
</html>
