# asociaciondetransportes de Guatemala developed by Javier Alfonso Roca Arellano

# Requisitos del Servidor Tener Instalado Node.js mayor o igual a la version v8.10.0
# tener Instalado MongoDB la Base de Datos
 
# Paso 1: Generar un Restore de la Base de Datos con el siguiente comando
# sudo mongorestore --db test --drop mongodb/backup/11-03-18/test/
# esta accion restora la base de datos el usuario del Administrador es:
# usuario: jrocaarellano password: 12345
# usuario del Piloto es:
# usuario: jperezperez password: 12345
# usuario del ayudante:
# usuario: lmendezgonzales password: 12345
# desde el perfil del Administrador se pueden crear Usuarios

# LA APLICACION NO CONECTARA A LA BASE DE DATOS SINO SE CAMBIA LA DIRECCION DE LOS WEBSOCKETS
# Paso 2: Cambiar la direccion de los WebSockets 
# abrir el archivo en la carpeta asociaciondetransportes/ 
# app/modern/app.js
# el archivo app.js contiene todo el codigo del app esta para producccion comprimido no esta por modulos
# o arquitectura MVC model view controller esto me tomara 5 dias desde que reciba una respuesta
# en el Archivo app/modern/app.js se tiene que encontrar y remplazar la IP esta la IP 192.168.1.54:8080 hay
# que remplazarla por la IP y puerto del Servidor del Campus TEC, el puerto 8080 es el default en Node.js
# la aplicacion necesita HTTPS para poder solicitar la Ubicacion GPS de la Persona se tiene que asignar
# un Dominio para el App ejemplo nombredelapp.com tiene que tener certificados SSL para que resuelva
# https://nombredelapp.com
# olvide mencionar un Punto en en archivo server.js el Servidor Node.js tambien debe cambiarse la IP y poner la IP del servidor actualmente esta 192.168.1.54 hay que buscar y remplazar aparece 2 veces en ese archivo.
# LISTO, CON ESTOS PASOS LA APLICACION PUEDE CORRER   
