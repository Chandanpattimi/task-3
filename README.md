# task-3
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Advanced Styling and JavaScript</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f4f4;
      color: #333;
    }

    .container {
      max-width: 800px;
      margin: auto;
      padding: 20px;
      text-align: center;
    }

    h1 {
      color: #00796b;
    }

    section {
      margin-bottom: 40px;
      padding: 20px;
      background: #fff;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }

    button {
      padding: 10px 15px;
      margin: 5px;
      border: none;
      border-radius: 5px;
      background-color: #00796b;
      color: white;
      cursor: pointer;
    }

    button:hover {
      background-color: #004d40;
    }

    @media (max-width: 768px) {
      body {
        background-color: #e0f7fa;
      }
    }

    @media (max-width: 480px) {
      body {
        font-size: 14px;
        background-color: #ffecb3;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Advanced Styling and JavaScript</h1>

    <!-- Task 1: Responsive Design -->
    <section>
      <h2>Responsive Design</h2>
      <p>This section changes background based on screen width using media queries.</p>
    </section>

    <!-- Task 2: Interactive Quiz -->
    <section>
      <h2>Simple Quiz</h2>
      <p>What is the capital of France?</p>
      <button onclick="checkAnswer('London')">London</button>
      <button onclick="checkAnswer('Paris')">Paris</button>
      <button onclick="checkAnswer('Rome')">Rome</button>
      <p id="quizResult"></p>
    </section>

    <!-- Task 3: Fetch Data from API -->
    <section>
      <h2>Random Joke Generator</h2>
      <button onclick="getJoke()">Get a Joke</button>
      <p id="joke"></p>
    </section>
  </div>

  <script>
    // Quiz logic
    function checkAnswer(answer) {
      const result = document.getElementById("quizResult");
      if (answer === "Paris") {
        result.textContent = "Correct! 🎉";
      } else {
        result.textContent = "Incorrect. Try again!";
      }
    }

    // API Fetch logic
    async function getJoke() {
      const response = await fetch("https://official-joke-api.appspot.com/random_joke");
      const data = await response.json();
      document.getElementById("joke").innerText = `${data.setup} — ${data.punchline}`;
    }
  </script>
</body>
</html>
