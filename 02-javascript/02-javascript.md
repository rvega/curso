# 2. Javascript

## 2.1. Por qué JavaScript?

* Corre en los navegadores web.
* Corre en servidores web (node.js).
* Corre como lenguaje de scripting de otras aplicaciones (mongodb, postgres, otras?)

## 2.2 Introducción a JS

    //////////////////////////////////////
    // Basic Types
    var intValue = 1;
    var floatValue = 3.0;
    var stringValue = "This is a string\n";

    ///////////////////////////////////////
    // Array
    var emptyList = [];
    var homogenousList = [1, 2, 3];
    var heterogenousList = ["one", 2, 3.0];

    ///////////////////////////////////////
    // Property Map
    var emptyMap = {};
    var homogenousMap = {"one": 1, "two": 2, "three": 3};
    var heterogenousMap = {"one": 1, "two": "two", "three": 3.0};

    ///////////////////////////////////////
    // Functions as values
    var callable = function (message) { // <-- notice assignment
        window.alert("Callable called with message = "
                     + message);
    }

    function createClosure(initial) {
        var res = function () {
            initial = initial + 1;
            window.alert("Closure with modified state "
                         + initial);
        }
        return res;
    }

    ///////////////////////////////////////
    // Functions as arguments
    function callCallable(f, x) {
        f(x);
    }

    function composeCallables(f, g, x) {
        f(g(x));
    }

    ///////////////////////////////////////
    // Objects
    function MyObject(name, value) {
        this.name = name;
        this.value = value;
    }

    ///////////////////////////////////////
    // Objects with Member Functions
    function Message(message) {
        this.message = message;
        this.show = function() {
            console.log("Message.show() with message = " + this.message);
        }
    }

## 2.3. Document Object Model

    <article id="primer_articulo">
        <h1>Titulo del artículo</h1>
        <p class="resumen"><img src="http://foo.com/bar.jpg" alt="Una foto cuadrada y nítida">Blah Blah Blah Blah</p>
    </article>

    <script type="text/javascript">
        var image = document.getElementById('primer_articulo').childNodes[3].childNodes[0];
        for( var x = 0; x < image.attributes.length; x++ ) {
           if( image.attributes[x].nodeName.toLowerCase() == 'alt' ) {
               window.alert('El alt de la imagen es: ' + image.attributes[x].nodeValue );
           }
       }
    </script>

# 2.4. jQuery

    <!DOCTYPE HTML>
    <html>
    <head>
       <meta http-equiv="content-type" content="text/html; charset=utf-8">

       <title>Parrafos</title>

       <style type="text/css" media="screen">
          p {
             font-family: "Helvetica Neue", "Helvetica", "Arial", "sans-serif";
             font-size:18px;
             color: #333;
             border: 1px solid #AAA; 
             width:400px;
             margin:20px auto;
             cursor: pointer;
          }
       </style>
    </head>
    <body>

       <p> Readymade quinoa beard shoreditch bicycle rights. Synth tofu ethical, biodiesel before they sold out PBR messenger bag readymade mcsweeney’s seitan echo park brooklyn pitchfork wayfarers tumblr. Quinoa bicycle rights salvia, mlkshk carles yr tattooed marfa high life helvetica artisan wayfarers next level butcher gluten-free.  </p>
       <p> Readymade quinoa beard shoreditch bicycle rights. Synth tofu ethical, biodiesel before they sold out PBR messenger bag readymade mcsweeney’s seitan echo park brooklyn pitchfork wayfarers tumblr. Quinoa bicycle rights salvia, mlkshk carles yr tattooed marfa high life helvetica artisan wayfarers next level butcher gluten-free.  </p>
       <p> Readymade quinoa beard shoreditch bicycle rights. Synth tofu ethical, biodiesel before they sold out PBR messenger bag readymade mcsweeney’s seitan echo park brooklyn pitchfork wayfarers tumblr. Quinoa bicycle rights salvia, mlkshk carles yr tattooed marfa high life helvetica artisan wayfarers next level butcher gluten-free.  </p>
       <p> Readymade quinoa beard shoreditch bicycle rights. Synth tofu ethical, biodiesel before they sold out PBR messenger bag readymade mcsweeney’s seitan echo park brooklyn pitchfork wayfarers tumblr. Quinoa bicycle rights salvia, mlkshk carles yr tattooed marfa high life helvetica artisan wayfarers next level butcher gluten-free.  </p>


       <script src="jquery-1.7.1.min.js" type="text/javascript"></script>
       <script src="jquery.color.min.js" type="text/javascript"></script>
       <script type="text/javascript" charset="utf-8">
          $(document).ready(function(){

             $('p').click(function(){
                 $('p').animate({
                     'color':"#333",
                     'font-size': '18px',
                     'padding': '0px'
                 });

                $(this).animate({
                   'color':"#0000AA",
                   'font-size': '22px',
                   'padding': '10px'
                });
             });      
          });
       </script>
    </body>
    </html>

## Ejercicio

* (20 minutos) Inventese y programe un juego de "choose your own story". Use las funciones prompt(), confirm() y console.log().

* (2 hora) Haga que el ejercicio de la lista de To-Dos funcione.
