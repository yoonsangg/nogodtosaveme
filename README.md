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
      background-image: url('data:image/png;base64,iVBORw0KGgoAAAANgIAAADuBgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVR42mOAAoH+DwADpwIDt7Lq3AAAAABJRU5GOgg=='); /* 미세 조정 */
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

    /* h1: Anton 폰트 적용 및 디스트로이드 텍스처 효과 */
    h1 {
      font-family: 'Anton', sans-serif; /* 폰트 변경! */
      font-size: 4.5em;
      letter-spacing: 5px;
      margin-bottom: 0.4em;
      font-weight: 400; /* Anton은 보통 400 굵기만 지원합니다. */
      text-transform: uppercase;
      color: #fff; /* background-clip 때문에 투명해지지만 기본 색은 흰색 */
      position: relative;
      animation: glitch 2s infinite;

      /* 디스트로이드 질감 오버레이를 위한 속성 */
      background: url('https://raw.githubusercontent.com/wrtn-community/wrtn/main/grunge-texture.png'); /* 거친 질감 이미지 */
      background-size: cover; /* 텍스트 크기에 맞춰 질감 조정 */
      -webkit-background-clip: text; /* 텍스트 모양으로 배경 자르기 (WebKit 브라우저용) */
      background-clip: text; /* 텍스트 모양으로 배경 자르기 */
      -webkit-text-fill-color: transparent; /* 텍스트 채우기 색상을 투명하게 (WebKit 브록시) */
      text-fill-color: transparent; /* 텍스트 채우기 색상을 투명하게 */
      filter: drop-shadow(1px 1px 0 #d12e2e) drop-shadow(-1px -1px 0 #a0a0a0); /* 텍스트 그림자 효과 (glitch와 조화) */
    }

    h1::before,
    h1::after {
      content: attr(data-text);
      position: absolute;
      left: 0;
      width: 100%;
      overflow: hidden;
      clip: rect(0, 900px, 0, 0);
      /* text-fill-color를 적용한 글씨체에 이펙트도 투명하게 보일 수 있으니,
         글리치 복제본은 다시 흰색으로 채워줍니다. */
      -webkit-text-fill-color: #fff;
      text-fill-color: #fff;
      filter: none; /* 드롭 쉐도우 중복 방지 */
    }

    h1::before {
      animation: glitchTop 2s infinite;
      color: #f00; /* 빨간색 글리치 효과 */
      z-index: -1;
    }

    h1::after {
      animation: glitchBottom 2s infinite;
      color: #0ff; /* 청록색 글리치 효과 */
      z-index: -2;
    }

    @keyframes glitch {
      0% {
        filter: drop-shadow(1px 1px 0 #d12e2e) drop-shadow(-1px -1px 0 #a0a0a0);
      }
      20% {
        filter: drop-shadow(1px -1px 0 #d12e2e) drop-shadow(-1px 1px 0 #a0a0a0);
      }
      40% {
        filter: drop-shadow(-1px 1px 0 #d12e2e) drop-shadow(1px -1px 0 #a0a0a0);
      }
      60% {
        filter: drop-shadow(-1px -1px 0 #d12e2e) drop-shadow(1px 1px 0 #a0a0a0);
      }
      80%, 100% {
        filter: drop-shadow(1px 1px 0 #d12e2e) drop-shadow(-1px -1px 0 #a0a0a0);
      }
    }

    @keyframes glitchTop {
      0% {
        clip: rect(0, 9999px, 0, 0);
        transform: translate(0);
      }
      20% {
        clip: rect(0, 9999px, 10px, 0);
        transform: translate(-2px, -2px);
      }
      40% {
        clip: rect(0, 9999px, 0, 0);
        transform: translate(0);
      }
      60% {
        clip: rect(0, 9999px, 10px, 0);
        transform: translate(-2px, 2px);
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
        clip: rect(10px, 9999px, 20px, 0);
        transform: translate(2px, 2px);
      }
      40% {
        clip: rect(0, 9999px, 0, 0);
        transform: translate(0);
      }
      60% {
        clip: rect(10px, 9999px, 20px, 0);
        transform: translate(2px, -2px);
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

    /* 아이템 페이지 이동 버튼 스타일 */
    .shop-button {
      position: fixed;
      bottom: 25px; /* 하단에서부터의 거리 */
      right: 25px; /* 우측에서부터의 거리 */
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 15px 30px;
      background-color: #000;
      border: 2px solid #fff; /* 흰색 테두리 */
      color: #fff;
      font-family: 'Anton', sans-serif; /* 강렬한 폰트 사용 */
      font-size: 1.2em;
      letter-spacing: 2px;
      text-transform: uppercase;
      text-decoration: none;
      box-shadow: 0 0 10px rgba(255, 255, 255, 0.2); /* 은은한 흰색 그림자 */
      transition: background-color 0.3s ease, color 0.3s ease, border-color 0.3s ease, box-shadow 0.3s ease;
      z-index: 10; /* 다른 요소들 위에 보이도록 */
      cursor: pointer;
    }

    .shop-button:hover {
      background-color: #d12e2e; /* 호버 시 붉은색 배경 */
      color: #fff;
      border-color: #d12e2e; /* 호버 시 테두리 색상도 붉은색으로 */
      box-shadow: 0 0 15px rgba(209, 46, 46, 0.6); /* 붉은색으로 그림자 강조 */
    }

    /* 모바일 반응형 조절 */
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

      .shop-button {
        bottom: 15px;
        right: 15px;
        padding: 10px 20px;
        font-size: 1em;
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

  <!-- 아이템 페이지 이동 버튼 -->
  <a href="shop.html" class="shop-button">VIEW ITEMS</a>

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
