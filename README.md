# sesion_04_lab01
Laboratorio Playbooks

# Enunciado del Ejercicio

- Crearemos u repositorio en GitHub con el nombre sesion_04_lab01
- Lo clonaremos en nuestor equipos
- Crearemos en ansible.cfg y el inventario
- Crearemos un playbook con las siguientes datos:
	- El titulo del Playbook sera "Instalacion y configuracion de serivdor Web"
	- Atacaremos al nodo 1
	- Mostraremos un mensaje por pantalla con el siguiente bloque de texto
		--> En este ejericicio practicaremos el desarrollo de un playbook desde 0
			para ello, realizaremos varias tareas para levantar un servidor apache
	- Intalacion de paquete httpd
	- Habilitar en el firewalld el servicio http y https
	- Recargar el firewalld
	- Arrancar el servicio de httpd en el server
	- Habilitar el servicio httpd para que lo haga en el arranque
	- Desactivar el selinux del servidor
- Configuraremos un host virtual con los siguientes pasos:
		- Crearemos el directorio --> /var/www/example.com/htm
		- Crearemos el directorio --> /var/www/example.com/log
		- El propietario y grupo de los directorios anteriores sera root
		- Le damos permisos recursivos 755 al directorio /var/www/
		- Creamos el fichero /var/www/example.com/html/index.html
		- Insertamos el siguiente bloque de texto en archivo anterior:
		
			<html>
				<head>
					<title>Welcome to Example.com!</title>
				</head>
				<body>
					<h1>Success! The example.com virtual host is working!</h1>
				</body>
			</html>
    
- Creamos los directorios /etc/httpd/sites-available y /etc/httpd/sites-enabled
		- Añadimos la siguiente linea "IncludeOptional sites-enabled/*.conf" al final del fichero 			/etc/httpd/conf/httpd.conf
		
		- Creamos el fichero /etc/httpd/sites-available/example.com.conf con usuario y permiso root
		- Insertamos el siguiente bloque de testo en el fichero anterior:
		
			<VirtualHost *:80>
				ServerName www.example.com
				ServerAlias example.com
				DocumentRoot /var/www/example.com/html
				ErrorLog /var/www/example.com/log/error.log
				CustomLog /var/www/example.com/log/requests.log combined
			</VirtualHost>
		
		- Creamos enlace simbolico con origen /etc/httpd/sites-available/example.com.conf y destino 		/etc/httpd/sites-enabled/example.com.conf
		
	- Reiniciamos el servidor
	- Comprobamos que el apache levanta con el server y que carga la web desde un navegador
