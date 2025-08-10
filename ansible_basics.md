# ¿Qué es Ansible? Mencione dos actividades que se puedan hacer con Ansible
Ansible es una herramienta de automatización open source que permite configurar sistemas, instalar software y ejecutar tareas en múltiples servidores al mismo tiempo, sin necesidad de instalar programas adicionales en cada uno. Funciona de forma simple y eficiente, utilizando archivos con instrucciones claras, llamados playbooks <br>
### Mencione dos actividades que se pueden hacer con Ansible:
1. Configurar servidores automáticamente:<br>
Ansible permite definir configuraciones en servidores y aplicarlas de forma automática y consistente. Por ejemplo, se puede instalar software, crear usuarios, copiar archivos de configuración, establecer permisos y ajustar servicios. Esto es útil cuando se trabaja con varios servidores, ya que evita tener que repetir las mismas acciones manualmente en cada uno.
2. Desplegar aplicaciones en varios servidores con un solo comando: <br>
Con Ansible se puede automatizar todo el proceso de despliegue de una aplicación: clonar el repositorio de código, instalar dependencias, configurar el entorno, reiniciar servicios y verificar que todo esté funcionando. Todo esto se puede ejecutar con un único comando.

# ¿Que es un playbook de Ansible?
Un playbook de Ansible es un archivo escrito en formato YAML que contiene una serie de tareas que Ansible debe ejecutar en uno o varios servidores. Estas tareas pueden incluir cosas como instalar programas, copiar archivos, reiniciar servicios o desplegar aplicaciones. <br>
Los playbooks permiten automatizar procesos de forma ordenada, reutilizable y fácil de entender. 

# ¿Que información contiene un inventario de Ansible?
Un inventario de Ansible contiene la lista de los servidores o equipos sobre los cuales se ejecutarán las tareas definidas en los playbooks. Estos servidores se organizan en grupos y se identifican por su nombre o dirección IP. <br>
Además de los nombres de host, el inventario puede incluir grupos de hosts para organizar los servidores según su función (por ejemplo, web, db, backend, etc.).<br>
Los inventarios pueden ser archivos en formato INI o YAML

# Explique que es un módulo de Ansible y dé un ejemplo.
Los módulos de Ansible son librerías que nos permiten hacer acciones sobre los servidores.
Ansible incluye cientos de módulos listos para usar incluidos en el core (builtin), pero también se pueden crear módulos personalizados o usar módulos creados por otros, instalandolos previamente
<br><br>
Por ejemplo, el módulo `file` permite gestionar atributos de archivos y directorios (crearlos, cambiar permisos, propietarios, etc.).

```
- name: Crear el directorio /var/ejemplo
  ansible.builtin.file:
    path: /var/ejemplo
    state: directory
    owner: Juan
    group: Testing
```
Esta task verifica que en el servidor remoto exista el directorio /var/ejemplo, y si no existe, lo crea. Luego, se asegura de que el directorio sea propiedad del usuario Juan y del grupo Testing.

# ¿Que ventajas tiene Ansible sobre otros métodos de automatización?
Ansible ofrece varias ventajas frente a otros métodos de automatización más tradicionales o herramientas similares, como por ejemplo:

* Simplicidad y facilidad de uso: Usa archivos de texto en formato YAML, que son fáciles de leer y escribir, hasta para personas con poca experiencia en programación.
* No requiere instalar software en los servidores que se administran. Se conecta por SSH (en Linux) o WinRM (en Windows), lo que simplifica el mantenimiento.
* Las tareas se diseñan para ser repetibles, si se ejecutan varias veces, el resultado será el mismo, evitando cambios innecesarios.
* Multiplataforma: Funciona en entornos Linux, Windows, contenedores, servicios en la nube, etc., permitiendo administrar infraestructuras diversas.
* Escalabilidad y reutilización: Permite organizar tareas en roles, agrupar servidores por función, y reutilizar configuraciones fácilmente en diferentes entornos.
