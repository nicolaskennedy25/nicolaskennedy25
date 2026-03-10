<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Banner Nicolas Kennedy</title>
<link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@500;600;700&family=Exo+2:wght@300;400;600;700&display=swap" rel="stylesheet">
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: #0a0a0a;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    font-family: 'Exo 2', sans-serif;
  }

  .banner {
    width: 1200px;
    height: 400px;
    background: #000;
    border-radius: 12px;
    overflow: hidden;
    position: relative;
    display: flex;
    align-items: center;
    border: 1px solid rgba(0, 120, 255, 0.2);
    box-shadow: 0 0 60px rgba(0, 100, 255, 0.15), 0 0 120px rgba(0, 60, 200, 0.08);
  }

  /* Fondo animado con circuitos */
  .circuit-bg {
    position: absolute;
    inset: 0;
    background: 
      radial-gradient(ellipse at 20% 50%, rgba(0, 80, 220, 0.12) 0%, transparent 60%),
      radial-gradient(ellipse at 80% 50%, rgba(0, 40, 150, 0.08) 0%, transparent 60%);
  }

  /* Grid lines de fondo */
  .grid-lines {
    position: absolute;
    inset: 0;
    background-image: 
      linear-gradient(rgba(0, 100, 255, 0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0, 100, 255, 0.04) 1px, transparent 1px);
    background-size: 40px 40px;
  }

  /* Divisor central */
  .divider {
    position: absolute;
    left: 50%;
    top: 10%;
    height: 80%;
    width: 1px;
    background: linear-gradient(to bottom, transparent, rgba(0, 120, 255, 0.6), rgba(0, 180, 255, 0.8), rgba(0, 120, 255, 0.6), transparent);
    transform: translateX(-50%);
    z-index: 5;
  }

  .divider::after {
    content: '';
    position: absolute;
    left: -2px;
    top: 50%;
    transform: translateY(-50%);
    width: 5px;
    height: 30px;
    background: rgba(0, 180, 255, 0.9);
    border-radius: 3px;
    box-shadow: 0 0 10px rgba(0, 180, 255, 0.8);
  }

  /* ======= LADO IZQUIERDO - LOGO ======= */
  .left-side {
    width: 50%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    z-index: 2;
  }

  .logo-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0;
    animation: fadeInLeft 0.8s ease forwards;
  }

  @keyframes fadeInLeft {
    from { opacity: 0; transform: translateX(-30px); }
    to { opacity: 1; transform: translateX(0); }
  }

  .logo-img {
    width: 280px;
    height: 280px;
    object-fit: contain;
    filter: drop-shadow(0 0 20px rgba(0, 120, 255, 0.4));
  }

  /* ======= LADO DERECHO - TECNOLOGÍAS ======= */
  .right-side {
    width: 50%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 30px 40px;
    position: relative;
    z-index: 2;
    animation: fadeInRight 0.8s ease 0.3s both;
  }

  @keyframes fadeInRight {
    from { opacity: 0; transform: translateX(30px); }
    to { opacity: 1; transform: translateX(0); }
  }

  .tech-container {
    width: 100%;
  }

  .tech-title {
    font-family: 'Rajdhani', sans-serif;
    font-size: 22px;
    font-weight: 700;
    letter-spacing: 6px;
    text-transform: uppercase;
    color: #fff;
    margin-bottom: 22px;
    position: relative;
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .tech-title::before {
    content: '';
    display: inline-block;
    width: 4px;
    height: 22px;
    background: linear-gradient(to bottom, #0078ff, #00c8ff);
    border-radius: 2px;
    box-shadow: 0 0 8px rgba(0, 180, 255, 0.7);
    flex-shrink: 0;
  }

  .tech-title .title-accent {
    color: #3399ff;
    text-shadow: 0 0 12px rgba(0, 150, 255, 0.6);
  }

  .tech-section {
    margin-bottom: 18px;
  }

  .section-label {
    font-family: 'Exo 2', sans-serif;
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: rgba(100, 170, 255, 0.7);
    margin-bottom: 10px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .section-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: linear-gradient(to right, rgba(0, 120, 255, 0.4), transparent);
  }

  .tags-row {
    display: flex;
    flex-wrap: wrap;
    gap: 7px;
  }

  .tag {
    padding: 5px 12px;
    border-radius: 4px;
    font-family: 'Rajdhani', sans-serif;
    font-size: 13px;
    font-weight: 600;
    letter-spacing: 0.5px;
    color: #fff;
    position: relative;
    transition: all 0.25s ease;
    cursor: default;
    animation: tagAppear 0.5s ease both;
  }

  @keyframes tagAppear {
    from { opacity: 0; transform: scale(0.85); }
    to { opacity: 1; transform: scale(1); }
  }

  /* Variantes de color por tecnología */
  .tag.js {
    background: rgba(247, 200, 0, 0.1);
    border: 1px solid rgba(247, 200, 0, 0.35);
    color: #f7c800;
    text-shadow: 0 0 8px rgba(247, 200, 0, 0.4);
  }
  .tag.php {
    background: rgba(119, 123, 179, 0.12);
    border: 1px solid rgba(119, 123, 179, 0.4);
    color: #a8aaff;
  }
  .tag.mysql {
    background: rgba(0, 163, 228, 0.1);
    border: 1px solid rgba(0, 163, 228, 0.35);
    color: #00a3e4;
  }
  .tag.html {
    background: rgba(228, 77, 38, 0.1);
    border: 1px solid rgba(228, 77, 38, 0.35);
    color: #e44d26;
  }
  .tag.css {
    background: rgba(21, 114, 182, 0.12);
    border: 1px solid rgba(21, 114, 182, 0.4);
    color: #4db8ff;
  }
  .tag.java {
    background: rgba(237, 84, 62, 0.1);
    border: 1px solid rgba(237, 84, 62, 0.35);
    color: #ed543e;
  }
  .tag.win {
    background: rgba(0, 120, 212, 0.1);
    border: 1px solid rgba(0, 120, 212, 0.35);
    color: #0078d4;
  }
  .tag.mac {
    background: rgba(180, 180, 180, 0.08);
    border: 1px solid rgba(200, 200, 200, 0.25);
    color: #c8c8c8;
  }
  .tag.linux {
    background: rgba(255, 165, 0, 0.08);
    border: 1px solid rgba(255, 165, 0, 0.3);
    color: #ffa500;
  }

  .tag:hover {
    transform: translateY(-2px) scale(1.05);
    box-shadow: 0 4px 15px rgba(0, 120, 255, 0.2);
    filter: brightness(1.2);
  }

  /* Línea decorativa inferior */
  .bottom-bar {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    height: 2px;
    background: linear-gradient(to right, transparent, #0050cc, #00aaff, #0050cc, transparent);
  }

  /* Puntos de circuito decorativos */
  .circuit-dots {
    position: absolute;
    bottom: 15px;
    left: 30px;
    right: 30px;
    height: 30px;
    opacity: 0.15;
    background-image: 
      radial-gradient(circle, #0078ff 1px, transparent 1px),
      radial-gradient(circle, #00aaff 1px, transparent 1px);
    background-size: 20px 20px, 40px 40px;
    background-position: 0 0, 10px 10px;
  }

  /* Esquinas decorativas */
  .corner {
    position: absolute;
    width: 20px;
    height: 20px;
    z-index: 10;
  }
  .corner.tl { top: 8px; left: 8px; border-top: 2px solid #0078ff; border-left: 2px solid #0078ff; }
  .corner.tr { top: 8px; right: 8px; border-top: 2px solid #0078ff; border-right: 2px solid #0078ff; }
  .corner.bl { bottom: 8px; left: 8px; border-bottom: 2px solid #0078ff; border-left: 2px solid #0078ff; }
  .corner.br { bottom: 8px; right: 8px; border-bottom: 2px solid #0078ff; border-right: 2px solid #0078ff; }

  /* Pulse glow animado */
  @keyframes pulse {
    0%, 100% { opacity: 0.4; }
    50% { opacity: 0.9; }
  }
  .divider { animation: pulse 3s ease-in-out infinite; }

  /* Stagger delays tags */
  .tag:nth-child(1) { animation-delay: 0.4s; }
  .tag:nth-child(2) { animation-delay: 0.5s; }
  .tag:nth-child(3) { animation-delay: 0.6s; }
  .tag:nth-child(4) { animation-delay: 0.7s; }
  .tag:nth-child(5) { animation-delay: 0.8s; }
  .tag:nth-child(6) { animation-delay: 0.9s; }
</style>
</head>
<body>

<div class="banner">
  <!-- Fondos decorativos -->
  <div class="circuit-bg"></div>
  <div class="grid-lines"></div>
  <div class="circuit-dots"></div>
  <div class="bottom-bar"></div>

  <!-- Esquinas -->
  <div class="corner tl"></div>
  <div class="corner tr"></div>
  <div class="corner bl"></div>
  <div class="corner br"></div>

  <!-- Divisor central -->
  <div class="divider"></div>

  <!-- ===== IZQUIERDA: LOGO ===== -->
  <div class="left-side">
    <div class="logo-container">
      <img 
        class="logo-img" 
        src="/mnt/user-data/uploads/1773119808572_image.png" 
        alt="Nicolas Kennedy Logo"
      />
    </div>
  </div>

  <!-- ===== DERECHA: TECNOLOGÍAS ===== -->
  <div class="right-side">
    <div class="tech-container">

      <div class="tech-title">
        <span>TECNO<span class="title-accent">LOGÍAS</span></span>
      </div>

      <div class="tech-section">
        <div class="section-label">Lenguajes</div>
        <div class="tags-row">
          <span class="tag js">JavaScript</span>
          <span class="tag php">PHP</span>
          <span class="tag mysql">MySQL</span>
          <span class="tag html">HTML5</span>
          <span class="tag css">CSS</span>
          <span class="tag java">Java</span>
        </div>
      </div>

      <div class="tech-section">
        <div class="section-label">Sistemas Operativos</div>
        <div class="tags-row">
          <span class="tag win">Windows</span>
          <span class="tag mac">macOS</span>
          <span class="tag linux">Linux</span>
        </div>
      </div>

    </div>
  </div>

</div>

</body>
</html>
