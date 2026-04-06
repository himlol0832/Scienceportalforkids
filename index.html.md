<!DOCTYPE html>  
<html>  
<head>  
  <title>Game Hub</title>  
  <style>  
    body {  
      font-family: Arial, sans-serif;  
      background: #0f172a;  
      color: white;  
      text-align: center;  
    }  
    h1 {  
      margin-top: 15px;  
    }  
    #search {  
      padding: 10px;  
      width: 60%;  
      margin: 15px;  
      border-radius: 8px;  
      border: none;  
    }  
    .grid {  
      display: grid;  
      grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));  
      gap: 12px;  
      padding: 20px;  
    }  
    .card {  
      background: #1e293b;  
      padding: 15px;  
      border-radius: 10px;  
      cursor: pointer;  
    }  
    .card:hover {  
      background: #334155;  
    }  
    iframe {  
      width: 90%;  
      height: 500px;  
      border: none;  
      margin-top: 20px;  
      border-radius: 10px;  
    }  
  </style>  
</head>  
  
<body>  
  
<h1>Game Hub</h1>  
<input type="text" id="search" placeholder="Search games..." onkeyup="searchGames()">  
  
<div id="grid" class="grid"></div>  
<iframe id="frame"></iframe>  
  
<script>  
const baseGames = [  
  ["Hextris","https://hextris.github.io/hextris/"],  
  ["2048","https://play2048.co/"],  
  ["Dino Run","https://chromedino.com/"],  
  ["Sandspiel","https://sandspiel.club/"],  
  ["Snake","https://playsnake.org/"],  
  ["Pacman","https://pacman.live/"],  
  ["Minesweeper","https://minesweeperonline.com/"],  
  ["Flappy Bird","https://flappybird.io/"],  
  ["Cookie Clicker","https://orteil.dashnet.org/cookieclicker/"],  
  ["Idle Breakout","https://mathadventure1.github.io/idle-breakout/"],  
  ["Slope","https://ubg100.github.io/games/slope/"],  
  ["Run 3","https://ubg100.github.io/games/run3/"],  
  ["Retro Bowl","https://ubg100.github.io/games/retro-bowl/"],  
  ["Tunnel Rush","https://ubg100.github.io/games/tunnel-rush/"],  
  ["Moto X3M","https://ubg100.github.io/games/moto-x3m/"],  
  ["Drift Boss","https://ubg100.github.io/games/drift-boss/"],  
  ["Crossy Road","https://ubg100.github.io/games/crossy-road/"],  
  ["Subway Surfers","https://ubg100.github.io/games/subway-surfers/"],  
  ["Stickman Hook","https://ubg100.github.io/games/stickman-hook/"],  
  ["Vex 6","https://ubg100.github.io/games/vex-6/"],  
  ["Vex 7","https://ubg100.github.io/games/vex-7/"],  
  ["1v1.LOL","https://ubg100.github.io/games/1v1-lol/"],  
  ["Paper.io","https://ubg100.github.io/games/paper-io/"],  
  ["Hole.io","https://ubg100.github.io/games/hole-io/"],  
  ["Tank Trouble","https://ubg100.github.io/games/tank-trouble/"],  
  ["Geometry Dash","https://ubg100.github.io/games/geometry-dash-lite/"],  
  ["Drive Mad","https://ubg100.github.io/games/drive-mad/"],  
  ["Rooftop Snipers","https://ubg100.github.io/games/rooftop-snipers/"],  
  ["Basket Random","https://ubg100.github.io/games/basket-random/"],  
  ["Soccer Random","https://ubg100.github.io/games/soccer-random/"]  
];  
  
let games = [];  
for (let i = 0; i < 4; i++) {  
  baseGames.forEach(g => {  
    games.push({ name: g[0] + " " + (i+1), url: g[1] });  
  });  
}  
  
const grid = document.getElementById("grid");  
  
function render(list) {  
  grid.innerHTML = "";  
  list.forEach(game => {  
    const div = document.createElement("div");  
    div.className = "card";  
    div.innerText = game.name;  
    div.onclick = () => {  
      document.getElementById("frame").src = game.url;  
    };  
    grid.appendChild(div);  
  });  
}  
  
function searchGames() {  
  const input = document.getElementById("search").value.toLowerCase();  
  const filtered = games.filter(g => g.name.toLowerCase().includes(input));  
  render(filtered);  
}  
  
render(games);  
</script>  
  
</body>  
</html>  
