# Imitacion_Learning_Atari_Breakout

El tipico modelo de Aprendisaje por imitacion del juego del Atari BreakOut y otros ha sido adaptado con otra una version personalizada

Paso 1:
en vez de aprende de un modelo experto o un humano, ahora debe aprender de un algoritmo que analiza la posicion de la bola y la barra

Paso 2:
en vez de utilizar la DQN con una red convolucional y una Full conected de 512 con salida ReLu, ahora solo utiliza una Capa de Entrada de 6 neuronas y otra de salida de 4 neuronas

Paso 3:
Se simplifica lo maximo posible para luego rescatar los pesos (w) y los bias (b) y reutilizarlos en aplicaciones simples y rapidas como un excel, una aplicacion con javascript en un telefono o pc basico o incluso un arduino con webcam y salida bluetooth como teclado

Paso 4:
Se supone que la red convolucional realiza convinaciones de enmascaramientos multiples a trozos de la pantalla, segmentando estos en entradas secuenciales para la primera capa de la red neuronal Fullconect
Este proceso es similar a utiliza un emascaramiento dirigido al sector de la bola y otro al de la barra, y por esto se cambia
Los datos resultantes son los minimos de esos arreglos y corresponden a la posicion de ambos elementos
Luego deben pasar a la Fullconect, pero como ya no son tantas combinaciones como en la red convolucional, esta puede ser reducida a la cantidad de entradas
La cantidad de entradas corresponde a 6 parametros normalizados coordenadas X,Y de la bola en su estado anterior y el actual; y la coordenada X,Y de la barra
La salida esperada es la accion (0,1,2,3)
Tambien se podria desglosar en dos partes este bloque y obtener como salida la coordenada X de la barra proyectada la posicion de la bola
y luego la accion entre la posicion de la barra y la posicion proyectada, esto lo haria mas eficiente en aprendizaje y reducido y de seguro mas preciso

Los resultados obtenidos son aceptables, funciona bien, se dejan link de videos subidos a Youtube
modelo Experto alcanzado con el entrenamiento del alumno a partir del algoritmo maestro
los datos de entrenamiento inicial, ya que, se realiza DAGGER para realizar aumentacion de datos

Se detecto que a mas experto sea el comportamiento del maestro menos aprendera el alumno, ya que este requiere poder aprender paso a paso y no acciones limitadas y precisas de golpe 
ya que debe aprender a entender la accion ante la combinacion barra y bola y la combinacion es de aprox 2.4millones de escenas

La velocidad de las acciones puede influir por lo que en modelo GYM se dejo solo la mitad de las acciones, que originalmente realizaba una por cada cuadro, y como se realiza observacion cada cuatro cuadros y se toma una accion, esta se repetia generando inconvenientes de posicion

