
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="description" content="No god to save me — A brand born from nothing for those who save themselves." />
  <meta property="og:title" content="no god to save me" />
  <meta property="og:description" content="A brand born from nothing — for those who save themselves." />
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://yourbrand.com" />
  <meta property="og:image" content="https://yourbrand.com/og-image.jpg" />

  <title>no god to save me</title>

  <!-- Google Font: Bebas Neue -->
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap" rel="stylesheet">

  <style>
    /* 기존 스타일 유지 */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background-color: #000;
      background-image: url('https://raw.githubusercontent.com/wrtn-community/wrtn/main/concrete-texture.webp');
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center center;

      color: #f0f0f0;
      font-family: 'Bebas Neue', sans-serif;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      text-align: center;
      overflow: hidden;
      padding: 2rem;
      position: relative;
      z-index: 0;
    }

    body::before {
      content: '';
      position: absolute;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background-color: rgba(0, 0, 0, 0.7);
      z-index: -1;
    }

    body::after {
      content: '';
      position: fixed;
      top: 0; left: 0;
      width: 100vw; height: 100vh;
      pointer-events: none;
      background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVR42mOAAoH+DwADpwIDt7Lq3AAAAABJRU5ErkJggg==');
      background-blend-mode: overlay;
      filter: url(#noiseFilter);
      opacity: 0.03;
      animation: grain 8s steps(10) infinite;
      z-index: 2;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @keyframes grain {
      0%, 100% { transform: translate(0, 0); }
      10% { transform: translate(-5%, -10%); }
      20% { transform: translate(-15%, 10%); }
      30% { transform: translate(7%, -15%); }
      40% { transform: translate(-10%, 8%); }
      50% { transform: translate(12%, -7%); }
      60% { transform: translate(-8%, 5%); }
      70% { transform: translate(4%, -12%); }
      80% { transform: translate(-14%, 6%); }
      90% { transform: translate(6%, -9%); }
    }

    main {
      animation: fadeIn 1.5s ease-out;
      z-index: 1;
    }

    h1 {
      color: #FFFFFF;
      font-size: 4.5em;
      letter-spacing: 5px;
      margin-bottom: 0.4em;
      font-weight: 700;
      text-transform: uppercase;
    }

    p.tagline {
      font-size: 1.3em;
      max-width: 700px;
      margin: 0 auto 2em auto;
      line-height: 1.6em;
      color: #bbb;
    }

    .contact {
      font-size: 0.95em;
      color: #888;
      margin-top: 4em;
      align-self: flex-end;
      margin-right: 5%;
    }

    .contact a {
      color: #a0a0a0;
      text-decoration: none;
      transition: color 0.3s ease;
    }

    .contact a:hover {
      color: #d12e2e;
    }

    /* 파란색 글씨 숨기기 */
    .container-lg.markdown-body {
      display: none !important;
    }

    @media (max-width: 768px) {
      h1 {
        font-size: 2.5em;
        letter-spacing: 3px;
      }

      p.tagline {
        font-size: 1em;
        padding: 0 1em;
      }

      .contact {
        align-self: center;
        margin-right: 0;
        margin-top: 2em;
      }
    }
  </style>
</head>

<body>
  <!-- 파란색 글씨가 포함된 div는 CSS로 숨김 처리되어 화면에 보이지 않습니다 -->

  <main>
    <h1>no god to save me</h1>
    <p class="tagline">a brand born from nothing — for those who save themselves.</p>

    <div class="contact">
      <p>contact: <a href="mailto:your@email.com">your@email.com</a></p>
      <p><a href="https://instagram.com/no_god_to_save_me" target="_blank" rel="noopener noreferrer">Instagram</a></p>
    </div>
  </main>

  <!-- SVG 필터 정의 -->
  <svg style="position: absolute; width: 0; height: 0;">
    <filter id="noiseFilter">
      <feTurbulence type="fractalNoise" baseFrequency="0.6" numOctaves="3" stitchTiles="stitch" />
      <feColorMatrix type="saturate" values="0" />
      <feBlend in="SourceGraphic" in2="noise" mode="multiply" />
    </filter>
  </svg>
</body>
</html>
