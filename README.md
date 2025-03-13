## En Ansible, los roles te permiten estructurar mejor tu código y reutilizar tareas en diferentes proyectos. En lugar de tener un solo playbook.yml, puedes dividir la configuración en varios archivos organizados por propósito.

🔹 ¿Qué es un rol en Ansible?

## Un rol en Ansible es una forma de organizar tareas, archivos y configuraciones dentro de un directorio estructurado. Te ayuda a mantener tus playbooks limpios y reutilizables.
📂 Estructura de un Rol

Cuando creas un rol, Ansible genera una estructura como esta:
nginx_role/
│── defaults/         # Variables por defecto
│   ├── main.yml
│── files/            # Archivos estáticos (como index.html)
│── handlers/         # Manejadores (ej: reiniciar Nginx)
│   ├── main.yml
│── tasks/            # Tareas (instalación y configuración)
│   ├── main.yml
│── templates/        # Plantillas Jinja2 (configuración Nginx)
│── vars/             # Variables específicas
│   ├── main.yml
│── meta/             # Metadatos del rol
│── README.md         # Documentación


# 🔹 Creando un Rol en Ansible
Podemos hacer que la instalación y configuración de Nginx sea un rol independiente. Aquí están los pasos:
1️⃣ Crear el Rol de Nginx

Ejecuta este comando en la misma carpeta donde tienes tu playbook:
### ansible-galaxy init nginx_role

Esto generará la estructura de archivos automáticamente.

## 2️⃣ Definir las Tareas en tasks/main.yml

Edita el archivo nginx_role/tasks/main.yml para definir qué hará el rol:

## 3️⃣ Definir los Handlers en handlers/main.yml

Los handlers son tareas que solo se ejecutan cuando algo cambia. En este caso, reiniciaremos Nginx si su configuración cambia:

## 4️⃣ Crear una Plantilla en templates/nginx.conf.j2

## 5️⃣ Definir Variables en vars/main.yml

## 6️⃣ Usar el Rol en el Playbook

# 🔹 Ventajas de Usar Roles

✅ Código más limpio y organizado
✅ Fácil de reutilizar en otros proyectos
✅ Modularidad: puedes agregar más roles para DB, seguridad, etc.
✅ Facilidad de mantenimiento