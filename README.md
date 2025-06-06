# My-Mision-Future
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Mission Future: Save the Timeline</title>
    <style>
        body {
            font-family: 'Segoe UI', sans-serif;
            background-color: #1e1e2f;
            color: #f0f0f0;
            padding: 2em;
            line-height: 1.6;
        }
        .choice {
            margin: 1em 0;
        }
        button {
            padding: 0.5em 1em;
            margin: 0.2em;
            font-size: 1em;
            background-color: #3e8ed0;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #66aaff;
        }
        #content {
            max-width: 600px;
            margin: auto;
        }
    </style>
</head>
<body>
    <div id="content">
        <h1>Mission Future: Save the Timeline</h1>
        <div id="scene"></div>
    </div>
    <script>
        let score = 0;

        const scenes = {
            start: `
                <p>You are Agent Nova. Time Control needs you. A villain from the future is changing history.</p>
                <p>The Director says: "You must stop him. If not, the world <strong>will change forever</strong>."</p>
                <p>Complete the sentence:</p>
                <p><em>"I ______ save the timeline."</em></p>
                <div class="choice">
                    <button onclick="nextScene('rightStart')">a) will</button>
                    <button onclick="nextScene('wrongStart')">b) did</button>
                    <button onclick="nextScene('wrongStart')">c) was</button>
                </div>
            `,
            rightStart: `
                <p>✅ Correct! You are ready to begin.</p>
                <p>You arrive at the time portal. You must enter fast!</p>
                <p>"I will take the ___."</p>
                <div class="choice">
                    <button onclick="nextScene('wrongTool')">a) banana</button>
                    <button onclick="nextScene('rightTool')">b) time blaster</button>
                    <button onclick="nextScene('wrongTool')">c) old sock</button>
                </div>
            `,
            wrongStart: `
                <p>❌ That's incorrect. Remember, use 'will' for the future.</p>
                <button onclick="nextScene('start')">Try again</button>
            `,
            rightTool: `
                <p>✅ Smart choice. You take the time blaster.</p>
                <p>You land in 1985. People are confused. A strange machine is glowing.</p>
                <p>What will you do?</p>
                <div class="choice">
                    <button onclick="nextScene('turnOff')">I will turn off the machine.</button>
                    <button onclick="nextScene('talkPeople')">I will talk to the people.</button>
                    <button onclick="nextScene('runAway')">I will run away.</button>
                </div>
            `,
            wrongTool: `
                <p>❌ That tool is not useful.</p>
                <button onclick="nextScene('rightStart')">Try again</button>
            `,
            turnOff: `
                <p>The machine shows a message:</p>
                <p>"If you don’t stop me, I ______ destroy everything."</p>
                <div class="choice">
                    <button onclick="nextScene('success')">a) will</button>
                    <button onclick="nextScene('fail')">b) am</button>
                    <button onclick="nextScene('fail')">c) have</button>
                </div>
            `,
            talkPeople: `
                <p>The people are scared and run away. You lost precious time.</p>
                <button onclick="nextScene('turnOff')">Go to the machine</button>
            `,
            runAway: `
                <p>You hide, but the future will be lost without your help.</p>
                <button onclick="nextScene('start')">Start over</button>
            `,
            success: `
                <p>✅ You stopped the machine just in time!</p>
                <p>"You saved the future," says the robot. "You will be a hero in history books."</p>
                <p>🎉 Congratulations!</p>
                <button onclick="nextScene('start')">Play again</button>
            `,
            fail: `
                <p>❌ Wrong choice. The machine explodes.</p>
                <p>History is lost.</p>
                <button onclick="nextScene('start')">Try again</button>
            `
        };

        function nextScene(sceneId) {
            document.getElementById('scene').innerHTML = scenes[sceneId];
        }

        // Start the story
        nextScene('start');
    </script>
</body>
</html>
