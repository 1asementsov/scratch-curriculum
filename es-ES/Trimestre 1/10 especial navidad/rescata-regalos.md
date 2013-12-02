Nivel 2

#Rescata regalos

__Introducci�n:__
__En este proyecto vamos a crear un juego con fondo en movimiento, un marcador y un mensaje navide�o al final.__
Un accidente en la f�brica de juguetes ha hecho volar todos los juguetes por los aires. �Ayuda al reno Rudolph a salvar la navidad rescatando los regalos!

##PASO 1: Haz volar a Rudolph

1. Comienza un nuevo proyecto de Scratch. Borra el objeto gato pinch�ndolo con el bot�n derecho y pinchando 'borrar'.
2. Reemplaza el fondo con SkyBackground.png.
3. Pincha en __Escoger un nuevo objeto desde archivo__ y a�ade el objeto Rudolph al proyecto usando el archivo __Rudolph.png__.
4. C�mbiale el nombre al objeto a __Rudolph__.
5. Haz que Rudolph siga al puntero del rat�n con este programa:


```scratch
al presionar BANDERA
enviar al frente
por siempre
	ir a apuntador del rat�n
(fin por siempre)
```

###Prueba tu proyecto

__Pincha en la bandera verde y mueve el rat�n__, �sigue Rudolph al rat�n?

6. Vamos a hacer el juego m�s interesante a�adiendo montes nevados que se muevan para que parezca que Rudolph est� volando. Pincha en __Escoger un nuevo objeto desde archivo__ y a�ade el objeto Nieve al proyecto usando el archivo __SnowHills.png__.
7. C�mbiale el nombre al objeto a __Nieve1__.
8. Crea una nueva variable pinchando en 'Variables' y luego en 'Nueva variable'. Dale el nombre ScrollX, m�rcala 'para todos los objetos' y despeja su casilla para que no aparezca en el escenario. Esta variable controlar� c�mo se mueven los montes.
9. A�ade este programa para hacer que se muevan los montes:

```scratch
al presionar BANDERA
fijar y a 0
por siempre
	fijar x a ScrollX
	cambiar ScrollX por -1
	si ScrollX < -480
		fijar ScrollX a 0
	(fin si)
(fin por siempre)
```

###Prueba tu proyecto

__Pincha en la bandera verde__, �se mueven los montes? �Qu� ocurre cuando los montes llegan al borde del escenario?

10 Vamos a arreglar el problema de los montes que saltan cuando llegan al borde del escenario, a�adiendo m�s montes pinchando en __Escoger un nuevo objeto desde archivo__ y a�adiendo un segundo objeto usando el archivo __SnowHills.png__.
11 C�mbiale el nombre al objeto a __Nieve2__.
12 A�ade este programa a __Nieve2__ para que el segundo grupo de montes vaya pegado al primero:

```scratch
al presionar BANDERA
fijar y a 0
por siempre
	fijar x a ScrollX + 479
(fin por siempre)
```

###Prueba tu proyecto

__Pincha en la bandera verde__, �se mueven los montes? �Se ha arreglado el problema de los montes que saltaban?

__Guarda tu proyecto__

##PASO 2: Regalos que caen

1. Vamos a a�adir los regalos que van a caer para que Rudolph los recoja. Pincha en __Escoger un nuevo objeto desde archivo__ y a�ade el objeto __Regalo__ usando el archivo __Present.png__.
2. C�mbiale el nombre al objeto a __Regalo__.
3. Crea una nueva variable pinchando en 'Variables' y luego en 'Nueva variable'. Dale el nombre __Parar__, m�rcala 'para este objeto' y despeja su casilla para que no aparezca en el escenario. Usaremos esta variable para controlar cu�ndo desaparece el regalo.
4. Crea otra nueva variable. Dale el nombre __Velocidad__, m�rcala 'para este objeto' y despeja su casilla para que no aparezca en el escenario. �sta controlar� la velocidad a la que cae el regalo.
5. A�ade este programa al objeto __Regalo__ para hacerlo caer del cielo. Ver�s que usaremos n�meros al azar para que el regalo aparezca cada vez en un punto distinto.
6. Usando el comando __�tocando Rudolph?__ haremos que el regalo desparezca cuando Rudolph lo atrapa, y as� mantenemos el marcador m�s tarde.


```scratch
al presionar BANDERA
por siempre
	fijar Parar a 0
	ir a x: n�mero al azar entre -230 y 230 y: n�mero al azar entre 50 y 170
	fijar Velocidad a -1
	repetir hasta que Parar = 1
		cambiar y por Velocidad
		si posici�n en y de Regalo < -160
			fijar Parar a 1
		(fin si)
		si �tocando Rudolph?
			fijar Parar a 1
		(fin si)
	(fin repetir)
(fin por siempre)
```

###Prueba tu proyecto

__Pincha en la bandera verde,__ �caen los regalos del cielo? �Desaparecen cuando Rudolph los toca o cuando llegan al suelo?

7 Hag�moslo m�s interesante cambiando el color de cada regalo. Lo hacemos usando el comando __cambiar efecto color__.
8 Cambia la velocidad de cada regalo fijando la Velocidad a un n�mero al azar en vez de siempre a -1. Prueba distintas velocidades.


```scratch
al presionar BANDERA
por siempre
	fijar Parar a 0
	ir a x: n�mero al azar entre -230 y 230 y: n�mero al azar entre 50 y 170
	cambiar efecto color por n�mero al azar entre 1 y 100
	fijar Velocidad a n�mero al azar entre -10 y -1
	repetir hasta que Parar = 1
		cambiar y por Velocidad
		si posici�n en y de Regalo < -160
			fijar Parar a 1
		(fin si)
		si �tocando Rudolph?
			fijar Parar a 1
		(fin si)
	(fin repetir)
(fin por siempre)
```

###Prueba tu proyecto
__Pincha en la bandera verde,__ �tiene cada regalo un color y una velocidad distintos?

##PASO 3: Marcador y efectos de sonido

1. __Cambiemos el programa para mantener la puntuaci�n durante el juego.__ Entonces podremos utilizar el marcador para decidir cu�ndo termina el juego y aparece el mensaje navide�o.
2. Crea una nueva variable pinchando en 'Variables'. Ll�mala __Puntos__ y m�rcala 'para todos los objetos'. Deja la casilla marcada para que aparezca en pantalla.
3. Cambia el programa del objeto __Regalo__ como aparece a continuaci�n. F�jate en que hemos a�adido efectos de sonido con el comando `tocar tambor` y tambi�n hacemos `cambiar Puntos por 1` cuando Rudolph toca el regalo.


```scratch
al presionar BANDERA
por siempre
	fijar Parar a 0
	ir a x: n�mero al azar entre -230 y 230 y: n�mero al azar entre 50 y 170
	cambiar efecto color por n�mero al azar entre 1 y 100
	fijar Velocidad a n�mero al azar entre -10 y -1
	repetir hasta que Parar = 1
		cambiar y por Velocidad
		si posici�n en y de Regalo < -160
			tocar tambor 57 durante 0.2 pulsos
			fijar Parar a 1
		(fin si)
		si �tocando Rudolph?
			tocar tambor 39 durante 0.2 pulsos
			cambiar Puntos por 1
			fijar Parar a 1
		(fin si)
	(fin repetir)
(fin por siempre)
```

4 A��dele m�sica al juego importando el sonido __Jingle_Bells.mp3__ para el __Escenario__.

```scratch
al presionar BANDERA
fijar ScrollX a 0
fijar Puntos a 0
tocar sonido Jingle_Bells
```

5 A�ade este programa al __Escenario__ para reiniciar el marcador de 0 cuando comienza el juego. Tambi�n tocar� la m�sica durante todo el juego.

Nota: si la m�sica suena entrecortada, prueba guardar el proyecto, cerrar Scratch y volver a abrir el proyecto.

###Prueba tu proyecto

__Pincha en la bandera verde,__ �cambia el marcador cuando Rudolph toca cada regalo?

__Guarda tu proyecto__

##PASO 4: Fin del juego

1. __Vamos a cambiar el programa para alertar cuando se llega a una cierta puntuaci�n.__ Luego usaremos esta alerta para mostrar el mensaje al final del juego.
2. Cambia el programa del __Escenario__ para que cuando el marcador llega a 10 enviamos a todos un mensaje __Fin__.

```scratch
al presionar BANDERA
fijar ScrollX a 0
fijar Puntos a 0
tocar sonido Jingle_Bells
por siempre 
	si Puntos = 10
		enviar a todos GameOver y esperar
	(fin si)
(fin por siempre)
```

3. Ahora a�adimos el mensaje del fin del juego. Pincha en __Escoger un nuevo objeto desde archivo__ y a�ade el objeto __Fin__ al proyecto usando el archivo __GameOver.png__.
4. C�mbiale el nombre al objeto a __Fin__.
5. __A��dele este programa__ que `esconde` la imagen cuando comienza el juego y la `muestra` cuando se recibe el mensaje __Fin__.


```scratch
al presionar BANDERA
esconder

al recibir Fin
enviar al frente
mostrar
detener todo
```

###Prueba tu proyecto

__Pincha en la bandera verde,__ �aparece el mensaje navide�o al final del juego?

__Guarda tu proyecto__

##Desaf�o: Hazlo m�s dif�cil

* �Puedes hacer que los regalos se tambaleen al caer por la pantalla?
* �Puedes hacer que haya m�s de un regalo a la vez en pantalla?
* Cambia el mensaje del fin del juego para que aparezca despu�s de rescatar 20 regalos.
* �Puedes cambiar el marcador para que pierda 1 punto por cada regalo que caiga al suelo?

__Bien hecho, hemos terminado. �Ahora a disfrutar de tu juego!__
�Te deseamos una feliz navidad!
