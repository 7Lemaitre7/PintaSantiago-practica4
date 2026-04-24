# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  
Si solucionó un problema presentado al realizar la práctica también se debe documentar.


## Antes de la práctica:

Tenía una idea muy superficial de cómo funcionaba la comunicación con los contenedores. Para mí, mapear un puerto era simplemente repetir números sin entender realmente la diferencia entre el puerto del host y el del contenedor. Además, veía a los contenedores como procesos "ciegos"; pensaba que si el contenedor estaba encendido, la aplicación adentro obligatoriamente estaba funcionando bien. No tenía ni idea de que se podían limitar los recursos físicos como la RAM o la CPU, y me preocupaba que un contenedor mal configurado pudiera "comerse" toda la memoria de mi computadora y colgar el sistema operativo.

## Después de la práctica:

Logré aterrizar conceptos críticos para mi formación profesional. Ahora entiendo la importancia de los Healthchecks para que Docker monitoree de forma inteligente si un servicio realmente responde, y no solo si el proceso está activo. Aprendí a configurar límites de memoria y CPU, lo cual es vital para desplegar aplicaciones de forma responsable en entornos de producción.

También comprendí la estructura de capas de un Dockerfile y cómo el mecanismo de caché optimiza el tiempo de construcción. Saber que el orden de las instrucciones puede ahorrar minutos de espera al momento de desarrollar. Finalmente, con las políticas de reinicio, ya sé cómo automatizar la disponibilidad de mis servicios sin tener que intervenir manualmente cada vez que algo falla.
