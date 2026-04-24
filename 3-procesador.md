# Limitar uso de procesador
Limitar la cantidad de núcleos de CPU:
```
--cpus=<número de núcleos>
```

Asignar núcleos de CPU específicos:
```
--cpuset-cpus=<lista de núcleos>
```

**¿Como saber el numero de procesadores virtuales que tiene una máquina?**
```
wmic cpu get NumberOfLogicalProcessors
```
<img width="737" height="83" alt="image" src="https://github.com/user-attachments/assets/02d82b81-e656-4e97-b1b5-b4ae277bf483" />

## COMPLETAR

## Ejemplos
_Puedes copiar y ejecutar directamente cada uno de los comandos_

Limitar el uso de CPU a 1.5 núcleos
```
docker run -d --name server-nginx --cpus="1.5" nginx:alpine
```
<img width="1104" height="97" alt="image" src="https://github.com/user-attachments/assets/ccbf2591-fd1e-4247-8d34-6dfd2d480ba5" />

Restringir el contenedor para que use los núcleos de CPU 0 a 2:
```
docker run -d --name server-nginx --cpuset-cpus="0-2" nginx:alpine
```
<img width="1192" height="60" alt="image" src="https://github.com/user-attachments/assets/93fd9722-d372-4358-9f65-d6b690c2b703" />

Restringir el contenedor para que use los núcleos de CPU 1 y 3:
```
docker run -d --name server-nginx --cpuset-cpus="1,3" nginx:alpine
```
<img width="1187" height="61" alt="image" src="https://github.com/user-attachments/assets/bc445b00-b84e-4075-8f6f-9d34f75e9fb4" />
