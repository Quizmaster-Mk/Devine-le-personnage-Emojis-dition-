<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<title>Quiz : Devine le personnage</title>
<style>
  body {
    font-family: 'Segoe UI', sans-serif;
    background: #111;
    color: #fff;
    text-align: center;
    padding: 20px;
  }
  h1 { color: #ff4444; margin-bottom: 30px; }
  .quiz-box {
    background: #222;
    border-radius: 12px;
    max-width: 400px;
    margin: 0 auto;
    padding: 25px;
    box-shadow: 0 0 15px rgba(255,0,0,0.3);
  }
  .emoji {
    font-size: 40px;
    margin-bottom: 20px;
  }
  button {
    background: #ff4444;
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 8px;
    font-size: 16px;
    cursor: pointer;
    transition: 0.2s;
  }
  button:hover { background: #ff6666; }
  .answer {
    margin-top: 20px;
    font-weight: bold;
    color: #00ff99;
    font-size: 18px;
    min-height: 30px;
  }
</style>
</head>
<body>

<h1>🦸 Quiz : Devine le personnage</h1>

<div class="quiz-box">
  <div class="emoji" id="emoji">🕷️🕸️📸</div>
  <button onclick="showAnswer()">Afficher la réponse</button>
  <div class="answer" id="answer"></div>
  <hr style="margin:20px 0; border-color:#444;">
  <button onclick="nextQuestion()">Question suivante ▶️</button>
</div>

<script>
const questions = [
  { emojis: "🕷️🕸️📸", answer: "Spider-Man" },
  { emojis: "🛡️🇺🇸⭐", answer: "Captain America" },
  { emojis: "🃏🤡💣", answer: "Joker" },
  { emojis: "🦇🌃💔", answer: "Batman" },
  { emojis: "⚡🟥👊", answer: "Flash" },
  { emojis: "👑🐆🌍", answer: "Black Panther" }
];

let current = 0;

function showAnswer() {
  document.getElementById("answer").innerText = "Réponse : " + questions[current].answer;
}

function nextQuestion() {
  current = (current + 1) % questions.length;
  document.getElementById("emoji").innerText = questions[current].emojis;
  document.getElementById("answer").innerText = "";
}
</script>

</body>
</html>
