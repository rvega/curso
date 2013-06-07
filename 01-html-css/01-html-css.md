# 1. HTML y CSS

## 1.1. ¿Por qué HTML?

* Estándar abierto
* Portabilidad
* Fácil de programar
* Comúnidad gigante

## 1.2. Historia

* Lenguaje de marcado de documentos, inventado en 1989 por Tim Berners-Lee como formato para compartir documentos a través de Internet en el instituto CERN.
* Hipertexto y vínculos!
* Septiembre de 1991 empieza la discusión abierta sobre la web y el HTML.
* 1995: Netscape, Internet Explorer, tablas y hojas de estilos (Diseño gráfico, browser wars).
* 1996: Netscape 2.0 incluye JavaScript. Además de mostrar documentos, se pueden correr scripts.
* 1998: Microsoft inventa "Ajax" (Aplicaciones).
* 2008: Primer borrador del estándar de HTML5 (Rich applications).

## 1.3 Elementos básicos de HTML

    <!DOCTYPE HTML>
    <html>
        <head>
            <meta charset="utf-8"/>
            <title>Hola!</title>
        </head>
        <body>
            <p>
                Hola Mundo!
            </p>
        </body>
    </html>

## 1.4 Etiquetas y atributos

    <!--Esto es un comentario-->
    
    <!--Sub-titulo con identificador-->
    <h2 id="capitulo-1">Capítulo Uno</h2>

    <!--Links-->
    <a href="http://www.wikipedia.org/">Click aquí para Wikipedia</a>
    <a href="#capitulo-1">Click aquí para Wikipedia</a>

    <!--Inputs-->
    <form>
        <p>
            <label for="nombre">Nombre:</label><br/>
            <input type="text" id="nombre"/>
        </p>
        <p>
            <label for="si-o-no">¿Quiere?:</label> <input type="checkbox" id="si-o-no"/>
        </p>
    </form>

[Aqui hay una lista de etiquetas y sus atributos.](http://www.w3schools.com/tags/ref_byfunc.asp)
    

## 1.5 Estilos básicos

CSS es el lenguaje que se usa para definir los estilos de un documento HTML. 

Pueden ir definidos en el mismo documento, en una etiquieta &lt;style&gt;:

    <!DOCTYPE HTML>
    <html>
        <head>
            <meta charset="utf-8"/>
            <title>Hola!</title>
            <style type="text/css" media="all">
                /* Para todos los parrafos, usar esas fuentes, tamaño y color */
                p {
                    font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
                    font-size: 32px;
                    color: #777777;
                }
            </style>
        </head>
        <body>
            <p>
                Hola Mundo!
            </p>
        </body>
    </html>

O en un archivo externo:

    <!DOCTYPE HTML>
    <html>
        <head>
            <meta charset="utf-8"/>
            <title>Hola!</title>
            <link rel="stylesheet" href="estilos.css" type="text/css" media="all" />
        </head>
        <body>
            <p>
                Hola Mundo!
            </p>
        </body>
    </html>

estilos.css:

    /* Para todos los parrafos, usar esas fuentes, tamaño y color */
    p {
        font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
        font-size: 32px;
        color: #777777;
    }

O "inline" en el documento. Esto no se recomienda pero en ocasiones es necesario.

    <!DOCTYPE HTML>
    <html>
        <head>
            <meta charset="utf-8"/>
            <title>Hola!</title>
        </head>
        <body>
            <p style="color:#333333; font-size: 32px;">
                Hola Mundo!
            </p>
        </body>
    </html>

## 1.6 Selectores y propiedades

    <!DOCTYPE HTML>
    <html>
      <head>
        <meta charset="utf-8"/>
        <title>Hola!</title>
        <style type="text/css" media="all">
          p {
            color: #BBBBBB; 
          } 

          #principal .impar{
            background-color: #333333;
          }

          #principal *{
            font-size:24px;
            font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
          }
        </style>
      </head>
      <body>
        <div id="principal">
          <p class="impar">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
          </p>
          <p class="par">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 
          </p>
          <p class="impar rojo">
            Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident.
          </p>
          <p class="par">Sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
        </div>

        <p class="impar">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
        </p>
      </body>
    </html>

[Referencia de selectores](http://www.w3schools.com/cssref/css_selectors.asp)  
[Referencia de propiedades](http://www.w3schools.com/cssref/default.asp)


## 1.7. Ejecricio.

* (15 minutos) Copie cualquier texto de wikipedia, escribalo en HTML y crée un minimo de estilos para que el documento se vea bien. Incluya una imágen y listados usando &lt;img&gt;, &lt;ul&gt; y &lt;li&gt;.

* (Hagalo luego) Utilice tipografías mas interesantes de [Google Fonts](http://www.google.com/fonts/)

## 1.8. Diagramación


