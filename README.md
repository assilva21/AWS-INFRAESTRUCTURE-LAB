# ☁️ Cloud e IA by AS 🤖

## 💡 ¿Qué hace esta aplicación?
Es una aplicación web sencilla pero con un motor en la nube muy potente. Su funcionamiento es el siguiente:
1. El usuario sube la foto de un objeto cotidiano a través del navegador.
2. Mi servidor recibe la imagen y se comunica de forma segura con la Inteligencia Artificial de AWS.
3. La IA analiza la foto y devuelve el nombre del objeto identificado.
4. Ese registro se guarda automáticamente en una base de datos privada como historial.

## 🗺️ Las Fases del Proyecto
Construí esta arquitectura dividiéndola en 5 fases lógicas para no perderme en el intento:

* **Fase 1: El Servidor Base (Cómputo):** Desplegué una máquina virtual EC2 con Ubuntu. Instalé Python, configuré un entorno virtual y levanté la aplicación básica con Flask escuchando en el puerto 8080.
* **Fase 2: La Base de Datos (Almacenamiento Seguro):** Creé una instancia de RDS (PostgreSQL). Aprendí a colocarla en una Subred Privada para que nadie de internet pueda atacarla directamente, permitiendo que solo mi servidor EC2 se comunique con ella.
* **Fase 3: Inteligencia Artificial (Permisos IAM):** Conecté el código con Amazon Rekognition. Aquí apliqué seguridad basada en roles (IAM Roles) para darle permiso a mi servidor de usar la IA sin tener que escribir mis contraseñas directamente en el código de Python.
* **Fase 4: El Toque Profesional (Redes y SSL):** Dejé de usar la dirección IP con el puerto 8080 y configuré un dominio público gratuito (usando No-IP). Luego, configuré Nginx como Proxy Inverso.
* **Fase 5: Desmantelamiento y FinOps:** Elimine todas las instancias creadas.
