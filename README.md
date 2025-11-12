Estes es el "read me" de mi repositorio.. Te informo que aqui 
solo encontraras el ejercicio Resuelto de la tarea grupal S3 Unemi.

function normalizarEspaciosConBucle(texto) {
    let resultado = '';
    let eraEspacio = false; // Variable para rastrear si el carácter anterior era un espacio

    Primero, eliminamos los espacios iniciales y finales para simplificar la lógica del bucle.
    Esto se puede hacer con otro bucle si es estrictamente necesario, pero trim() es simple.
    Si no puedes usar trim(), el bucle principal debe manejar los espacios iniciales.

    ///Implementación sin trim():
    let inicio = 0;
    let fin = texto.length - 1;

    // Encontrar el primer carácter no espacial
    while (inicio <= fin && texto[inicio] === ' ') {
        inicio++;
    }

    // Encontrar el último carácter no espacial
    while (fin >= inicio && texto[fin] === ' ') {
        fin--;
    }

    // Iterar solo sobre la parte relevante del texto
    for (let i = inicio; i <= fin; i++) {
        let caracterActual = texto[i];

        if (caracterActual === ' ') {
            // Si es un espacio, solo lo añadimos si el caracter anterior NO era un espacio
            if (!eraEspacio) {
                resultado += caracterActual;
                eraEspacio = true;
            }
        } else {
            // Si no es un espacio, siempre lo añadimos
            resultado += caracterActual;
            eraEspacio = false;
        }
    }
    return resultado;
}

// Ejemplo de uso:
let fraseOriginal = "hola     mundo       que      tal";
let fraseNormalizada = normalizarEspaciosConBucle(fraseOriginal);
console.log("Original:", fraseOriginal);
console.log("Normalizada:", fraseNormalizada);

O tambien:

let frase1 = prompt("Ingrese la frase (ej: 'hola     mundo       que      tal')");
let fraseProcesada = normalizarEspaciosConBucle(frase1);
console.log("Aquí esta la frase con espacios normalizados: " + fraseProcesada);
