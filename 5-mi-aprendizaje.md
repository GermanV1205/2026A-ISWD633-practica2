# COMPLETAR  
Problema: Tuve errores de autenticación y de conexión al intentar que las aplicaciones hablaran con las bases de datos.
Solución: Descubrí que el orden de los comandos es estricto (las variables -e siempre van antes del nombre de la imagen) y que para conectar contenedores en la misma red se debe usar el nombre exacto del contenedor (ej. srv-postgres o servidor-mysql) y no localhost.

Consultar: Cómo se gestionan datos confidenciales con los secretos de Docker (Docker Secrets).

Escribir contraseñas directamente en la consola con -e es peligroso porque cualquiera puede verlas inspeccionando el contenedor. Docker Secrets es la herramienta profesional para solucionar esto: encripta las contraseñas o datos sensibles y se los entrega al contenedor guardándolos temporalmente en su memoria RAM, por lo que nunca quedan escritos en el disco duro y son imposibles de robar.
