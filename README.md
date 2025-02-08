<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Custom Wordle - Hey Cutie</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        .grid {
            display: grid;
            grid-template-columns: repeat(5, 50px);
            gap: 10px;
            justify-content: center;
        }
        .cell {
            width: 50px;
            height: 50px;
            background-color: lightgray;
            border: 1px solid black;
            font-size: 20px;
            text-align: center;
            line-height: 50px;
        }
        .correct { background-color: green; }
        .present { background-color: yellow; }
        .absent { background-color: gray; }
        input {
            font-size: 20px;
            width: 50px;
            text-align: center;
        }
        #proposalScreen {
            display: none;
            text-align: center;
        }
        .btn {
            padding: 15px 30px;
            font-size: 20px;
            margin: 10px;
            cursor: pointer;
        }
        .btn-yes {
            background-color: green;
            color: white;
        }
        .btn-no {
            background-color: red;
            color: white;
        }
    </style>
</head>
<body>
    <h1>Wordle: Hey Cutie!</h1>
    <div id="grid" class="grid">
        <div class="cell" id="cell-0"></div>
        <div class="cell" id="cell-1"></div>
        <div class="cell" id="cell-2"></div>
        <div class="cell" id="cell-3"></div>
        <div class="cell" id="cell-4"></div>
        <div class="cell" id="cell-5"></div>
        <div class="cell" id="cell-6"></div>
        <div class="cell" id="cell-7"></div>
        <div class="cell" id="cell-8"></div>
        <div class="cell" id="cell-9"></div>
    </div>
    <br>
    <input type="text" id="input" maxlength="1" oninput="handleInput(event)" autofocus>
    <button onclick="submitGuess()">Submit</button>

    <div id="proposalScreen">
        <h2>Hey Cutie, Will You Be My Valentine?</h2>
        <button class="btn btn-yes" onclick="respond('yes')">Yes</button>
        <button class="btn btn-no" onclick="respond('no')">No</button>
    </div>

    <script>
        const word1 = "HEY";
        const word2 = "CUTIE";
        let currentGuess = "";
        let guessIndex = 0;
        let correctWord = [word1, word2];
        const grid = document.getElementById("grid");
        const proposalScreen = document.getElementById("proposalScreen");

        function handleInput(event) {
            const value = event.target.value.toUpperCase();
            if (/[A-Z]/.test(v
