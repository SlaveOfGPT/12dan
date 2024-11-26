<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>구구단 게임</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
        }
        h1 {
            margin-top: 20px;
        }
        #timer {
            font-size: 24px;
            margin-top: 20px;
        }
        #question {
            font-size: 30px;
            margin-top: 30px;
        }
        input[type="number"], input[type="text"] {
            font-size: 18px;
            padding: 5px;
            margin-top: 10px;
        }
        button {
            font-size: 18px;
            padding: 10px 20px;
            margin-top: 10px;
            cursor: pointer;
        }
        #score {
            font-size: 20px;
            margin-top: 20px;
        }
        #rankings {
            margin-top: 20px;
            text-align: left;
        }
        .button-group {
            margin-top: 20px;
        }
        .button-group button {
            margin: 5px;
        }
        #gameScreen {
            display: none; /* 게임 화면은 처음에 숨김 */
        }
        #endScreen {
            display: none; /* 게임 종료 화면도 처음에 숨김 */
        }
    </style>
</head>
<body>
    <h1>구구단 게임</h1>

    <!-- 첫 번째 화면 (문제 수 선택) -->
    <div id="startScreen">
        <div class="button-group">
            <!-- 문제 수 선택 버튼 -->
            <button id="btn10">10문제</button>
            <button id="btn20">20문제</button>
            <button id="btn30">30문제</button>
            <button id="btn50">50문제</button>
        </div>
    </div>

    <!-- 두 번째 화면 (문제 풀이 화면) -->
    <div id="gameScreen">
        <p id="question"></p>
        <input type="number" id="answer" placeholder="정답을 입력하세요">
        <button id="submit">제출</button>

        <p id="timer">시간: 0초</p> <!-- 타이머 표시 -->
        <p id="score">맞은 문제 수: 0</p> <!-- 맞은 문제 수 표시 -->
    </div>

    <!-- 게임 종료 후 결과 화면 -->
    <div id="endScreen">
        <h2>게임 종료</h2>
        <p>맞은 문제 수: <span id="finalScore"></span></p>
        <p>소요 시간: <span id="finalTime"></span>초</p>
        <label for="playerName">이름: </label>
        <input type="text" id="playerName" placeholder="이름을 입력하세요" required>
        <button id="saveScore">점수 저장</button>

        <div id="rankings"></div> <!-- 순위 표시 -->
    </div>

    <script>
        let startTime = null;
        let timerInterval = null;
        let timeElapsed = 0;
        let correctAnswers = 0;
        let totalQuestions = 0;
        let questionsAnswered = 0;

        // 게임 시작 시 타이머 시작
        function startTimer() {
            startTime = Date.now();
            timerInterval = setInterval(function() {
                timeElapsed = Math.floor((Date.now() - startTime) / 1000); // 경과 시간 (초 단위)
                document.getElementById("timer").textContent = "시간: " + timeElapsed + "초";
            }, 1000);
        }

        // 게임 종료 시 타이머 멈추기
        function stopTimer() {
            clearInterval(timerInterval);
        }

        // 문제 출제 함수
        function askQuestion() {
            const num1 = Math.floor(Math.random() * 9) + 1;
            const num2 = Math.floor(Math.random() * 9) + 1;
            const correctAnswer = num1 * num2;

            document.getElementById("question").textContent = `${num1} x ${num2} = ?`;

            document.getElementById("submit").onclick = function() {
                const userAnswer = parseInt(document.getElementById("answer").value);
                if (userAnswer === correctAnswer) {
                    correctAnswers++;
                    document.getElementById("score").textContent = "맞은 문제 수: " + correctAnswers;
                }
                questionsAnswered++;

                // 모든 문제가 끝났을 때 게임 종료
                if (questionsAnswered >= totalQuestions) {
                    endGame();
                } else {
                    document.getElementById("answer").value = ""; // 입력창 비우기
                    askQuestion(); // 다음 문제 출제
                }
            };
        }

        // 엔터 키 이벤트를 사용하여 문제 제출
        document.getElementById("answer").addEventListener("keydown", function(event) {
            if (event.key === "Enter") {
                document.getElementById("submit").click();
            }
        });

        // 게임 종료 후 결과 화면
        function endGame() {
            stopTimer(); // 게임 종료 시 타이머 멈추기
            document.getElementById("finalScore").textContent = correctAnswers;
            document.getElementById("finalTime").textContent = timeElapsed;

            // 화면 전환: 게임 화면 숨기고 결과 화면 보이기
            document.getElementById("gameScreen").style.display = "none";
            document.getElementById("endScreen").style.display = "block";
        }

        // 점수 저장 함수
        function saveScore() {
            const playerName = document.getElementById("playerName").value.trim();
            if (playerName === "") {
                alert("이름을 입력하세요!");
                return;
            }

            const previousScores = JSON.parse(localStorage.getItem("scores")) || [];
            const newScore = {
                name: playerName,
                score: correctAnswers,
                time: timeElapsed,
                date: new Date().toLocaleString()
            };
            previousScores.push(newScore);
            previousScores.sort((a, b) => b.score - a.score || a.time - b.time); // 점수 내림차순, 동일 점수는 시간 오름차순
            localStorage.setItem("scores", JSON.stringify(previousScores));
            showRankings(previousScores);
        }

        // 순위 표시 함수
        function showRankings(scores) {
            let rankingsHTML = "<h2>순위</h2><ol>";
            scores.forEach((score, index) => {
                rankingsHTML += `<li>순위 ${index + 1}: ${score.name} - 점수: ${score.score}, 시간: ${score.time}초, ${score.date}</li>`;
            });
            rankingsHTML += "</ol>";
            document.getElementById("rankings").innerHTML = rankingsHTML;
        }

        // 게임 시작 함수
        function startGame() {
            correctAnswers = 0;
            questionsAnswered = 0;
            timeElapsed = 0;
            document.getElementById("score").textContent = "맞은 문제 수: " + correctAnswers;

            // 화면 전환: 문제 화면 보이기
            document.getElementById("startScreen").style.display = "none";
            document.getElementById("gameScreen").style.display = "block";

            startTimer();
            askQuestion();
        }

        // 문제 수 버튼 클릭 시 문제 수 설정 및 게임 시작
        document.getElementById("btn10").onclick = function() { totalQuestions = 10; startGame(); };
        document.getElementById("btn20").onclick = function() { totalQuestions = 20; startGame(); };
        document.getElementById("btn30").onclick = function() { totalQuestions = 30; startGame(); };
        document.getElementById("btn50").onclick = function() { totalQuestions = 50; startGame(); };

        // 점수 저장 버튼 클릭 시 점수 저장
        document.getElementById("saveScore").onclick = saveScore;
    </script>
</body>
</html>
