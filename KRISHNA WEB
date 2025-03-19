<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KRISHNA WEB</title>
    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #1a1a1a;
            color: #ffffff;
            text-align: center;
            margin: 0;
            overflow: hidden;
        }
        #particles-red, #particles-white {
            position: fixed;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: transparent;
        }
        #particles-red { top: 0; left: 0; }
        #particles-white { top: 0; left: 0; }

        .title {
            font-size: 2em;
            font-weight: bold;
            color: red;
            padding: 20px 0;
        }
        .container {
            position: relative;
            z-index: 1;
            padding: 20px;
        }
        .section {
            background: #222;
            padding: 15px;
            margin: 10px auto;
            border-radius: 5px;
            width: 50%;
            text-align: center;
        }
        .hidden { display: none; }

        /* Neon Blinking Effect */
        .blinking {
            font-size: 2em;
            font-weight: bold;
            color: red;
            text-shadow: 0 0 5px #ff0000, 0 0 10px #ff0000, 0 0 20px #ff0000, 0 0 40px #ff0000;
            animation: blinkEffect 1s infinite alternate;
        }
        @keyframes blinkEffect {
            0% { opacity: 1; }
            100% { opacity: 0.3; }
        }

        .btn {
            background-color: #FF0000;
            color: white;
            font-size: 18px;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 10px;
        }
        .btn:hover { background-color: #cc0000; }
    </style>
</head>
<body>

    <div id="particles-red"></div>
    <div id="particles-white"></div>

    <div class="title">KRISHNA WEB</div>

    <div class="container">
        <div class="section">
            <h3>⏳ Period Number</h3>
            <p id="periodDisplay">Loading...</p>
        </div>

        <div class="section">
            <h3>🔮 Prediction Result</h3>
            <p id="predictedResult" class="hidden">????</p>
        </div>

        <div class="section">
            <button class="btn" id="showResultBtn">Show Result</button>
        </div>

        <button class="btn" id="predictButton">Predict Now</button>
    </div>

    <script>
        class WingoPredictionCalculator {
            constructor() {
                this.previousOutcomes = [];
            }

            predictNextOutcome() {
                if (this.previousOutcomes.length < 20) {
                    return this.generateRandomPrediction();
                }
                return this.analyzePatternAndPredict();
            }

            generateRandomPrediction() {
                const outcomes = ["BIG", "SMALL"];
                return outcomes[Math.floor(Math.random() * outcomes.length)];
            }

            analyzePatternAndPredict() {
                let recentRounds = this.previousOutcomes.slice(-20);
                let bigCount = recentRounds.filter(outcome => outcome === "BIG").length;
                let smallCount = recentRounds.filter(outcome => outcome === "SMALL").length;

                let bigProbability = bigCount / recentRounds.length;
                let smallProbability = smallCount / recentRounds.length;

                return bigProbability > smallProbability ? "BIG" : "SMALL";
            }
        }

        let predictor = new WingoPredictionCalculator();

        function updatePeriodNumber() {
            const now = new Date();
            const year = now.getUTCFullYear();
            const month = String(now.getUTCMonth() + 1).padStart(2, '0');
            const day = String(now.getUTCDate()).padStart(2, '0');
            const totalMinutes = now.getUTCHours() * 60 + now.getUTCMinutes();
            const periodNumber = `${year}${month}${day}1000${10001 + totalMinutes}`;
            document.getElementById("periodDisplay").innerText = periodNumber;
        }

        function generatePrediction() {
            updatePeriodNumber();
            let prediction = predictor.predictNextOutcome();
            let predictedResult = document.getElementById("predictedResult");

            predictor.previousOutcomes.unshift(prediction);
            if (predictor.previousOutcomes.length > 20) predictor.previousOutcomes.pop();

            predictedResult.innerText = prediction;
            predictedResult.classList.add("hidden");
            predictedResult.classList.remove("blinking");
        }

        document.getElementById("predictButton").addEventListener("click", generatePrediction);
        document.getElementById("showResultBtn").addEventListener("click", function () {
            let resultElement = document.getElementById("predictedResult");
            resultElement.classList.remove("hidden");
            resultElement.classList.add("blinking");
        });

        updatePeriodNumber();
        setInterval(updatePeriodNumber, 60000);

        // Red Particles
        particlesJS("particles-red", {
            particles: {
                number: { value: 80 },
                color: { value: "#FF0000" },
                line_linked: { enable: true, color: "#FF0000" },
                size: { value: 5, random: true },
                move: { speed: 2 }
            }
        });

        // White Particles (NEW)
        particlesJS("particles-white", {
            particles: {
                number: { value: 60 },
                color: { value: "#FFFFFF" }, // Changed to WHITE
                line_linked: { enable: true, color: "#FFFFFF" },
                size: { value: 4, random: true },
                move: { speed: 1.5 }
            }
        });

    </script>

</body>
</html>
