<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Escape Game - Kaufvertrag</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            text-align: center;
        }

        .game-container {
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            width: 400px;
        }

        h1 {
            color: #333;
        }

        .question {
            font-size: 1.2em;
            margin-bottom: 20px;
        }

        .answers {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .answer {
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            cursor: pointer;
            background-color: #f9f9f9;
            transition: background-color 0.3s;
        }

        .answer:hover {
            background-color: #dcdcdc;
        }

        .button {
            padding: 10px 20px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1.2em;
        }

        .button:hover {
            background-color: #45a049;
        }

        .hidden {
            display: none;
        }

        .game-over {
            font-size: 1.5em;
            color: red;
            margin-top: 20px;
        }

        .next-button {
            margin-top: 20px;
        }
    </style>
</head>
<body>

<div class="game-container">
    <h1>Escape Game - Kaufvertrag</h1>
    <div id="question1">
        <div class="question">Was ist ein Kaufvertrag?</div>
        <div class="answers">
            <div class="answer" onclick="checkAnswer(1)">Vertrag zwischen Käufer und Verkäufer</div>
            <div class="answer" onclick="checkAnswer(2)">Vertrag über den Kauf von Waren oder Dienstleistungen</div>
            <div class="answer" onclick="checkAnswer(3)">Vertrag, der keine rechtliche Wirkung hat</div>
        </div>
    </div>
    <div id="question2" class="hidden">
        <div class="question">Wann kommt ein Kaufvertrag zustande?</div>
        <div class="answers">
            <div class="answer" onclick="checkAnswer2(1)">Ein Kaufvertrag kommt zustande, wenn der Käufer das Angebot des Verkäufers akzeptiert.</div>
            <div class="answer" onclick="checkAnswer2(2)">Ein Kaufvertrag kommt zustande, wenn der Verkäufer das Angebot des Käufers akzeptiert.</div>
        </div>
    </div>
    <div id="gameOver" class="game-over hidden">Game Over! Versuch es noch einmal!</div>
    <button class="button next-button hidden" id="nextButton" onclick="nextStation()">Weiter zur nächsten Station</button>
</div>

<script>
    // Station 1: Frage 1
    let correctAnswer1 = 1; // Die richtige Antwort auf Frage 1 ist die erste Option

    function checkAnswer(selectedAnswer) {
        if (selectedAnswer === correctAnswer1) {
            document.getElementById('question1').classList.add('hidden');
            document.getElementById('question2').classList.remove('hidden');
        } else {
            document.getElementById('gameOver').classList.remove('hidden');
        }
    }

    // Station 2: Frage 2
    let correctAnswer2 = 1; // Die richtige Antwort auf Frage 2 ist die erste Option

    function checkAnswer2(selectedAnswer) {
        if (selectedAnswer === correctAnswer2) {
            document.getElementById('gameOver').classList.add('hidden');
            document.getElementById('nextButton').classList.remove('hidden');
        } else {
            document.getElementById('gameOver').classList.remove('hidden');
        }
    }

    // Weiter zur nächsten Station (optional)
    function nextStation() {
        alert("Glückwunsch! Du hast alle Fragen richtig beantwortet.");
    }
</script>

</body>
</html>
