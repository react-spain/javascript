# Mis Notas Javascript
Notas de Clases de Javascript

# HTML Mínimo
 ```
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript</title>
</head>
<body>
    <button onclick="presionoClick()">Boton</button>
    <script src="app.js"></script>
    <script type="text/javascript">
        var a = 1;
        var b = "fernando";
    </script>
</body>
</html>
 ```

# Console Log
 ```
console.log( a );
console.warn( a );
console.error( a );
console.info( a );
 ```

 # Button
 ```
 <button onclick="presionoClick()">Boton</button>
 
 function presionoClick(){
    console.log("Presiono");

}
 ```
 
 # Ciclo For
 ```
 function Imprimir(){
    for( var i=0; i<8000; i++ ){
        console.log("Imprimio");
    }
}
 ```
