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

  <!-- Google Font (Alternative to Helvetica Neue) -->
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap" rel="stylesheet">

  <style>
    /* === Reset & Base === */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background-color: #000;
      color: #fff;
      font-family: 'Roboto', sans-serif;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      text-align: center;
      overflow: hidden;
      padding: 2rem;
      animation: fadeIn 1.5s ease-out;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }

    h1 {
      font-size: 3.5em;
      letter-spacing: 3px;
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
    }

    .contact a {
      color: #ccc;
      text-decoration: none;
      transition: color 0.3s ease;
    }

    .contact a:hover {
      color: #fff;
    }

    /* Responsive Design */
    @media (max-width: 768px) {
      h1 {
        font-size: 2.2em;
      }

      p.tagline {
        font-size: 1em;
        padding: 0 1em;
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
</body>
</html>
