

Funciones para leer html desde java script, estas funciones solo sirven si ejecutamos java script desde el navegador, no sirven en el backend

const h1 = document.querySelector('h1'):En esta funcion tenemos en un string en cual ponemos el selector con el cual queremos seleccionar el elemento en html en este caso es 'h1' 
Si queremos tabajar con clases simplente ponemos el . y el nombre de la clase ejemplo .parrafito.
lo mismo se hace con los Id solamente que esta vez se pone el # antes del nombre del id ejemplo #pid.

const p = document.querySelector('p'): si queremos seleccionar un parrafo 
const parrafito = document.getElementsByClassName('.parrafito'):seleccionar una clase
const pid = document.getElementById('pid'):seleccionar un id
const input = document.querySelector('input'):seleccionar un inputa

Para ver todas las propiedades en la consola debo escribir lo siguiente, si entro a cualquiera por ejemplo al h1, se despliegan todas las propiedades de ese elemento y si accedemos desde java script a alguna de esas propiedades me va mostrar la clase, el valor, si tiene un id, nos puede ayudar a escuchar eventos ya sean de click o que pasen el mouse por encima etc.
console.log({
    h1,
    p,
    parrafito,
    pid,
    input,
});
ejemplo:
console.log(input.value);:me muestra el valor que tiene la propiedad value del input

Como escribir html desde java script

h1.innerHTML = 'Patito <br> Feo';:la propiedad innerHTML nos permite modificar el html dentro de la etiqueta que seleccionemos, tiene un riesgo y es que convierte todo a html y es posible que se modifcado por un agente externo
h1.innerText = 'Patito <br> Feo';:si queremos protegernos de ataques envés de poner innerHTML ponesmos innerText el cual convierto todo a texto no a codigo html por lo cual no es posible modificar el codigo.


h1.getAttribute('pantalla'): nos ayuda a leer alguno de los atributos que tenga nuestro elemento console.log(h1.getAttribute('pantalla')); me va mostrar en la consola lo que este en ese atributo pantalla.

Si queremos modifcar un atributo usamos escribimos el siguiente codigo:
h1.setAttribute('class', 'rojo'); esta es una forma para modificar nuestros atributos en html
si queremos modificar clases exite un atributo mas especifico classList.add(),
h1.classList.add('rojo'); para aderir el rojo a nuestra clase
h1.classList.remove('Verde');para remover el verde de nuestra clase
h1.classList.toggle('Verde');
h1.classList.contains('Verde');

input.value = '547'

Como crear un elemento desde cero, se hace con document.createElement(''):en el string puedes poner el elemento html que queramo puede ser una imagen, un span, etc
un ejemplo es el siguiente 
const img = document.createElement('img');
Para hacer que nuestra imagen no solo aparesca en la cosola si no que aparesca para los usuarios se hace lo siguiente
img.setAttribute('src', 'https://i.pinimg.com/564x/c2/5b/95/c25b955741dfae646f5127e0b0f6d74a.jpg');
console.log(img);
Para meter la imagen en alguna parte se pueden usar la siguientes 2 opciones 
pid.innerHTML = '';
pid.append(img);:tambien podemos poner pid.appenChild(img) 

Importante: Cuando desde el nombre de la funcion del metodo selector estamos diciendo que queremos seleccionar una clase o un id ya no tenemos que poner el . o el # (clase numero 12 de platzi)


Escuchar eventos de html desde java script
Una de las formas auque no la ideal es con el atrubuto onlclick en cada evento que queremos escuchar pero lo mejor es crear una funcion en java script ejemplo 

function btnOnclick() {}: a esta funcion le podemos hacer un console.log
function btnOnclick() {
    console.log('escuchando el evento de click');
}

Conectando GitHub a proyecto de JavaScript

Importante realizar un gitignore para evitar las carpetas que no nos van a servir y que pesan demasiado 