
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <title>Mirohodez.ru</title>

    <style>
body {
    background: url(https://i.ytimg.com/vi/udae955Z06E/maxresdefault.jpg) no-repeat center center fixed;
    background-size: cover;
    height: 100vh;
    margin: 0;
    color: white;
    font-family: Arial;
    text-align: center;
    padding-top: 100px;
}
         h1 {
            color: #00ff88;
            font-size: 48px;
        }

        button {
            padding: 15px 40px;
            font-size: 18px;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            background: #00ff88;
            margin: 15px;
            transition: 0.2s;
        }

        button:hover {
            background: #00cc6a;
            transform: scale(1.05);
        }
    </style>
</head>

<body>

    <h1>Путеводитель</h1>

    <button onclick="go1()">No Scam</button>
    <button onclick="go2()">Magazine</button>
    <button onclick="go3()">New seria</button>

    <script>

        function go1() {
            window.location.href = "https://www.youtube.com/watch?v=dQw4w9WgXcQ";
        }

        function go2() {
            window.location.href = "https://mirohodec.ru/";
        }

        function go3() {
            window.location.href = "https://www.youtube.com/watch?v=hLYEZcUnjyc";
        }

    </script>

</body>

<html lang="ru">
<head>
<meta charset="UTF-8">
<title>Колесо Сезонов</title>
<style>
body {
    background: url(https://i.ytimg.com/vi/udae955Z06E/maxresdefault.jpg) no-repeat center center fixed;
    background-size: cover;
    color: white;
    font-family: Arial;
    text-align: center;
}

h1 {
    color: #00ff88;
}

#wheel {
    width: 300px;
    height: 300px;
    border: 10px solid #00ff88;
    border-radius: 50%;
    margin: 30px auto;
    position: relative;
    overflow: hidden;
    transform: rotate(0deg);
    transition: transform 4s ease-out;
}

.slice {
    position: absolute;
    width: 50%;
    height: 50%;
    transform-origin: 100% 100%;
    text-align: right;
    padding: 5px;
    box-sizing: border-box;
    font-size: 12px;
}

#arrow {
    font-size: 40px;
}

button {
    padding: 15px 30px;
    font-size: 18px;
    background: #00ff88;
    border: none;
    border-radius: 10px;
    cursor: pointer;
}
</style>
</head>

<body>

<h1>✨ Колесо Сезонов</h1>

<div id="arrow">⬇️</div>

<div id="wheel"></div>

<br>

<button onclick="spin()">Крутить</button>

<h2 id="result"></h2>

<script>

let names = [
    "Идеальный Мир",
    "Голос Времени",
    "Тринадцать Огней",
    "Последняя Реальность",
    "Сердце Вселенной",
    "Точка Невозврата",
    "Мастерская 47",
    "Падение Искры",
];

// ===== Рисуем колесо =====

let wheel = document.getElementById("wheel");
let angle = 360 / names.length;

for (let i = 0; i < names.length; i++) {

    let slice = document.createElement("div");
    slice.className = "slice";

    slice.style.transform =
        "rotate(" + (i * angle) + "deg) skewY(" + (90 - angle) + "deg)";

    slice.style.background =
        i % 2 == 0 ? "#00ff88" : "#00cc6a";

    slice.innerText = names[i];

    wheel.appendChild(slice);
}

// ===== Крутилка =====

let currentRotation = 0;

function spin() {

    let random = Math.floor(Math.random() * 360) + 720;

    currentRotation += random;

    wheel.style.transform =
        "rotate(" + currentRotation + "deg)";

    let index = Math.floor(
        (360 - (currentRotation % 360)) / angle
    ) % names.length;

    setTimeout(() => {
        document.getElementById("result").innerText =
            "На Барабане: " + names[index];
    }, 4000);
}

</script>

</body>
</html>

