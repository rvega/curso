# 3. Programación Gráfica

* &lt;svg&gt;
* &lt;canvas&gt;

Así como con el DOM y jQuery, las APIs nativas de svg y canvas no son muy prácticas y existen varias librerías para hacer mas fácil el trabajo. Miremos [KineticJS](http://kineticjs.com/)

## 3.1 KineticJS

    <!DOCTYPE HTML>
    <html>
      <head>
        <style>
          body {
            margin: 0px;
            padding: 0px;
          }
        </style>
      </head>
      <body>
        <div id="container"></div>
        <script src="http://www.html5canvastutorials.com/libraries/kinetic-v4.5.4-beta.js"></script>
        <script defer="defer">
          var stage = new Kinetic.Stage({
            container: 'container',
            width: 578,
            height: 200
          });

          var layer = new Kinetic.Layer();

          var rect = new Kinetic.Rect({
            x: 239,
            y: 75,
            width: 100,
            height: 50,
            fill: 'green',
            stroke: 'black',
            strokeWidth: 4
          });

          // add the shape to the layer
          layer.add(rect);

          // add the layer to the stage
          stage.add(layer);
        </script>
      </body>
    </html>

## 3.2 Tweens

    <!DOCTYPE HTML>
    <html>
      <head>
        <style>
          body {
            margin: 0px;
            padding: 0px;
          }
        </style>
      </head>
      <body>
        <div id="container"></div>
        <script src="http://www.html5canvastutorials.com/libraries/kinetic-v4.5.4-beta.js"></script>
        <script defer="defer">
          var stage = new Kinetic.Stage({
            container: 'container',
            width: 578,
            height: 200
          });
          var layer = new Kinetic.Layer();
          var rect = new Kinetic.Rect({
            x: 100,
            y: 100,
            width: 100,
            height: 50,
            fill: 'green',
            stroke: 'black',
            strokeWidth: 2,
            opacity: 0.2
          });

          layer.add(rect);
          stage.add(layer);

          var tween = new Kinetic.Tween({
            node: rect, 
            duration: 1,
            x: 400,
            y: 30,
            rotation: Math.PI * 2,
            opacity: 1,
            strokeWidth: 6,
            scaleX: 1.5
          });
          
          // start tween after 20 seconds
          setTimeout(function() {
            tween.play();
          }, 2000);
        </script>
      </body>
    </html>

## 3.3 Animaciones 

    <!DOCTYPE HTML>
    <html>
      <head>
        <style>
          body {
            margin: 0px;
            padding: 0px;
          }
        </style>
      </head>
      <body>
        <div id="container"></div>
        <script src="http://www.html5canvastutorials.com/libraries/kinetic-v4.5.4-beta.js"></script>
        <script defer="defer">
          var stage = new Kinetic.Stage({
            container: 'container',
            width: 578,
            height: 200
          });
          var layer = new Kinetic.Layer();

          var hexagon = new Kinetic.RegularPolygon({
            x: stage.getWidth() / 2,
            y: stage.getHeight() / 2,
            sides: 6,
            radius: 70,
            fill: 'red',
            stroke: 'black',
            strokeWidth: 4
          });

          layer.add(hexagon);
          stage.add(layer);

          var amplitude = 150;
          var period = 2000;
          // in ms
          var centerX = stage.getWidth() / 2;

          var anim = new Kinetic.Animation(function(frame) {
            hexagon.setX(amplitude * Math.sin(frame.time * 2 * Math.PI / period) + centerX);
          }, layer);

          anim.start();

        </script>
      </body>
    </html>

## 3.4 Eventos

    <!DOCTYPE HTML>
    <html>
      <head>
        <style>
          body {
            margin: 0px;
            padding: 0px;
          }
        </style>
      </head>
      <body>
        <div id="container"></div>
        <script src="http://www.html5canvastutorials.com/libraries/kinetic-v4.5.4-beta.js"></script>
        <script defer="defer">
          function writeMessage(messageLayer, message) {
            var context = messageLayer.getContext();
            messageLayer.clear();
            context.font = '18pt Calibri';
            context.fillStyle = 'black';
            context.fillText(message, 10, 25);
          }
          var stage = new Kinetic.Stage({
            container: 'container',
            width: 578,
            height: 200
          });
          var shapesLayer = new Kinetic.Layer();
          var messageLayer = new Kinetic.Layer();

          var triangle = new Kinetic.RegularPolygon({
            x: 190,
            y: 120,
            sides: 3,
            radius: 80,
            fill: '#00D2FF',
            stroke: 'black',
            strokeWidth: 4
          });

          triangle.on('mouseout', function() {
            writeMessage(messageLayer, 'Mouseout triangle');
          });

          triangle.on('mousemove', function() {
            var mousePos = stage.getMousePosition();
            var x = mousePos.x - 190;
            var y = mousePos.y - 40;
            writeMessage(messageLayer, 'x: ' + x + ', y: ' + y);
          });

          shapesLayer.add(triangle);

          var circle = new Kinetic.Circle({
            x: 380,
            y: stage.getHeight() / 2,
            radius: 70,
            fill: 'red',
            stroke: 'black',
            strokeWidth: 4
          });

          circle.on('mouseover', function() {
            writeMessage(messageLayer, 'Mouseover circle');
          });
          circle.on('mouseout', function() {
            writeMessage(messageLayer, 'Mouseout circle');
          });
          circle.on('mousedown', function() {
            writeMessage(messageLayer, 'Mousedown circle');
          });
          circle.on('mouseup', function() {
            writeMessage(messageLayer, 'Mouseup circle');
          });

          shapesLayer.add(circle);

          stage.add(shapesLayer);
          stage.add(messageLayer);
        </script>
      </body>
    </html>

## 3.5. Ejercicio

* Facil: tarea.html
* Mediano: Pong
