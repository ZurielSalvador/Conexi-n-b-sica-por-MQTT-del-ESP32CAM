# Conexion-basica-por-MQTT-del-ESP32CAM
En este repositorio se explica cómo hacer la conexión básica por MQTT del ESP32CAM
Autor: Victor Zuriel Dominguez Salvador


Autor del ejercicio: Hugo Escalpelo

Enlaces del Autor: https://github.com/codigo-iot/ESP32CAM_MQTT-Basic

Requisitos:


-ESP32-CAM
-FTDI TTL-USB




Enlaces de editores recomendados:


https://stackedit.io/app#


https://dillinger.io/


https://pandao.github.io/editor.md/en.html



---------------------------------------------------------------------------------------------------

Descripción del funcionamiento:


1. Clonar repositorio ESP32CAM_MQTT-Basic:


https://github.com/codigo-iot/ESP32CAM_MQTT-Basic
 

2. Modificar el archivo Readme.md


-Abrir VSCode
-Abrir el directorio del repositorio
-Modificar el archivo

3. Una vez que este modificado te dira que Crees un Fork del proyecto
	por lo cual desde GitHub Desktop le daras "For my own purposes"



4. Descargar biblioteca PubSubClient de Nick O'Leary 
   Posteriormente, Modificar código en la IDE de Arduino (Recuerda que este codigo viene de enlaces de autor el cual fue clonado).


	-SSID y contraseña de red
	-IP del broker local
		ifconfig
	-Tema donde se publica
		-Al final de void loop ()
	-Tema donde se suscribe
		-En la funcion callback
		-En la función reconnect
	


5. Configurar mosquitto



-Dirigirse a /usr/share/doc/mosquitto/examples/mosquitto.conf.exampl y obtener el archivo de configuración de ejemplo
-Colocar el archivo mosquitto.conf en el directorio /etc/mosquitto/conf.d/
-Descomentar las siguientes lineas y en la linea 25 escribas "true" de la siguiente manera:


	25	allow_anonymous true
	235	listener 1883 0.0.0.0

    *Nota: Es importante que la palabra "true" este colocada para que al reiniciar el servicio pueda funcionar de manera correcta.*


-Reiniciar el servicio:


	-Consultar el servicio
	systemctl status mosquitto
	-Detener servicio
	systemctl stop mosquitto
	-Arrancar servicio
	systemctl start mosquitto


---------------------------------------------------------------------------------------------------
Evidencias:

En la primera imagen podemos ver que el contador esta funcionando de manera correcta en las dos terminales.

[![contador-2.png](https://i.postimg.cc/0QDBYnJd/contador-2.png)](https://postimg.cc/PpfyhmyP)


Sin embargo para poder ver que en verdad esta conectado por Wifi, se desconectara de la computadora para conectarlo a un enchufe con ayuda de un cargador de celular.



Como se aprecia en la siguiente imagen:
[![Contador-3.jpg](https://i.postimg.cc/k4h81P3x/Contador-3.jpg)](https://postimg.cc/cgwrCjJH)


Por lo tanto en la terminal de ubuntu se reiniciara el contador.

[![contador-4.png](https://i.postimg.cc/vDw4kQP6/contador-4.png)](https://postimg.cc/xNgjbSV0)


Fin del ejercicio.







