# Mis Notas Javascript
Notas de Clases de Javascript

# Notas
- Las funciones son objetos
- Si nombras las funciones haslo de esta forma: "estoEsUnaFuncion" se llama letra de caja camello (estilizado como CamelCase)

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
 
# Tipos de datos o variables en Javascript
 ```
// Tipos primitivos
var num = 10
var str = "texto";
var bol = true;
var und = undefined;
var mynull = null;
console.log( num )

// Objetos
var obj = {
    numero: 10,
    texto: "Nuevo Texto",

    objHijo: {
        numero2: 20,
        text2: "Nuevo texto 2"
    }
};
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
 
 
# Funciones
 ```
 function imprimir( nombre,apellido ){
    // Si esta definidio el apellido es apellido sino BBB
    apellido = apellido || "BBB"
    console.log( nombre + " " + apellido );
}

imprimir( "Juan");
 ```

# Funciones con IF Else
 ```
function obtenerAleatorio(){
    return Math.random();
}

function esMayor05(){
    if ( obtenerAleatorio() > 0.5 ){
        return true;
    }else{
        return false;
    }
}

console.log( esMayor05() );
 ```
