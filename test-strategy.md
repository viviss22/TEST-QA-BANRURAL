Durante la revision del programa de Numeros a Adivinar se encontraron las siguientes areas de oportunidad

1. Cuando se realiza la inicializacion de la variable "randomNumber" es para generar numeros entre 1 a 100 que fue lo solicitado por el cliente, el codigo dice lo siguiente:

    let randomNumber = Math.random() * 10;

y la correccion seria la siguiente: 

    let randomNumber = Math.floor(Math.random() * 100) + 1; //  Math.random devuelve un numero de punto flotante que es mayor o igual a 0 y menor que 1 mientras        que Math.floor devuelte el entero mas grande o mejor por lo que siempre redondea.

2. Se debe corregir la constante declarada ATTEMPTS que significa intentos por lo cual estaba mal escrita "ATTEMPS" por lo cual no era reconocida, en la misma linea se puede percatar que solo solicita 5 intentos y el cliente solicito 10 intentos para poder adivinar el numero

3. En la linea 49 podremos darnos cuenta que la constante lowOrHi debe comezar con un (.) el cual no tiene 
    const lowOrHi = document.querySelector('lowOrHi');,
esto es para colocarlo como un selector de clase por lo que la expresion correcta seria la siguiente:
     const lowOrHi = document.querySelector('.lowOrHi');

4. En las lineas siguientes de codigo del numero 64 al numero 75 debemos corregir los colores de las alertas que necesitamos dar en nuestro programa, en la linea 65 y 66 indica que para el color negro indica la palabra 'perdiste' en negro y debemos colocarla en rojo, por lo que cambiamos la frase por la correcta 'Incorrecto' siendo esta la correcta en negro, en la linea 70 y 71 nos indica la frase 'Felicitaciones! adivinaste el numero' en rojo y la correcta en color rojo seria la palabra 'Perdiste' por lo que la sustituimos, y en la linea 74 y 75 nos encontramos con la palabra 'Incorrecto' en color verde por la que la cambiamos por la frase correcta 'Felicidades! adivinaste el numero'. siendo estos los colores de alerta solicitados por el cliente.

5. En la linea 87 nos encontramos con el evento siguiente
    guessSubmit.addeventListener('click', checkGuess); // siendo incorrecto ya que el evento addeventListener debe llevar en mayuscula la palabra Event.
por lo cual corregimos la linea
    guessSubmit.addEventListener('click', checkGuess); // agregamos mayuscula en la palabra Event

6. En la linea 95 nos encontramos con el evento siguiente
    resetButton.addeventListener('click', resetGame); // siendo incorrecto ya que el evento addeventListener debe llevar en mayuscula la palabra Event.
por lo cual corregimos la linea
    resetButton.addEventListener('click', resetGame); // agregamos mayuscula en la palabra Event

7. Cuando se realiza el nuevo calculo del numero aleatorio "randomNumber" , el codigo dice lo siguiente:

    randomNumber = Math.floor(Math.random()) + 1; // como podremos percatarnos no se realiza el calculo sobre los 100 numeros aleatorios, solamente los sumariza 

por lo que realizamos la correccion siguiente: 

    randomNumber = Math.floor(Math.random() * 100) + 1; 

8. al finalizar seguia mostrando un error solo nos dejaba visualizar el numero anterior solicitado por lo que se agrego en la linea 58 la palabra 'parseInt' para que pudiera convertir la cadena solicitada a un numero entero y asi se pudiera realizar una comparacion correctamente, siendo la linea anterior la siguiente:
     let userGuess = guessField.value; // agregando la palabra para poder hacer la conversion correcta
se agrega de la siguiente manera:
    let userGuess = parseInt(guessField.value);

9. Se ingreso una alerta para que se ingresara un numero valido entero y asi si se ingresaba un decimal no lo reconociera como entero y volviera a ingresarse el numero siendo el siguiente
    if (isNaN(userGuess) || !Number.isInteger(userGuess)) {
    alert('Por favor, ingresa un número entero válido.');
    return; }
// a pesar que se ingreso de igual manera nos reconoce los numeros antes del punto como entero, no hay inconveniente si se coloca con decimal.