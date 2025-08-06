<!DOCTYPE html>
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

  <!-- Google Font: Bebas Neue (더 강렬하고 무게감 있는 느낌) -->
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap" rel="stylesheet">

  <style>
    /* === Reset & Base === */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background-color: #000; /* 기본 배경은 검은색 */
      /* 배경 질감 이미지 (예시: 거친 콘크리트 질감) - 실제 경로로 변경해주세요 */
      background-image: url('https://raw.githubusercontent.com/wrtn-community/wrtn/main/concrete-texture.webp');
      background-size: cover;
      background-repeat: no-repeat;
      background-position: center center;

      color: #f0f0f0; /* 순수한 흰색 대신 살짝 탁한 흰색으로 변경 */
      font-family: 'Bebas Neue', sans-serif; /* Bebas Neue 폰트 적용 */
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      text-align: center;
      overflow: hidden; /* 배경 애니메이션 시 스크롤바 방지 */
      padding: 2rem;
      position: relative; /* ::before, ::after 가상 요소를 위한 기준점 */
      z-index: 0; /* z-index 설정으로 오버레이 컨트롤 용이 */
    }

    /* 배경 위에 반투명 검은색 오버레이 (텍스트 가독성 및 어두운 분위기 강조) */
    body::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.7); /* 70% 투명도의 검은색 오버레이 */
      z-index: -1; /* 배경 이미지와 body 사이, 콘텐츠 아래에 위치 */
    }

    /* 전체 화면에 미세한 노이즈 효과 */
    body::after {
      content: '';
      position: fixed; /* 전체 화면에 고정 */
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      pointer-events: none; /* 클릭 이벤트 방지 */
      /* 아주 작은 투명 PNG 이미지를 데이터 URI로 사용 (성능 최적화) */
      background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAYAAAAfFcSJAAAADUlEQVR42mOAAoH+DwADpwIDt7Lq3AAAAABJRU5ErkJggg==');
      background-blend-mode: overlay; /* 오버레이 모드로 질감 적용 */
      filter: url(#noiseFilter); /* SVG 필터 적용 */
      opacity: 0.03; /* 아주 미묘하게 보일 정도로 투명도 조절 */
      animation: grain 8s steps(10) infinite; /* 움직이는 노이즈 효과 */
      z-index: 2; /* 콘텐츠 위에 있지만 투명도가 낮음 */
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
      animation: fadeIn 1.5s ease-out; /* main 콘텐츠에 fadeIn 애니메이션 적용 */
      z-index: 1; /* 콘텐츠가 오버레이 위로 오도록 */
    }

    h1 {
      color: #FFFFFF; /* 🎉 글씨색을 순수 흰색으로 확실히 지정합니다. */
      font-size: 4.5em; /* 폰트 변경에 따라 크기 조절 */
      letter-spacing: 5px; /* 더 강조된 자간 */
      margin-bottom: 0.4em;
      font-weight: 700; /* Bebas Neue는 단일 굵기지만, 시각적으로 강렬함 */
      text-transform: uppercase;
      /* 여기에서 text-shadow 속성을 완전히 제거했습니다! */
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
      margin-top: 4em; /* 위쪽 여백 증가 */
      align-self: flex-end; /* 기본적으로 오른쪽에 붙도록 (flex-direction: column일 때) */
      margin-right: 5%; /* 오른쪽 여백 추가 */
    }

    .contact a {
      color: #a0a0a0; /* 링크 기본 색상: 약간 더 어둡게 */
      text-decoration: none;
      transition: color 0.3s ease;
    }

    .contact a:hover {
      color: #d12e2e; /* 호버 시 녹슨 붉은색 계열로 변경하여 악센트 효과 */
    }

    /* Responsive Design */
    @media (max-width: 768px) {
      h1 {
        font-size: 2.5em; /* 모바일에서 폰트 크기 조절 */
        letter-spacing: 3px;
      }

      p.tagline {
        font-size: 1em;
        padding: 0 1em;
      }

      .contact {
        align-self: center; /* 모바일에서는 다시 중앙 정렬 */
        margin-right: 0;
        margin-top: 2em; /* 모바일 여백 조절 */
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

  <!-- SVG 필터 정의 (미세한 노이즈 효과를 위한 코드) -->
  <svg style="position: absolute; width: 0; height: 0;">
    <filter id="noiseFilter">
      <feTurbulence type="fractalNoise" baseFrequency="0.6" numOctaves="3" stitchTiles="stitch" />
      <feColorMatrix type="saturate" values="0" />
      <feBlend in="SourceGraphic" in2="noise" mode="multiply" />
    </filter>
  </svg>
</body>
</html>
