# Funcionamiento de acordeón

```js
const li = document.querySelectorAll('.li');
const bloque = document.querySelectorAll('.bloque');

//Recorremos todos los li
li.forEach((cadaLi,i)=>{
    //asignamos el evento 'click' a todos los li
    li[i].addEventListener('click',()=>{

        //recorremos otra vez los li
        li.forEach((cadaLi,i)=>{
            //quitamos la clase activo de todos los li(para que deje de aplicarse a cualquier otro li que estuviera activo)
            li[i].classList.remove('activo');
            bloque[i].classList.remove('activo');
        });

        //en el li que hacemos click añadimos la clase activo
        li[i].classList.add('activo');
        //en el bloque también añadimos la clase activo
        bloque[i].classList.add('activo');
    });
});
```

# While

Primero pregunta la condición y después en caso de true, ejecuta el código.

```js

while (numero <= 6) {
    numero++;
    document.write(numero+"<br>");
}

```

# Do While

Primero ejecuta una vez luego llega al while a preguntar la condición y después vuelve a ejecutar si el while es true
```js
do{
    document.write(numero + "br");
    numero++;
} while (numero<6)

//otro ejemplo para utilizar while y frenar en algún punto:

while(numero < 100){
    numero++;
    
    if (numero == 10){ //pararía en el 10
        break; 
    }
    document.write(numero);
}
```

# For

```js

for (let i = 0; i<6; i++){
    document.write(i+ "<br>")
 if(numero==4){
    continue; //aqui hace un stop en 4 y lo salta;
}
}
```

```js
let animales = ["gato", "perro", "tiranosaurio rex"];

for (animal in animales){
    document.write(animal + "br"); //muestra la posición (el indice)
}

document.write("<br>");

for (animal of animales){
    document.write(animal + "br"); //muestra el valor de la posición es decir el contenido
}



array1 = ["maría", "josefa", "roberta"];
array2 = ["pedro", "marcelo", array1];

forRancio: //ESTO ES UNA ETIQUETA
for (let array in array2){
    if (array == 2) {
        for
    }break forRancio; //para toda la etiqueta
}

```
# Function

```js
// las funciones tienes dos partes (lo que hace, y como la llamamos)
function saludar(){
    respuesta = prompt("Hola que tal fue tu dia?");
    if (respuesta == "bien"){
        alert("me alegro")
    } else{
        alert("una pena")
    };
    return " la función se ejecutó bien" //el return también hace que se termine la función, lo que pusieramos después de aqui en el scope local no se guardaría
};

saludar() //esto es llamar a la función

let saludo = saludar();
document.write(saludo)
```

```js

function suma(num1,num2){ //parámetros
    let res = num1 + num2;
    document.write(res);
    document.write("br")
}
suma(12,32) //argumentos  
suma(33,44)


//otro ejemplo
function suma(num1,num2){
    let res = num1 + num2;
    return res
}

let resultado = suma(20,25)


//otro ejemplo

function saludar(nombre){
    let frase = `Hola ${nombre}, que tal`;
    document.write(frase)
}
saludar("Manolo")


//otro ej
const saludar = function(nombre){
    let frase = `Hola ${nombre}, que tal`;
    document.write(frase)
    }

    saludar("pedro")

    // funcion flecha

    const saludar = (nombre) => {
    let frase = `Hola ${nombre}, que tal`;
    document.write(frase)
    }
    saludar("pedro")


```



