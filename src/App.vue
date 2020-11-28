<template>
  <div id="app">
    <h1>Ssssssnake</h1>

    
    <canvas id='myCanvas'></canvas>

  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  mounted: function() {
    let canvas = document.getElementById("myCanvas");
    let ctx = canvas.getContext("2d");

    let X = 10;

    let Y = 10;

    let CircleX = Math.random()*canvas.width;
    
    let CircleY = Math.random()* canvas.height;
  
    ctx.beginPath();
    ctx.strokeStyle = "red";
    ctx.lineWidth = "1";
    ctx.rect(X, 10, 10, 10);
    ctx.stroke();


    ctx.beginPath();
    ctx.strokeStyle = "black";
    ctx.lineWidth = "1";
    ctx.arc(CircleX, CircleY, 5, 0, 2*Math.PI );
    ctx.stroke();



    document.addEventListener('keydown', function(event) {
      
      if(event.key === 'ArrowRight' && X < canvas.width - 10) {
      console.log("pressRight") 
        ctx.clearRect(0, 0, canvas.width, canvas.height);

        ctx.beginPath();
        ctx.strokeStyle = "black";
        ctx.lineWidth = "1";
        ctx.arc(CircleX, CircleY, 5, 0, 2*Math.PI );
        ctx.stroke();

        ctx.beginPath();
        ctx.strokeStyle = "red";
        ctx.lineWidth = "1";
        X = X + 5;
        ctx.rect(X,Y, 10, 10);
        ctx.stroke();
      }

      if(event.key === 'ArrowLeft' && X>0) {
        console.log('We have pressed LEFT arrow')
        ctx.clearRect(0, 0, canvas.width, canvas.height);

        ctx.beginPath();
        ctx.strokeStyle = "black";
        ctx.lineWidth = "1";
        ctx.arc(CircleX, CircleY, 5, 0, 2*Math.PI );
        ctx.stroke();


        ctx.beginPath();
        ctx.strokeStyle = "red";
        ctx.lineWidth = "1";
        X = X - 5;
        ctx.rect(X,Y, 10, 10);
        ctx.stroke();
      }

      if(event.key === 'ArrowDown' && Y < canvas.height - 10) {
        console.log("pressdown")
        ctx.clearRect(0, 0, canvas.width, canvas.height);

        ctx.beginPath();
        ctx.strokeStyle = "black";
        ctx.lineWidth = "1";
        ctx.arc(CircleX, CircleY, 5, 0, 2*Math.PI );
        ctx.stroke();

        ctx.beginPath();
        ctx.strokeStyle = "red";
        ctx.lineWidth = "1";
        Y = Y + 5;
        ctx.rect(X,Y, 10, 10);
        ctx.stroke();
      }

      if(event.key === 'ArrowUp' && Y>0) {
        console.log("pressUp")
        ctx.clearRect(0, 0, canvas.width, canvas.height);

        ctx.beginPath();
        ctx.strokeStyle = "black";
        ctx.lineWidth = "1";
        ctx.arc(CircleX, CircleY, 5, 0, 2*Math.PI );
        ctx.stroke();


        ctx.beginPath();
        ctx.strokeStyle = "red";
        ctx.lineWidth = "1";
        Y = Y - 5;
        ctx.rect(X,Y, 10, 10);
        ctx.stroke();
      }
    });

  },
  data: () => ({
    count: 0
  })
}
</script>

<style>
body {
  margin: 0px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

canvas {
  width: 100%;
  border: 5px solid rgb(0, 0, 0);
}

html {
  overflow: hidden;
}
</style>
