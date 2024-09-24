- Voy a dejar en esta nota todo lo relacionado con smalltalk
-
- Semana 1
	- Pharo object model
		- Solo objectos, mensajes y Bloques, es todo lo que hay en pharo
		- los mensajes son el "Que" ... la intención
		- los metodos son el "Como"
		- Los bloques, son como funciones anonimas, Lexical Clousures es el termino correcto
		- Ejemplo:
			- 4 timesRepeat: [ Transcript show: 'Hello world']
				- 4 es el objeto o reciber
				- timesRepeat: es el mensaje
					- mensaje: , los dos puntos indican que el mensaje necesita un argumento
				- [...] lo que esta entre paréntesis cuadrados es un bloque
		- las variables de instancias son protegidas, privadas para los objetos y accesible desde las subclases
		- todos los metodos son privados
		- herencia unica entre clases
	- Sintaxis
		- ![image.png](../assets/image_1727127705969_0.png)
		- ![image.png](../assets/image_1727127730436_0.png)
		- Mensajes
			- ![image.png](../assets/image_1727127780527_0.png)
			- los condicionales y loops son mensajes tambien
				- ![image.png](../assets/image_1727128016535_0.png)
				- ![image.png](../assets/image_1727128055688_0.png)
				-
				- ![image.png](../assets/image_1727128461156_0.png)
				-
		- definir una clase
			- ![image.png](../assets/image_1727128530576_0.png)
			- las clases pertenecen a pacquetes
			- todos son subclases de Object
			- declaras las variables de instancia / clase como un string separados por espacios
			- category es el nombre del package
			- puedes crear metodos a nivel de instancia a o de clase (static method)
		- definir un metodo
			- ![image.png](../assets/image_1727128946913_0.png)
			-
			-
		- Bloques
			- se pueden asignar a variables
			- se evaluan en tiempo de ejecucion o con el mensaje valure
				- [...] value
				- pueden tener argumentos
					- [:x| x+2]
						- si quiero evaluar esto seria :
						- [:x|x+2] value:5
							- >7
			- buenas practicas al usar bloques:
				- ![image.png](../assets/image_1727129508160_0.png)
		- Loops
			- timesRepeat:
				- 4 timesRepeat: [self doSomthing]
			- to:do:
				- 1 to: 100 do: [:i|...]
			- Iteradores
				- ![image.png](../assets/image_1727130032835_0.png)
				- [...] whileTrue: [...]
					- ![image.png](../assets/image_1727130289618_0.png)
				- booleans y condicionales
				  id:: 66f1eab2-7014-46c3-9751-2fb961690915
					- eager y lazy
						- ![image.png](../assets/image_1727205745520_0.png)
					- condicionales son mensajes
						- ```smalltalk 
						  Weather isRaining
						  ifTrue: [self takeMyUmbrella]
						  ifFalse: [self takeMySunglasses]
						  ```
						- ifEmpty:[...] , ifNotEmpty:[...] -> se explican solas y se usan en colecciones
				- yourself
					- se usa en conjunto con cascade ';' para retornar el objeto/reciver original y no el resultado del ultimo menasaje
					- sin yourself:
						- ```smalltalk 
						  Set new add: 2
						  > 2
						  "retorna un 2 y no un set con un dos dentro"
						  ```
					- con yourself
						- ```pharo
						  Set new
						  add: 2;
						  yourself
						  >aSet 
						  "esto si retorna un set con el numero dos dentro"
						  ```
				-
				-
				-
				-