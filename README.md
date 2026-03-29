<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Questions for My Partner</title>
  <style>
    :root {
      --bg1: #ffdde1;
      --bg2: #ee9ca7;
      --card: rgba(255,255,255,0.88);
      --text: #2b2b2b;
      --accent: #ff5c8a;
      --accent2: #ff8fb1;
      --shadow: 0 20px 50px rgba(0,0,0,0.15);
    }

    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: Arial, Helvetica, sans-serif;
      min-height: 100vh;
      display: grid;
      place-items: center;
      background: linear-gradient(135deg, var(--bg1), var(--bg2));
      color: var(--text);
      padding: 20px;
    }

    .container {
      width: min(700px, 100%);
      background: var(--card);
      border-radius: 24px;
      box-shadow: var(--shadow);
      overflow: hidden;
      backdrop-filter: blur(8px);
    }

    .header {
      padding: 28px 24px 18px;
      text-align: center;
      background: linear-gradient(135deg, #fff 0%, #fff7fa 100%);
      border-bottom: 1px solid rgba(0,0,0,0.05);
    }

    .header h1 {
      margin: 0;
      font-size: 2rem;
      color: var(--accent);
    }

    .header p {
      margin: 10px 0 0;
      line-height: 1.5;
      font-size: 1rem;
      color: #555;
    }

    .progress-wrap {
      padding: 0 24px 20px;
    }

    .progress-bar {
      width: 100%;
      height: 10px;
      border-radius: 999px;
      background: #f3d5dd;
      overflow: hidden;
    }

    .progress {
      height: 100%;
      width: 0%;
      background: linear-gradient(90deg, var(--accent), var(--accent2));
      transition: width 0.35s ease;
    }

    .quiz {
      padding: 0 24px 24px;
    }

    .question-card {
      display: none;
      animation: fadeIn 0.3s ease;
    }

    .question-card.active {
      display: block;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .q-number {
      font-size: 0.9rem;
      color: #777;
      margin-bottom: 8px;
    }

    .q-text {
      font-size: 1.35rem;
      line-height: 1.5;
      margin: 0 0 18px;
      color: #222;
    }

    .options {
      display: grid;
      gap: 12px;
    }

    .option {
      border: 2px solid #f0c9d5;
      background: #fff;
      padding: 14px 16px;
      border-radius: 16px;
      cursor: pointer;
      font-size: 1rem;
      transition: 0.2s ease;
      text-align: left;
    }

    .option:hover {
      transform: translateY(-1px);
      border-color: var(--accent);
      box-shadow: 0 8px 18px rgba(255,92,138,0.12);
    }

    .option.selected {
      border-color: var(--accent);
      background: #fff0f5;
      font-weight: bold;
    }

    .nav {
      display: flex;
      justify-content: space-between;
      gap: 12px;
      padding: 0 24px 24px;
    }

    button {
      border: none;
      border-radius: 14px;
      padding: 12px 18px;
      font-size: 1rem;
      cursor: pointer;
      transition: 0.2s ease;
    }

    .btn {
      background: var(--accent);
      color: white;
    }

    .btn:hover { opacity: 0.92; }

    .btn-secondary {
      background: #f4f4f4;
      color: #333;
    }

    .btn:disabled, .btn-secondary:disabled {
      opacity: 0.5;
      cursor: not-allowed;
    }

    .result {
      display: none;
      padding: 24px;
      text-align: center;
    }

    .result h2 {
      color: var(--accent);
      margin-top: 0;
      font-size: 2rem;
    }

    .result p {
      font-size: 1.05rem;
      line-height: 1.7;
      color: #444;
    }

    .footer-note {
      padding: 0 24px 24px;
      text-align: center;
      color: #777;
      font-size: 0.92rem;
    }

    @media (max-width: 540px) {
      .header h1 { font-size: 1.6rem; }
      .q-text { font-size: 1.15rem; }
      .nav { flex-direction: column; }
      button { width: 100%; }
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="header">
      <h1>Questions for My Partner 💖</h1>
      <p>A cute little quiz to make us smile, laugh, and feel closer.</p>
    </div>

    <div class="progress-wrap">
      <div class="progress-bar">
        <div class="progress" id="progress"></div>
      </div>
    </div>

    <div class="quiz" id="quiz">
      <div class="question-card active" data-question="0">
        <div class="q-number">Question 1 of 5</div>
        <div class="q-text">What is the cutest thing I do that makes you smile?</div>
        <div class="options">
          <button class="option">My smile</button>
          <button class="option">My messages</button>
          <button class="option">My teasing</button>
          <button class="option">Everything about me</button>
        </div>
      </div>

      <div class="question-card" data-question="1">
        <div class="q-number">Question 2 of 5</div>
        <div class="q-text">What is your favorite thing to do with me?</div>
        <div class="options">
          <button class="option">Talk for hours</button>
          <button class="option">Go on a date</button>
          <button class="option">Watch movies</button>
          <button class="option">Just be together</button>
        </div>
      </div>

      <div class="question-card" data-question="2">
        <div class="q-number">Question 3 of 5</div>
        <div class="q-text">What kind of partner am I to you?</div>
        <div class="options">
          <button class="option">Sweet</button>
          <button class="option">Funny</button>
          <button class="option">Caring</button>
          <button class="option">All of the above</button>
        </div>
      </div>

      <div class="question-card" data-question="3">
        <div class="q-number">Question 4 of 5</div>
        <div class="q-text">What should we never stop doing?</div>
        <div class="options">
          <button class="option">Making memories</button>
          <button class="option">Supporting each other</button>
          <button class="option">Laughing together</button>
          <button class="option">All of these</button>
        </div>
      </div>

      <div class="question-card" data-question="4">
        <div class="q-number">Question 5 of 5</div>
        <div class="q-text">How much do I mean to you?</div>
        <div class="options">
          <button class="option">A little</button>
          <button class="option">A lot</button>
          <button class="option">A very lot</button>
          <button class="option">More than words can explain</button>
        </div>
      </div>
    </div>

    <div class="nav">
      <button class="btn-secondary" id="prevBtn" disabled>Previous</button>
      <button class="btn" id="nextBtn">Next</button>
    </div>

    <div class="result" id="result">
      <h2>That was sweet 💕</h2>
      <p>
        Thank you for answering my little questions.<br />
        No matter what, you are special to me and I’ll always cherish you.
      </p>
      <p><strong>Made with love for my favorite person.</strong></p>
      <button class="btn" onclick="restartQuiz()">Play Again</button>
    </div>

    <div class="footer-note">
      You can edit the questions inside the HTML file anytime.
    </div>
  </div>

  <script>
    const cards = document.querySelectorAll(".question-card");
    const progress = document.getElementById("progress");
    const prevBtn = document.getElementById("prevBtn");
    const nextBtn = document.getElementById("nextBtn");
    const quiz = document.getElementById("quiz");
    const result = document.getElementById("result");

    let current = 0;
    const answers = new Array(cards.length).fill(null);

    function showQuestion(index) {
      cards.forEach((card, i) => {
        card.classList.toggle("active", i === index);
      });

      progress.style.width = `${(index / cards.length) * 100}%`;
      prevBtn.disabled = index === 0;
      nextBtn.textContent = index === cards.length - 1 ? "Finish" : "Next";
    }

    cards.forEach((card, index) => {
      const options = card.querySelectorAll(".option");
      options.forEach((option) => {
        option.addEventListener("click", () => {
          options.forEach((opt) => opt.classList.remove("selected"));
          option.classList.add("selected");
          answers[index] = option.textContent;
        });
      });
    });

    nextBtn.addEventListener("click", () => {
      if (current < cards.length - 1) {
        current++;
        showQuestion(current);
      } else {
        document.querySelector(".quiz").style.display = "none";
        document.querySelector(".nav").style.display = "none";
        document.querySelector(".progress-wrap").style.display = "none";
        result.style.display = "block";
        progress.style.width = "100%";
      }
    });

    prevBtn.addEventListener("click", () => {
      if (current > 0) {
        current--;
        showQuestion(current);
      }
    });

    function restartQuiz() {
      current = 0;
      answers.fill(null);
      document.querySelectorAll(".option").forEach((opt) => opt.classList.remove("selected"));
      document.querySelector(".quiz").style.display = "block";
      document.querySelector(".nav").style.display = "flex";
      document.querySelector(".progress-wrap").style.display = "block";
      result.style.display = "none";
      showQuestion(current);
    }

    window.restartQuiz = restartQuiz;
    showQuestion(current);
  </script>
</body>
</html>
