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

    function CheckColision() {
      if (CircleX - X < 5 && CircleY - Y < 5){
        CircleX = Math.random()*canvas.width;
        CircleY = Math.random()*canvas.height;
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        DrawCircle()
        DrawRect()
      } 
    }
  
    function DrawRect () {
      ctx.beginPath();
      ctx.strokeStyle = "purple";
      ctx.lineWidth = "1";
      ctx.rect(X, Y, 10, 10);
      ctx.stroke();
    }

    function DrawCircle () {
      ctx.beginPath();
      ctx.strokeStyle = "blue";
      ctx.lineWidth = "1";
      ctx.arc(CircleX, CircleY, 5, 0, 2*Math.PI );
      ctx.stroke();
    }

    DrawRect();

    DrawCircle();

    document.addEventListener('keydown', function(event) {
      
      if(event.key === 'ArrowRight' && X < canvas.width - 10) {
        ctx.clearRect(0, 0, canvas.width, canvas.height);

        DrawCircle();
        
        X = X + 5

        DrawRect ();

        CheckColision() 
      }

      if(event.key === 'ArrowLeft' && X>0) {
        ctx.clearRect(0, 0, canvas.width, canvas.height);

        DrawCircle();

        X = X - 5;
        
        DrawRect();

        CheckColision()
      }

      if(event.key === 'ArrowDown' && Y < canvas.height - 10) {
        ctx.clearRect(0, 0, canvas.width, canvas.height);

        DrawCircle();

        Y = Y + 5;

        DrawRect();

        CheckColision()
      }

      if(event.key === 'ArrowUp' && Y>0) {
        ctx.clearRect(0, 0, canvas.width, canvas.height);

        DrawCircle();

        Y = Y - 5;
        
        DrawRect();

        CheckColision()
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
