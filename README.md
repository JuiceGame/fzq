<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chemistry Balancing Equations Quiz</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        .question {
            margin-bottom: 20px;
        }
        .result {
            margin-top: 20px;
            padding: 10px;
            border: 1px solid #ddd;
            background-color: #f9f9f9;
        }
        .correct {
            color: green;
        }
        .incorrect {
            color: red;
        }
        input[type="text"] {
            width: 30px;
            text-align: center;
        }
    </style>
</head>
<body>

    <h1>Chemistry Balancing Equations Quiz</h1>
    <form id="quizForm">
        <div class="question">
            <label for="q1">1. <input type="text" id="q1_1" name="q1_1" placeholder="1"> H₂ + <input type="text" id="q1_2" name="q1_2" placeholder="1"> N₂ → <input type="text" id="q1_3" name="q1_3" placeholder="1"> NH₃</label>
        </div>

        <div class="question">
            <label for="q2">2. <input type="text" id="q2_1" name="q2_1" placeholder="1"> C₂H₆ + <input type="text" id="q2_2" name="q2_2" placeholder="1"> O₂ → <input type="text" id="q2_3" name="q2_3" placeholder="1"> CO₂ + <input type="text" id="q2_4" name="q2_4" placeholder="1"> H₂O</label>
        </div>

        <div class="question">
            <label for="q3">3. <input type="text" id="q3_1" name="q3_1" placeholder="1"> Al + <input type="text" id="q3_2" name="q3_2" placeholder="1"> O₂ → <input type="text" id="q3_3" name="q3_3" placeholder="1"> Al₂O₃</label>
        </div>

        <div class="question">
            <label for="q4">4. <input type="text" id="q4_1" name="q4_1" placeholder="1"> Fe + <input type="text" id="q4_2" name="q4_2" placeholder="1"> Cl₂ → <input type="text" id="q4_3" name="q4_3" placeholder="1"> FeCl₃</label>
        </div>

        <div class="question">
            <label for="q5">5. <input type="text" id="q5_1" name="q5_1" placeholder="1"> Pb(NO₃)₂ + <input type="text" id="q5_2" name="q5_2" placeholder="1"> KI → <input type="text" id="q5_3" name="q5_3" placeholder="1"> PbI₂ + <input type="text" id="q5_4" name="q5_4" placeholder="1"> KNO₃</label>
        </div>

        <div class="question">
            <label for="q6">6. <input type="text" id="q6_1" name="q6_1" placeholder="1"> Na₂CO₃ + <input type="text" id="q6_2" name="q6_2" placeholder="1"> HCl → <input type="text" id="q6_3" name="q6_3" placeholder="1"> NaCl + <input type="text" id="q6_4" name="q6_4" placeholder="1"> H₂O + <input type="text" id="q6_5" name="q6_5" placeholder="1"> CO₂</label>
        </div>

        <div class="question">
            <label for="q7">7. <input type="text" id="q7_1" name="q7_1" placeholder="1"> C₄H₁₀ + <input type="text" id="q7_2" name="q7_2" placeholder="1"> O₂ → <input type="text" id="q7_3" name="q7_3" placeholder="1"> CO₂ + <input type="text" id="q7_4" name="q7_4" placeholder="1"> H₂O</label>
        </div>

        <div class="question">
            <label for="q8">8. <input type="text" id="q8_1" name="q8_1" placeholder="1"> Ca(OH)₂ + <input type="text" id="q8_2" name="q8_2" placeholder="1"> H₃PO₄ → <input type="text" id="q8_3" name="q8_3" placeholder="1"> Ca₃(PO₄)₂ + <input type="text" id="q8_4" name="q8_4" placeholder="1"> H₂O</label>
        </div>

        <div class="question">
            <label for="q9">9. <input type="text" id="q9_1" name="q9_1" placeholder="1"> KClO₃ → <input type="text" id="q9_2" name="q9_2" placeholder="1"> KCl + <input type="text" id="q9_3" name="q9_3" placeholder="1"> O₂</label>
        </div>

        <div class="question">
            <label for="q10">10. <input type="text" id="q10_1" name="q10_1" placeholder="1"> C₆H₁₂O₆ → <input type="text" id="q10_2" name="q10_2" placeholder="1"> C₂H₅OH + <input type="text" id="q10_3" name="q10_3" placeholder="1"> CO₂</label>
        </div>

        <button type="button" onclick="checkAnswers()">Submit</button>
    </form>

    <div id="results" class="result"></div>

    <script>
        function checkAnswers() {
            const answers = {
                q1_1: "3", q1_2: "1", q1_3: "2",
                q2_1: "2", q2_2: "7", q2_3: "4", q2_4: "6",
                q3_1: "4", q3_2: "3", q3_3: "2",
                q4_1: "2", q4_2: "3", q4_3: "2",
                q5_1: "1", q5_2: "2", q5_3: "1", q5_4: "2",
                q6_1: "1", q6_2: "2", q6_3: "2", q6_4: "1", q6_5: "1",
                q7_1: "2", q7_2: "13", q7_3: "8", q7_4: "10",
                q8_1: "3", q8_2: "2", q8_3: "1", q8_4: "6",
                q9_1: "2", q9_2: "2", q9_3: "3",
                q10_1: "1", q10_2: "2", q10_3: "2"
            };

            const form = document.getElementById("quizForm");
            const results = document.getElementById("results");
            results.innerHTML = "";

            let correctCount = 0;

            for (let i = 1; i <= 10; i++) {
                let correct = true;
                for (let j = 1; j <= Object.keys(answers).filter(key => key.startsWith(`q${i}_`)).length; j++) {
                    const userAnswer = form[`q${i}_${j}`].value.trim();
                    const correctAnswer = answers[`q${i}_${j}`];

                    if (userAnswer !== correctAnswer) {
                        correct = false;
                        results.innerHTML += `<p class="incorrect">Question ${i}: Incorrect. The correct coefficient for ${j === 1 ? '' : j} is <strong>${correctAnswer}</strong>.</p>`;
                    }
                }
                if (correct) {
                    results.innerHTML += `<p class="correct">Question ${i}: Correct!</p>`;
                    correctCount++;
                }
            }

            results.innerHTML += `<p>You got ${correctCount} out of 10 correct.</p>`;
        }
    </script>

</body>
</html>
