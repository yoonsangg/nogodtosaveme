
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

  <!-- Google Font: Anton (그로테스크하고 강렬한 느낌) -->
  <link href="https://fonts.googleapis.com/css2?family=Anton&display=swap" rel="stylesheet">
  <!-- Google Font: Bebas Neue (기존 유지, fallback이나 다른 텍스트에 사용) -->
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap" rel="stylesheet">


  <style>
    /* === Reset & Base === */
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
      font-family: 'Bebas Neue', sans-serif; /* 기본 폰트는 Bebas Neue 유지 (Anton은 제목에만) */
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

    /* 배경 오버레이 */
    body::before {
      content: '';
      position: absolute;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background-color: rgba(0, 0, 0, 0.7);
      z-index: -1;
    }

    /* 미세 노이즈 효과 */
    body::after {
      content: '';
      position: fixed;
      top: 0; left: 0;
      width: 100vw; height: 100vh;
      pointer-events: none;
      background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVR42mOAAoH+DwADpwIDt7Lq3AAAAABJRUVOgg==');
      background-blend-mode: overlay;
      filter: url(#noiseFilter);
      opacity: 0.03;
      animation: grain 8s steps(10) infinite;
      z-index: 2;
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

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* h1: Anton 폰트 적용, 글리치 효과 간소화 */
    h1 {
      font-family: 'Anton', sans-serif;
      font-size: 4.5em;
      letter-spacing: 5px;
      margin-bottom: 0.4em;
      font-weight: 400; /* Anton은 보통 400 굵기만 지원합니다. */
      text-transform: uppercase;
      color: #FFFFFF; /* 텍스트 자체를 선명한 흰색으로 표시 */
      position: relative;
      animation: simplifiedGlitch 4s infinite alternate; /* 새로운 애니메이션 적용 */
      /* 이전에 텍스트에 직접 적용되었던 질감 오버레이 속성들은 제거 */
      /* background, background-size, -webkit-background-clip, background-clip, -webkit-text-fill-color, text-fill-color 제거됨 */
    }

    /* h1::before, h1::after 및 관련 keyframes (glitchTop, glitchBottom) 완전히 제거 */
    /* 더 이상 이 가상 요소들을 사용하지 않습니다. */

    @keyframes simplifiedGlitch {
      0%, 100% {
        text-shadow: none; /* 기본 상태에서는 그림자 없음 */
        transform: translate(0, 0);
      }
      5%, 15% { /* 불규칙한 순간에만 짧게 글리치 효과 */
        text-shadow: 0.5px 0.5px #d12e2e, -0.5px -0.5px #a0a0a0; /* 미세한 그림자 */
        transform: translate(0.5px, 0.5px); /* 미세한 위치 이동 */
      }
      10% {
        text-shadow: 0.5px -0.5px #d12e2e, -0.5px 0.5px #a0a0a0;
        transform: translate(-0.5px, 0.5px);
      }
      20% {
        text-shadow: 0 0 1px rgba(255, 255, 255, 0.8); /* 약한 흐림 효과 */
        transform: translate(0, 0);
      }
      30%, 35% {
        text-shadow: 0.2px 0.2px #d12e2e; /* 아주 미세한 그림자 */
        transform: translate(0.2px, -0.2px);
      }
      40% {
        text-shadow: none;
        transform: translate(0, 0);
      }
      /* 나머지 시간은 그림자나 변형 없이 선명하게 표시 */
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
