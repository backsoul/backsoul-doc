# Primeros pasos
## Trabajando con docker

en este punto ya debes conocer docker, en esta documentación hablare solo de la
implementación con
odoo. Si no conoces docker aprende leyendo su [Documentación](https://docs.docker.com/get-started/).

lo necesario para iniciar odoo son dos cosas su imagen y una base datos. El
docker-compose se vería de esta manera.
```
version: '3.1'
services:
  web:
    image: odoo:14.0
    depends_on:
      - mydb
    ports:
      - "8069:8069"
    environment:
    - HOST=mydb
    - USER=odoo
    - PASSWORD=myodoo
  mydb:
    image: postgres:13
    environment:
      - POSTGRES_DB=postgres
      - POSTGRES_PASSWORD=myodoo
      - POSTGRES_USER=odoo
```

este docker-compose se saco de odoo en docker hub. [Leer mas](https://hub.docker.com/_/odoo)

Inicia el contenedor

```
    docker-compose up -d
```

Dirigete al [localhost:8069](http://localhost:8069), verás una pagina parecida
a esta.


##
