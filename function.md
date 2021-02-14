# Obtenemos un parametro por la URL

```
function getParamURL(name) {
    return decodeURIComponent((new RegExp('[?|&]' + name + '=' + '([^&;]+?)(&|#|;|$)').exec(location.search)||[,""])[1].replace(/\+/g, '%20'))||null
  }
```

# Random entero entre dos intervalo

```
function randomEntre(min,max){
    return Math.floor( Math.random() * (max-min+1) + min);
}
```

# redondear a dos decimales

```
console.log( Math.round( numero*100  ) /100 );
```
