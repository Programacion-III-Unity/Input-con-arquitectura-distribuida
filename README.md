# Input con arquitectura distribuida
En este ejemplo tomamos el repo de [Input System basico](https://github.com/Programacion-III-Unity/Input-System-Basico), y desacoplamos los componentes principales en 4 scripts.
En ese proyecto, dentro del script "Jugador" podemos identificar 3 componentes principales:
- Las caracteristicas del Jugador (posicion, prefab del disparo, etc)
- El input del jugador
- El movimiento del jugador

Debemos seguir el principio de la responsabilidad simple en los componentes: cada componente tiene la responsabilidad sobre un solo aspecto.

				               --------------------
				              |      Jugador       |
				              ----------------------
				                        |
				                        |
						   ----------------------------------
					       |       							|
					       |								|
						--------						---------------
					   |  Input | 					   |   Movimiento  |
						--------						---------------
							

En este modelo, el script de Jugador contiene todas las caracteristicas del jugador, y variables relacionadas a su status, y el movimiento e input se separan en dos scripts.
A su vez, estos dos scripts se estan comunicando constantemente con el script de jugador para coordinar sus tareas, nunca se comunican directamente.

Esto permite generar un codigo mucho mas claro, con un flujo formalizado y definido, ademas de manejar codigo mas limpio, eficiente, y mantenible.
