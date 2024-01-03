# Volúmenes
## ANÓNIMO

Un volumen anónimo en Docker es un tipo de volumen que se crea y se adjunta a un contenedor sin un nombre específico

```
docker run -d --name server-nginx -v /usr/share/nginx/html --publish published=9800,target=80 nginx:alpine
```

### Para eliminar el contenedor y el volumen

```
docker rm -fv server-nginx
```

_esta instrucción elimina el volumen si éste es de tipo anónimo_