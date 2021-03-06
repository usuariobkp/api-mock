# Api-mock

Api-mock

## Índice 
* [Desarrollo](#desarrollo)
* [Contacto](#contacto)

## Desarrollo

### Requerimientos

Este proyecto require python 3.6.
Python 3 puede ser instalado con [pyenv](https://github.com/pyenv/pyenv).

1. Usar [pyenv-installer](https://github.com/pyenv/pyenv-installer) para instalar pyenv
1. Ver las versiones de python disponibles: `pyenv install --list`
1. Instalar python 3. Ejemplo: `pyenv install 3.6.3` (3.6.3 o mayor)


Tambien [nodejs](https://nodejs.org/en/) es necesario para usar `eslint` y `jscpd`.

1. Instalar `nodejs`, esto se puede llevar a cabo mediante [nvm](https://github.com/creationix/nvm).
1. Instalar la version `7` de `nodejs`
1. Usar `npm` para instalar las dependencias: `npm install`


Opcionalmente se puede usar Docker y Docker Compose para desarrollo.

### Configuracion

Este proyecto adopta [The 12 factor methodology](https://12factor.net/).
Esto significa que todas las configuraciones deberian hacerse por variables de entorno. [(Factor III)](https://12factor.net/config).

## Configuracion Local

1. Crear un "virtualenv" con un nombre descriptivo: `pyenv virtualenv 3.6.3 my_virtualenv`
1. Crear un archivo `.python-version`: `echo "my_virtualenv" > .python-version`
1. Instalar los requerimientos: `pip install -r requirements/local.txt`

### Development with Docker

1. Build: `docker-compose build`
1. Iniciar los servicios: `docker-compose up -d`
1. Migrar la base de datos: `docker-compose run django python3 manage.py migrate`
1. Crear un super usuario: `docker-compose run django python3 manage.py createsuperuser`

## Git hooks

* Instalar [git-hooks](https://github.com/git-hooks/git-hooks/).
* Instalar los hooks de git: `git hooks install`

## Tips:

Server para desarrollo: 

* `./manage.py runserver`

Consola de django:

* `./manage.py shell`

Correr migraciones:

* Con Docker: `docker-compose run django python3 manage.py migrate`
* Local: `python manage.py migrate`

Tests:

* `scripts/tests.sh`

### Correr Lint/Style/CPD


* [Flake8](http://flake8.pycqa.org/en/latest/index.html): `scripts/flake8.sh`
* [Pylint](https://pylint.readthedocs.io/en/latest/): `scripts/pylint.sh`
* [Jscpd](https://github.com/kucherenko/jscpd): `scripts/jscpd.sh`
* [Eslint](https://eslint.org/): `scripts/eslint.sh`

### Testing con Vagrant

Luego de instalar [Vagrant](https://www.vagrantup.com/), cambiar al directorio `deploy/` y correr el comando `vagrant up --provision`.

## Contacto
Te invitamos a [crearnos un issue](https://github.com/datosgobar/api-mock/issues/new?title=Encontre-un-bug-en-api-mock)
en caso de que encuentres algún bug o tengas comentarios de alguna parte de `api-mock`. Para todo lo demás, podés mandarnos tu sugerencia o consulta a [datos@modernizacion.gob.ar](mailto:datos@modernizacion.gob.ar).
