# Django DataBase
Databases with django
## Basic Installations and Upgrades (pip and venv)
- sudo apt-get update
- sudo apt-get install python3-pip
- python3 -m pip install --upgrade pip
- sudo apt-get install python3-venv
## Run Virtual Enviroment and Django
- python3 -m venv venv
- source venv/bin/activate
- pip install django |OR| pip install -r requirements.txt -> en caso de existir
## Start Projects and Applications
- django-admin startproject OnlineStore
- python3 manage.py startapp orders
## Conectrar PostgreSql (Dentro de la carpeta de tu proyecto)
- Cambiar la configuracion del archivo settings - DATABASES
- Cambiar la configuracion del archivo settings - APPLICATIONS
## Make Migrations (Una vez creados los modelos 'DB', en caso de agregar mas, volver a migrar)
- python3 manage.py check orders
- python3 manage.py makemigrations
- python3 manage.py sqlmigrate orders 0001
- python3 manage.py migrate
## Manipular Base de Datos
- python3 manage.py shell
### Consola Interactiva
- FROM orders.models import Clientes
### Ingresar Datos
- art1 = Clientes.objects.create(nombre="Guillermo", direccion="mundo",email="gcacho@gmail.com", tfno="1692238") -> Insertar en una linea
- art2 = Clientes(nombre="Guillermo", direccion="mundo",email="gcacho@gmail.com", tfno="1692238") -> Insertar en 2 lineas
- art2.save()
### Actualizar Datos
- art1.nombre='holo' -> cambia el titulo
- art1.save()
### Eliminar Datos
- borrar=Clientes.objects.get(id="1") -> Para guardar el criterio y borrar el articulo con id=1
- borrar.delete()
### Hacer una consulta / Query (SELECT)
- Lista=Clientes.objects.all() -> Guarda todos los registros de la tabla Articulos
- Lista -> Muestra los objetos
- Lista.query.__str__() -> Muestra el SELECT generado
## Revision de Aplicaciones
- python3 manage.py check orders