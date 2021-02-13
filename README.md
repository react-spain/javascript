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
 
 # Objetos
 ```
 
 var persona = {
    nombre: "Maria",
    apellido: "Demo",
    imprimirNombre: function(){
        console.log( this.nombre );
    },
    direccion:{
        pais: "Costa Rica",
        obtenerPais: function(){
            console.log( this.pais );
            var self = this;
            var nuevaDireccion = function(){
                console.log( self );
                console.log( self.pais );
            }
            nuevaDireccion();
        }
    }
};

persona.imprimirNombre();
persona.direccion.obtenerPais();
 ```
 
  # Objetos con New
 ```
 
 // Inicia con Mayúscula para definir que es una funcion de primera clase.
function Persona(nombre){
    this.nombre = nombre;
    this.apellido = "Mendoza";
    this.edad = 32;

    this.nombreCompleto = function(){
        return this.nombre + " " + this.apellido;
    }
}


var juan = new Persona("Juan");
console.log( juan );
console.log( juan.nombre );
console.log( juan.nombreCompleto() );
 ```

# Juego Demo 1
 ```
function Jugador( nombre ){
    this.nombre = nombre;
    this.pv = 100;
    this.sp = 100;

    this.curar = function( jugadorObjetivo ){
        if (this.sp >= 40){
            this.sp -= 40;
            jugadorObjetivo.pv +=  20;
        }else{
            console.info(this.nombre + " no tiene SP");
        }
        this.estado( jugadorObjetivo );
        
    }

    this.tirarFlecha = function ( jugadorObjetivo ){
        if (jugadorObjetivo.pv > 40){
            jugadorObjetivo.pv -=40;
        }else{
            jugadorObjetivo.pv = 0;
            console.error( jugadorObjetivo.nombre + "murio !!") 
        }
        this.estado( jugadorObjetivo );
        
    }

    this.estado = function(jugadorObjetivo){
        console.info(this);
        console.info(jugadorObjetivo);
    }
}

var gandalF = new Jugador("Gandalf");
var legola = new Jugador("Legola");

console.log( gandalF );
console.log( legola );
 ```
 
# Prototipo
```
 function Persona(){
    this.nombre = "Fernando";
    this.apellido = "Herrera";
    this.edad = 30;
    this.pais = "Costa Rica";
}

// Persona.prototype.pais = "Costa Rica";

Persona.prototype.imprimirInfo = function(){
    console.log( this.nombre + " " + this.apellido)
}
var fer = new Persona();
var a = "Fernando"
 ```
 
 # Prototipo Numero ampliar
```
 Number.prototype.esPositivo = function(){
    if(this > 0){
        return true;
    }else{
        return false;
    }
}
 ```
 
# Funciones Anónimas
  ```
 (function(){
    var a = 10;
    console.log(a);
    function cambiarA(){
        a = 20;
    }
    console.info( a );
})();
 ```
  ```
 function ejecutarFuncion( fn ){
    if(fn() === 1){
        return true;
    }else{
        return false;
    }
}
console.log(
ejecutarFuncion( function(){
  console.log("Funcion Anonima");
  return 1;
})
);
 ```
 
 # typeof
  ```
 function identifica( param ){
    if ( typeof param == "function"){
        param();
    }else{
        console.log( param );
    }
}

function Persona(){
    this.nombre = "Fernando";
    this.edad = 30;
}

var juan = new Persona

identifica(function(){ console.log("soy anonima"); });
 ```
 
# Arreglo
```
var arr1 = new Array();
var arr = [5,4,3,2,1];
console.log(arr);

// Invertir Arreglo
arr.reverse();
console.log(arr);

// Map de un array
arr = arr.map( function(elem){
    elem *= elem;
    return elem;
});
console.log(arr);

// Raiz cuadrada de array
arr = arr.map( Math.sqrt )
console.log(arr);

// Toma el arreglo y lo pega
arr = arr.join(".");
console.log(arr);

// Pasa a Arreglo
arr = arr.split(".");
console.log(arr);

// Agregando un arreglo al Final
arr.push("6")
console.log(arr);

// Agregando un arreglo al Inicio
arr.unshift("0");
console.log(arr);

console.log(arr.toLocaleString());

// Eliminar ultimo elemento con POP
var elimine = arr.pop();
console.log(arr, elimine);

// Ve a la posision 1 y elimima 1 y agrega 10
arr.splice( 1, 1, "10" );
console.log(arr);

// Cortar el arreglo
arr = arr.slice(0,2);
console.log(arr);
```

 
# Arreglo con Funciones Anónimas y Objetos Anónimos
```
// bool
// Objeto Anónimo
// Funcion Anónima
var arr = [
    true,
    {
        nombre: "Marlon",
        apellido: "Falcon"
    },
    true,
    function(){
        console.log("Estoy aqui")
    },
    function(persona){
        console.log(persona.nombre)
    }
];
console.log(arr[1].nombre);

// LLamada a la funcion anonima de la posicion 2
arr[3]();
arr[4](arr[1]);
```

# Validación de Argumentos en una Función
```
function miFuncion(a,b){
    if(arguments.length !== 4 )
    {
        console.error("Los parametros tienen que ser 4");
        return;
    }
    console.log( arguments );
    console.log (a+b);
}
miFuncion(10,20);
```

# Funciones que llaman a Funciones
```
function crearProductos(nombre, precio){
    nombre = nombre || "sin Nombre";
    precio = precio || 0;
    console.log ("Producto ", nombre, "Precio ", precio);
}

function crearProductos100(nombre){
    crearProductos(nombre,100)
}

crearProductos("Lapiz");
crearProductos100("Corrector");
```

# Number
```
// Number
var a = 10.21212121;
console.log( a.toFixed(4) );
console.log( a.toString());
console.log( a.toPrecision(4));

a = 10;
a *= 2

console.log( a );

var b = new Number("20");
console.log( b );
console.log( b.valueOf() );
```

# Fechas
```
var hoy = new Date();
console.log(hoy);

var fMili = new Date(0);
console.log(fMili);

var fFija = new Date(1980,06,20);
console.log(fFija);
// Sun Jul 20 1980 00:00:00 GMT+0200

// 2022
console.log( hoy.getFullYear() + 1 );
// 13
console.log( hoy.getDay() );
// 12
console.log( hoy.getHours() );
```
```
var hoy = new Date();
console.log(hoy);

var fMili = new Date(0);
var inicio = new Date();

for (var i=0; i< 5000; i++){
    console.log("Algo");
}

var fin = new Date();

// console.log( inicio );
// console.log( fin );

var duraccion = fin.getTime() - inicio.getTime();
console.log("Duracion milisegundos:" , duraccion);
console.log("Duracion Segundos:" , duraccion/1000);
```

# Creando prototipos para sumar fechas
```
var fecha = new Date(2016,9,20);

// Sumar Días
Date.prototype.sumarDias = function(dias){
    this.setDate(this.getDate() + dias);
    return this;
}
Date.prototype.sumarAnios = function(anios){
    this.setFullYear(this.getFullYear() + anios);
    return this;
}

console.log(fecha);
console.log(fecha.sumarDias(5));
console.log(fecha.sumarAnios(5));
```
