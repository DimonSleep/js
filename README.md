# js
// EX5
document.addEventListener("DOMContentLoaded", function(event) {

  var canvas = document.getElementById("myCanvas");
  var context = canvas.getContext("2d");


  canvas.width = 400;
  canvas.height = 400;

  // Desenează pătratul
  var squareSize = 200;
  var squareX = canvas.width / 2 - squareSize / 2;
  var squareY = canvas.height / 2 - squareSize / 2;

  context.fillStyle = "blue";
  context.fillRect(squareX, squareY, squareSize, squareSize);


  var circleRadius = squareSize / 2;
  var circleX = squareX + squareSize / 2;
  var circleY = squareY + squareSize / 2;

  context.strokeStyle = "red";
  context.lineWidth = 2;
  context.beginPath();
  context.arc(circleX, circleY, circleRadius, 0, 2 * Math.PI);
  context.stroke();
});


///ex6


document.addEventListener("DOMContentLoaded", function(event) {

  var paragraf = document.getElementById("PAR1");


  var curentWidth = paragraf.offsetWidth;
  var curentHeight = paragraf.offsetHeight;


  var nouWidth = curentWidth - 3;
  var nouHeight = curentHeight - 3;

  paragraf.style.width = nouWidth + "px";
  paragraf.style.height = nouHeight + "px";
});


////EX7
<!DOCTYPE html>
<html>
<head>
  <title>Joc matematic</title>
  <style>
    body {
      font-family: Arial, sans-serif;
    }

    #exercitiu {
      font-size: 24px;
      margin-bottom: 10px;
    }

    #rezultat {
      margin-top: 10px;
    }
  </style>
</head>
<body>
  <h1>Joc matematic</h1>
  <div id="exercitiu"></div>
  <input type="number" id="inputRezultat">
  <button id="verificaBtn">Verifică</button>
  <div id="rezultat"></div>

  <script>
    document.addEventListener("DOMContentLoaded", function(event) {
      var exercitiiRezolvate = 0;
      var exercitiiCorecte = 0;
      var numarExercitii = 5;

      var exercitiuContainer = document.getElementById("exercitiu");
      var inputRezultat = document.getElementById("inputRezultat");
      var verificaBtn = document.getElementById("verificaBtn");
      var rezultatContainer = document.getElementById("rezultat");

      // Funcția care generează un exercițiu nou
      function genereazaExercitiu() {
        var m = Math.floor(Math.random() * 500);
        var n = Math.floor(Math.random() * 500);

        exercitiuContainer.textContent = m + "/" + n + " = ?";
        inputRezultat.value = "";
        rezultatContainer.textContent = "";
      }

      // Funcția care verifică rezultatul introdus de utilizator
      function verificaRezultat() {
        var rezultat = eval(exercitiuContainer.textContent.replace("?", inputRezultat.value));
        if (rezultat === m / n) {
          rezultatContainer.textContent = "Corect!";
          exercitiiCorecte++;
        } else {
          rezultatContainer.textContent = "Greșit!";
        }

        exercitiiRezolvate++;

        // Verifică dacă s-au rezolvat toate exercițiile
        if (exercitiiRezolvate === numarExercitii) {
          alert("Jocul s-a încheiat. Ai rezolvat corect " + exercitiiCorecte + " exerciții.");
        } else {
          genereazaExercitiu();
        }
      }

      // Atașează funcția de verificare la evenimentul de click al butonului "Verifică"
      verificaBtn.addEventListener("click", verificaRezultat);

      // Generează primul exercițiu
      genereazaExercitiu();
    });
  </script>
</body>
</html>

