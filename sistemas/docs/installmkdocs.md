# Preparación del equipo para la documentación.

En [su página oficial](https://www.mkdocs.org/#installation) podéis encontrar más información acerca de la instalación en varias plataformas, en este caso lo explicaremos para [Ubuntu 18.04LTS](https://ubuntu.com).

## Instalación con [APT](https://es.wikipedia.org/wiki/Advanced_Packaging_Tool).
`sudo apt install -y mkdocs` 

## Instalación con [PIP](https://pypi.org/project/pip/).
`pip install mkdocs` 

## Comprobamos la versión instalada:
`mkdocs --version`

>mkdocs, version 1.0.4

## En este caso usamos la versión ReadTheDocs [Dropdown](https://github.com/cjsheets/mkdocs-rtd-dropdown), la instalamos:
`pip install mkdocs-rtd-dropdown`

## Clonamos el repositorio:
`git clone https://github.com/Colm3na/sistemas.git`

## Nos dirigimos a la carpeta del proyecto, e iniciamos el servidor de desarrollo:
`cd $HOME/sistemas/` 

`mkdocs serve`

> Si abrimos el navegador y nos vamos a la página [http://127.0.0.1:8000/](http://127.0.0.1:8000/) podemos ver la documentación.