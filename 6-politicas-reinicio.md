# Políticas de reinicio

## Para esta parte de la práctica
1. Usa el archivo Dockerfile que se encuentra en cada carpeta con el nombre de la política de reinicio para crear una imagen. Analiza las instrucciones de cada Dockerfile 
2. Usa la imagen para ejecutar un contenedor agregando la política respectiva y observar lo que sucede verificando el cumplimiento de la política de reinicio
```
docker build -t test-reinicio:1.0 .
```

<img width="1895" height="349" alt="image" src="https://github.com/user-attachments/assets/e8ff755b-c0c9-44a3-8454-da7b42be4197" />

<img width="632" height="53" alt="image" src="https://github.com/user-attachments/assets/7b8dca2b-4ea4-4034-b421-287f7ca9a2e3" />

# Politica no
```
docker run -d --name c-no --restart no alpine sh -c "sleep 5 && exit 1"
```

<img width="1736" height="219" alt="image" src="https://github.com/user-attachments/assets/77b6be00-b584-4028-8987-3e2a0616f5cf" />

```
docker inspect c-no --format='{{.RestartCount}}'
```
<img width="540" height="49" alt="image" src="https://github.com/user-attachments/assets/e767832e-2f40-4be1-85db-73f896ff2faa" />

# Politica Always
```
docker run -d --name c-always --restart always alpine sh -c "sleep 5 && exit 1"
```
<img width="755" height="46" alt="image" src="https://github.com/user-attachments/assets/b23489e9-4940-4ae7-9d82-668f8ae826ab" />
```
docker ps
```
<img width="964" height="95" alt="image" src="https://github.com/user-attachments/assets/cb9c1197-561e-488b-a537-9e7ab9c16b83" />

# Politica on-failure
```
docker run -d --name c-failure --restart on-failure alpine sh -c "sleep 5 && exit 1"
```
<img width="777" height="60" alt="image" src="https://github.com/user-attachments/assets/ecfa3cf9-b7db-480b-b45d-b750a45ca13a" />
```
docker run -d --name c-success --restart on-failure alpine sh -c "sleep 5 && exit 0"
```
<img width="808" height="48" alt="image" src="https://github.com/user-attachments/assets/b51ee760-0f9f-43ab-9323-6ffa0b37a16d" />
# Politica unless-stopped
```
docker run -d --name c-unless --restart unless-stopped alpine sh -c "sleep 5 && exit 1"
```
<img width="817" height="47" alt="image" src="https://github.com/user-attachments/assets/040ead47-63ff-4ced-a6d9-7650f3bbfd53" />

```
docker stop c-unless
```
<img width="358" height="48" alt="image" src="https://github.com/user-attachments/assets/c6153c2f-9ff9-4b36-aaba-a3a982414bdf" />

### no
No reinicia el contenedor bajo ninguna razón. Esta es la política por default
```
docker run -d --name <nombre contenedor> <nombre imagen>
```

### always
Reinicia siempre el contenedor si se detiene. Si se detiene manualmente, sólo se reiniciará cuando se reinicie el demonio Docker o cuando se reinicie manualmente el propio contenedor
```
docker run -d --name <nombre contenedor> --restart always <nombre imagen>
```

### unless-stopped

Similar a always, excepto que cuando el contenedor se detiene (manualmente o de otra manera), no se reinicia incluso después de reiniciar el demonio Docker.
```
docker run -d --name <nombre contenedor> --restart unless-stopped <nombre imagen>
```

### on-failure
Se reinicia únicamente cuando hay una falla en la ejecución del código que se manifiesta con un código diferente de 0. No se reinicia si el contenedor se detiene manualmente.

```
docker run -d --name <nombre contenedor> --restart on-failure <nombre imagen>
```
