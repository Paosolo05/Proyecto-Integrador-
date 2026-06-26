# Nombre del proyecto  
Juego del computador Adivina tu número
## Nombre
Paola Solorzano
## 📖 Introducción
A continuación, se presenta el análisis del programa desarrollado para el juego en el que la computadora debe adivinar un número del 1 al 100 que el usuario ha pensado. Se ha implementado el algoritmo de búsqueda binaria para garantizar que los intentos sean siempre los mínimos posibles. Dicho análisis se ha dividido en cuatro apartados: las funcionalidades del sistema, la estructura lógica del programa, la organización del código y las herramientas de desarrollo utilizadas.
## Objetivo del sistema
Implementar un algoritmo que mantenga dos variables (límite inferior y superior), calcule el punto medio en cada ronda, y actualice esos límites según la respuesta del usuario, asegurándose de que el rango nunca se vacíe y de detectar si el usuario está dando respuestas incoherentes.
## Funcionalidades del sistema 
Las funcionalidades principales que el sistema ofrece al usuario son las siguientes:
- **Adivinanza mediante punto medio**: La función central del sistema calcula el número situado en el centro del rango posible en cada turno. Por ejemplo, al iniciar con el rango de 1 a 100, la primera pregunta siempre es por el número 50, lo que permite descartar la mitad de las opciones en cada iteración.
- **Rango fijo predefinido**: Se han establecido los límites directamente en las variables minimo = 1 y maximo = 100. Aunque el rango podría modificarse en el futuro, para esta versión se ha dejado fijo según lo solicitado.
- **Validación de entradas**: El sistema solo acepta tres respuestas exactas: "mayor", "menor" o "correcto". Cualquier otra entrada (como "si", "no" o caracteres sueltos) es rechazada. El programa notifica al usuario del error y solicita una nueva respuesta sin contabilizar ese intento fallido.
- **Conteo de intentos**: Se lleva un registro numérico de cuántas preguntas ha realizado la máquina. Esto permite al usuario verificar que el objetivo de 7 intentos o menos se cumple.
- **Detección de contradicciones o respuestas erróneas**: Si el usuario proporciona respuestas lógicamente incoherentes (por ejemplo, decir "mayor" cuando ya no quedan números superiores), el rango de búsqueda se vacía. El programa detecta esta situación y finaliza la partida mostrando un mensaje de contradicción, sin llegar a adivinar el número.
- **Rejugabilidad**: Se ha incorporado un bucle en la función main() que permite al usuario jugar partidas de manera continua. Al finalizar cada ronda, el sistema pregunta si se desea jugar otra vez y solo finaliza la ejecución cuando el usuario responde "n".
## Estructura lógica del programa 
La lógica interna del programa sigue un flujo secuencial claro, basado en la reducción progresiva del rango de búsqueda. Dicho flujo se describe a continuación:
### 1.	Inicio y configuración inicial
Al ejecutar el archivo, se invoca la función main(), que a su vez llama a adivinar_numero(). Esta función muestra un encabezdo y solicita al usuario que piense en un número, deteniendo la ejecución con input("Presiona ENTER...") para dar tiempo al jugador.
### 2.	Preparación de la partida
Antes de comenzar las preguntas, se inicializan los límites del rango (minimo = 1, maximo = 100) y el contador de intentos se establece en cero.
### 3.	Bucle principal de adivinanzas
Se ejecuta un bucle while que se mantiene activo mientras minimo sea menor o igual a maximo. Dentro de este bucle:
-	Se calcula el punto medio mediante división entera: intento = (minimo + maximo)/2.
-	Se incrementa el contador de intentos.
-	Se muestra el número propuesto y se espera la respuesta del usuario.
### 4.	Procesamiento de la respuesta (árbol de decisión)
Mediante un bloque if/elif/else, se evalúa la entrada del usuario:
-	Si es "correcto", se muestra un mensaje de éxito con el número de intentos y se ejecuta return para finalizar la partida.
-	Si es "mayor", se actualiza el límite inferior: minimo = intento + 1.
-	Si es "menor", se actualiza el límite superior: maximo = intento - 1.
-	Si no es ninguna de las anteriores, se notifica el error y se decrementa el contador de intentos para no contabilizar esa respuesta inválida.
### 5.	Salida por fallo (contradicción)
Si el bucle while termina porque minimo ha superado a maximo, se interpreta que el usuario ha dado respuestas contradictorias. El programa imprime un mensaje informando de la imposibilidad de encontrar el número y finaliza la ronda sin éxito.
### 6.	Bucle externo de repetición
Una vez terminada la partida (por acierto o por fallo), el flujo regresa a main(), donde se pregunta al usuario si desea jugar nuevamente. Si la respuesta no es "s", se rompe el bucle y se muestra el mensaje de despedida.
## Organización del código 
## Uso de herramientas de desarrollo 
## Fecha 
28 de Junio del 2026
