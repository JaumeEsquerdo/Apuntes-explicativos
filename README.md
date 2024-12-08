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

# Ejercicio  Problema B

- Crear mini-sistema para registrar presentes y ausentes

- Pasados 30 días, mostrar situación final del alumno

- Maximo de 10% de ausencias

- Crear calculadora para simplificar trabajo

```html


```


```js

let free = false;

const validarCliente = (time) => {
    let edad = prompt("Cual es tu edad?")
    if(edad > 18){
        if(time >= 2 && time < 7 && free == false){
            alert("puedes pasar gratis");
            free = true;
        } else{
            alert(`son las ${time}:00Hs puedes, pasar pero pagando entrada`);
        }

    } else {
    alert("fuera no puedes pasar, eres menor");
    }
}

validarCliente(23)

```
```js

let cantidad = prompt("cuantos alumnos son?");
let alumnosTotales = [];

for(i=0; i < cantidad; i++){
    alumnosTotales[i]= [prompt("nombre del alumno " + (i+1)),0] //el 0 es la cantidad de asistencias
}
//alumnosTotales que es un array tiene otro array dentro con el nombre y la cantidad de asistencias
//entonces en alumnosTotales[i][1]++; aqui estaría la i seleccionando la posicion del array y el[1 estaría cogiendo el segundo elemento del array de dentro, es decir si es nombre y asistencias, cogeria la asistencia]

const tomarAsistencia = (nombre, p)=>{ //p aqui es la posicion en la lista
    let presencia = prompt(nombre);
    if(presencia == "p"|| presencia == "P"){
        alumnosTotales[p][1]++;
    }
}

for (i=0; i<30; i++){
    for(alumno in alumnosTotales){ //in pasa la posición si fuese OF pasaria el valor
        tomarAsistencia(alumnosTotales[alumno][0],alumno);
    }
}

for (alumno in alumnosTotales){
    let resultado = `${alumnosTotales[alumno][0]}: 
    ....Presentes: ${alumnosTotales[alumno][1]}:
    .....Ausencias: ${30- pasrseInt(alumnosTotales[alumno][1])}  `;
}
if (30 - alumnosTotales[alumno][1] > 18){
    resultado += "suspendido por asistencias";
} else{
    resultado += "";
}
document.write(resultado);

```

```js
const sumar = (num1,num2)=>{
    return parseInt(num1)+ parseInt(num2);
}
const restar = (num1,num2)=>{
    return parseInt(num1)- parseInt(num2);
}
const dividir = (num1,num2)=>{
    return parseInt(num1)/ parseInt(num2);
}
const multiplicar = (num1,num2)=>{
    return parseInt(num1)* parseInt(num2);
}

alert("que operacion quieres hacer?");
let operacion = prompt("1:suma,2:resta,3:dividir,4:multiplicar");

if (operacion ==1){
    let numero1= prompt("primer numero para sumar");
    let numero2= prompt("segundo numero para sumar");
    resultado = suma(numero1,numero2);
    alert(`tu resultado es ${resultado}`);
}
else if (operacion ==2){
    let numero1= prompt("primer numero para restar");
    let numero2= prompt("segundo numero para restar");
    resultado = resta(numero1,numero2);
    alert(`tu resultado es ${resultado}`);
}

else if (operacion ==3){
    let numero1= prompt("primer numero para dividir");
    let numero2= prompt("segundo numero para dividir");
    resultado = dividir(numero1,numero2);
    alert(`tu resultado es ${resultado}`);
}

else if (operacion ==4){
    let numero1= prompt("primer numero para multiplicar");
    let numero2= prompt("segundo numero para multiplicar");
    resultado = multiplicar(numero1,numero2);
    alert(`tu resultado es ${resultado}`);
}
else{
    alert("no se ha encontrado la operacion");
};


