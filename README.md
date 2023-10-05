# traffic-light-Set-Timeout-
Link : https://codepen.io/Him_1204/pen/VwqEgvQ


HTML
<div class="main-container">
  <div class="traffic-light">
    <div class="light red"></div>
    <div class="light yellow"></div>
    <div class="light green"></div>
  </div>
</div>

Css 
.main-container{
  display:flex;
  justify-content:center;
}
.traffic-light {
  width: 100px;
  height: 300px;
  background-color: black;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  padding: 10px;
}

.light {
  width: 80px;
  height: 80px;
  border-radius: 50%;
}

.red {
  background-color: red;
}

.yellow {
  background-color: yellow;
}

.green {
  background-color: green;
}

JS

function switchLights() {
  var redLight = document.querySelector(".light.red");
  var yellowLight = document.querySelector(".light.yellow");
  var greenLight = document.querySelector(".light.green");

  function setLights(redOpacity, yellowOpacity, greenOpacity) {
    redLight.style.opacity = redOpacity;
    yellowLight.style.opacity = yellowOpacity;
    greenLight.style.opacity = greenOpacity;
  }

  var lightSequence = [
    { red: 1, yellow: 0.3, green: 0.3 }, // Initial state
    { red: 0.3, yellow: 1, green: 0.3 }, // After 4000ms
    { red: 0.3, yellow: 0.3, green: 1 }, // After 4500ms
  ];

  var currentIndex = 0;
  
  setInterval(function() {
    setLights(lightSequence[currentIndex].red, lightSequence[currentIndex].yellow, lightSequence[currentIndex].green);
    currentIndex = (currentIndex + 1) % lightSequence.length;
  }, 7500);
}

switchLights();




