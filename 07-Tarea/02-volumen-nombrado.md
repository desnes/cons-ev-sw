# Volúmenes
## NOMBRADO

### Crear volumen

```
docker volume create vol-postgres
```
### ¿Cuál es el Mountpoint de vol-postgres?
El “Mountpoint” de un volumen Docker es el lugar en el sistema de archivos del host donde se almacenan los datos del volumen.

### ¿Cómo acceder a ese Mountpoint?
Puedes encontrar el Mountpoint de tu volumen vol-postgres utilizando el comando `docker volume inspect vol-postgres2`. Este comando te dará un resultado en formato JSON, y puedes buscar la clave “Mountpoint” para encontrar el Mountpoint de tu volumen. Para acceder a este Mountpoint, se debe navegar a la ruta del Mountpoint en el sistema de archivos del host
### Crear una red para postgres

```
docker network create postgres-network

```

### Servidor postgres usando el volumen nombrado

```
docker run -d --name server-postgres -e POSTGRES_DB=db_drupal -e POSTGRES_PASSWORD=12345 -e POSTGRES_USER=user_drupal -v vol-postgres:/var/lib/postgresql/data --network net-postgres postgres
```

### ¿Qué ha sucedido en vol-postgres?
Cuando se ejecuta el contenedor `server-postgres`, Docker monta el volumen `vol-postgres` en la ruta `var/lib/postgresql/data`.Esto significa que todos los datos que Postgres escribe en /var/lib/postgresql/data se almacenan en vol-postgres.