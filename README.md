#odoo-agenda-sw1
Este repositorio contiene los archivos bases para instalar Odoo usando Docker

Básicos de desarrollo en Odoo con Utilizando docker

# Puesta en marcha en localhost
	1. Descargar el proyecto base de la agenda académica de github
		https://github.com/RafaelSvgh/agendasw1.git
	2. Ejecutar el siguiente comando 
		docker compose -f docker-compose-dev.yml up
		Nota: No olvidar tener abierto docker
	3. Entrar a http://localhost:8069/ -> Listo

# Integrar Odoo a un IDE
	1. Descargar el proyecto base de odoo desde github
		https://github.com/BenjaminRo-Dev/odoo-agenda-sw1.git
	2. Hacer un cd a la carpeta: cd /mnt/extra-addons
	3. Ejecutar el comando odoo scaffold manage
		a. Listar
	4. Activar el módulo creado
		a. Nota: Quitar el filtro "app" del buscador
	5. Realizar cambios (Hacer un CRUD)
		a. Crear un modelo
			i. models/nombre_model.py
			ii. Referenciarlo en el init.py
			iii. Definirlo en security/ir.model.access.csv
				1) Revisar que ese archivo esté en el manifest
			iv. Nota: Cada vez que se modifica un modelo se debe reiniciar el contenedor
		b. Crear las vistas
			i. views/nombre_view.xml
			ii. Nota, el achivo views/views.xml debe ir de ultimo
			iii. Crear el action en views/views.xml
			iv. Nota: Cada vez que se modifica una vista se debe actualizar la app
	6. Probar, listo =)
