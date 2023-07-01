# CheckList de creación base de una aplicación WEB

## pasos para la implementacion de la estructura base de una aplicación

- [ ] Crear el entorno virtual  
```bash
$>  python -m venv .
```
- [ ] Activar en entorno 
```bash
$>  source Script/activate
```
- [ ] Instalar los paquetes necesarios 

```bash
$  pip install Django=4.2
$  python -m pip install --upgrade pip
$  pip install django_rest_framework
$  pip install requests
$  pip install mysqlclient          # cliente Mysql 
$  pip install psycopg2             # cliente Postgresql
$  pip install pyodbc               # cliente SQLServer necesita ODBC
$  pip install redis                # cliente Redis
$  pip install pymongo              # cliente mongoDB
$  pip install graphene-django      # libreria para implementar GraphQL
$  pip install django-environ       # Permite manejar la configuración
```

- [ ] Generar el archivo requirements.txt
```bash
$> pip freeze > requirements.txt
```
- [ ] Crear un proyecto
```bash 
$ django-admin startproject  <name_project>
```
- [ ] Crear una aplicación
```bash
$ python manage.py startapp <name_app>
```
- [ ] Crear las carpetas stactic y templete de la aplicación

```bash
$ cd <name_project>/<name_app>
$ mkdir ./templates ./static
$ cd ./static
$ mkdir ./css ./js ./images

```
- [ ] Agregar templates en el archivo settings.py
```py
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [
            os.path.join(BASE_DIR, 'app1', 'templates'),
            os.path.join(BASE_DIR, 'app2', 'templates'),
        ],
        ...
    },
]
```
- [ ] Agregar la carpeta static de la aplicación en settings.py
```py
STATICFILES_DIRS = [
    os.path.join(BASE_DIR, 'app1', 'static'),
    os.path.join(BASE_DIR, 'app2', 'static'),
]
```