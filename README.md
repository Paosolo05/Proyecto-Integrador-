# Nombre del proyecto  
Juego del computador Adivina tu número
## Nombre
Paola Solorzano
## Objetivo del sistema
Implementar un algoritmo que mantenga dos variables (límite inferior y superior), calcule el punto medio en cada ronda, y actualice esos límites según la respuesta del usuario, asegurándose de que el rango nunca se vacíe y de detectar si el usuario está dando respuestas incoherentes.
## Introducción
A continuación, se presenta el análisis del programa desarrollado para el juego en el que la computadora debe adivinar un número del 1 al 100 que el usuario ha pensado. Se ha implementado el algoritmo de búsqueda binaria para garantizar que los intentos sean siempre los mínimos posibles. Dicho análisis se ha dividido en cuatro apartados: las funcionalidades del sistema, la estructura lógica del programa, la organización del código y las herramientas de desarrollo utilizadas.
## Funcionalidades del sistema 
Las funcionalidades principales que el sistema ofrece al usuario son las siguientes:
- **Adivinanza mediante punto medio**: La función central del sistema calcula el número situado en el centro del rango posible en cada turno. Por ejemplo, al iniciar con el rango de 1 a 100, la primera pregunta siempre es por el número 50, lo que permite descartar la mitad de las opciones en cada iteración.
- **Rango fijo predefinido**: Se han establecido los límites directamente en las variables minimo = 1 y maximo = 100. Aunque el rango podría modificarse en el futuro, para esta versión se ha dejado fijo según lo solicitado.
- **Validación de entradas**: El sistema solo acepta tres respuestas exactas: "mayor", "menor" o "correcto". Cualquier otra entrada (como "si", "no" o caracteres sueltos) es rechazada. El programa notifica al usuario del error y solicita una nueva respuesta sin contabilizar ese intento fallido.
- **Conteo de intentos**: Se lleva un registro numérico de cuántas preguntas ha realizado la máquina. Esto permite al usuario verificar que el objetivo de 7 intentos o menos se cumple.
- **Detección de contradicciones o respuestas erróneas**: Si el usuario proporciona respuestas lógicamente incoherentes (por ejemplo, decir "mayor" cuando ya no quedan números superiores), el rango de búsqueda se vacía. El programa detecta esta situación y finaliza la partida mostrando un mensaje de contradicción, sin llegar a adivinar el número.
- **Rejugabilidad**: Se ha incorporado un bucle en la función main() que permite al usuario jugar partidas de manera continua. Al finalizar cada ronda, el sistema pregunta si se desea jugar otra vez y solo finaliza la ejecución cuando el usuario responde "n".
## Estructura lógica del programa 
## Organización del código 
## Uso de herramientas de desarrollo 
## Fecha 
28 de Junio del 2026
