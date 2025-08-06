
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
      background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVR42mOAAoH+DwADpwIDt7Lq3AAAAABJRU1BUUVOgg==');
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

    /* h1: Anton 폰트 적용, 질감 제거 및 글리치 애니메이션 강도 조절 */
    h1 {
      font-family: 'Anton', sans-serif;
      font-size: 4.5em;
      letter-spacing: 5px;
      margin-bottom: 0.4em;
      font-weight: 400; /* Anton은 보통 400 굵기만 지원합니다. */
      text-transform: uppercase;
      color: #FFFFFF; /* 이제 텍스트 자체는 선명한 흰색입니다. */
      position: relative;
      animation: glitch 3s infinite; /* 애니메이션 속도 늦춤 */
      /* 질감 오버레이 관련 속성 제거 */
      /* background: url(...); */
      /* -webkit-background-clip: text; */
      /* background-clip: text; */
      /* -webkit-text-fill-color: transparent; */
      /* text-fill-color: transparent; */
    }

    h1::before,
    h1::after {
      content: attr(data-text);
      position: absolute;
      left: 0;
      width: 100%;
      overflow: hidden;
      clip: rect(0, 900px, 0, 0);
      color: #fff; /* 글리치 복제본은 여전히 흰색 */
      -webkit-text-fill-color: #fff;
      text-fill-color: #fff;
      filter: none; /* 그림자 중복 방지 */
    }

    h1::before {
      animation: glitchTop 3s infinite; /* 애니메이션 속도 맞춤 */
      color: #f00; /* 빨간색 글리치 효과 */
      z-index: -1;
    }

    h1::after {
      animation: glitchBottom 3s infinite; /* 애니메이션 속도 맞춤 */
      color: #0ff; /* 청록색 글리치 효과 */
      z-index: -2;
    }

    @keyframes glitch {
      0% {
        text-shadow: 1px 1px #d12e2e, -1px -1px #a0a0a0; /* 그림자 강도 조절 */
      }
      20% {
        text-shadow: 1px -1px #d12e2e, -1px 1px #a0a0a0;
      }
      40% {
        text-shadow: -1px 1px #d12e2e, 1px -1px #a0a0a0;
      }
      60% {
        text-shadow: -1px -1px #d12e2e, 1px 1px #a0a0a0;
      }
      80%, 100% {
        text-shadow: 1px 1px #d12e2e, -1px -1px #a0a0a0;
      }
    }

    @keyframes glitchTop {
      0% {
        clip: rect(0, 9999px, 0, 0);
        transform: translate(0);
      }
      20% {
        clip: rect(0, 9999px, 5px, 0); /* 잘림 범위 조절 */
        transform: translate(-1px, -1px); /* 이동 범위 조절 */
      }
      40% {
        clip: rect(0, 9999px, 0, 0);
        transform: translate(0);
      }
      60% {
        clip: rect(0, 9999px, 5px, 0);
        transform: translate(-1px, 1px);
      }
      80%, 100% {
        clip: rect(0, 9999px, 0, 0);
        transform: translate(0);
      }
    }

    @keyframes glitchBottom {
      0% {
        clip: rect(0, 9999px, 0, 0);
        transform: translate(0);
      }
      20% {
        clip: rect(5px, 9999px, 10px, 0); /* 잘림 범위 조절 */
        transform: translate(1px, 1px); /* 이동 범위 조절 */
      }
      40% {
        clip: rect(0, 9999px, 0, 0);
        transform: translate(0);
      }
      60% {
        clip: rect(5px, 9999px, 10px, 0);
        transform: translate(1px, -1px);
      }
      80%, 100% {
        clip: rect(0, 9999px, 0, 0);
        transform: translate(0);
      }
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
    <h1 data-text="NO GOD TO SAVE ME">NO GOD TO SAVE ME</h1>
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
