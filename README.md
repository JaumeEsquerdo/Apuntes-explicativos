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