<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Contador Regresivo</title>
<style>
  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background: linear-gradient(135deg, #f77062, #fe5196); /* Dégradé de rose */
    color: #fff;
  }

  #contador {
    background-color: rgba(255, 255, 255, 0.8); /* Blanc transparent */
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
    text-align: center;
    color: #333;
  }
</style>
</head>
<body>

<div id="contador">
  <h1>¡Contador Regresivo!</h1>
  <p>¡Tiempo restante antes de que el servicio 0800 bitstp llegue!</p>
  <p id="tiempo-restante">16h 00m 00s</p>
</div>

<script>
// Fonction pour mettre à jour le compte à rebours
function mettreAJourCompteRebours() {
  var maintenant = new Date();
  var finJournee = new Date();
  finJournee.setHours(16, 0, 0, 0); // Réglage de l'heure à 16h00

  var difference = finJournee - maintenant;

  var heures = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
  var minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));
  var secondes = Math.floor((difference % (1000 * 60)) / 1000);

  var countdownElement = document.getElementById('tiempo-restante');
  countdownElement.innerHTML = heures + 'h ' + minutes + 'm ' + secondes + 's';
}

// Mettre à jour le compte à rebours toutes les secondes
setInterval(mettreAJourCompteRebours, 1000);

// Mise à jour initiale du compte à rebours
mettreAJourCompteRebours();
</script>

</body>
</html>
