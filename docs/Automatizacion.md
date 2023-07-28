# <span style="color: #00A1DD">Descripción del servicio de automatización</span>
---
En esta sección tendrá una visión puntual de los scripts de automatización y las tareas programadas utilizadas en esta arquitectura. Estos scripts son fundamentales para la ejecución automática de procesos recurrentes, como la actualización de datos. La documentación ofrece ejemplos prácticos de scripts y detalla las mejores prácticas para su implementación, asegurando una administración eficiente y confiable del sistema de BI y análisis de datos.

Asimismo, se presentan casos de uso específicos en los que se muestran ejemplos prácticos de cómo utilizar los scripts y las tareas programadas para optimizar la productividad y la eficiencia en diferentes escenarios empresariales.

## <span style="color: #00A1DD">Requerimientos y Consola recomendada</span>
Para iniciar con el uso de los Scripts de automatización es importante mencionar que se desarrollaran usando el lenguaje de programación Python (<img src="https://raw.githubusercontent.com/FortAwesome/Font-Awesome/0698449d50f2b95517562295a59d414afc68b369/svgs/brands/python.svg" width="15" height="15">), por lo que se debe tener instalada una version reciente de este lenguaje.
Tambien sera importante contar con una terminal de comandos para el sistema operativo respectivo, en el caso de Windows se recomienda usar cmder:
![Consola](images\console.png "cmder-windows")

## <span style="color: #00A1DD">Entornos virtuales</span>
Siguiendo la recomendación de buenas practicas, es util desplegar el entorno de desarrollo del script sobre un entorno virtual de python, para esto se debe crear una carpeta y dirigiendose desde la terminal hasta esta nueva ruta ejecutar el siguiente comando:

```bash
python -m venv name_entorno
```
Esto creara el entorno virtual el cual ademas se debe activar con el siguiente comando:

```bash
name_entorno\Scripts\Activate
```
Ya activado el entorno virtual se procede a instalar sobre este las respectivas librerías de python que se deben usar.
*Nota:* Si yo no se va a usar el entorno virtual se puede desactivar usando el comando:

```bash
deactivate
```
## <span style="color: #00A1DD">Libreria de Automatización</span>
La libreria que se usara para desarrollar los scripts de automatización de python se llama **Pyautogui** y para el uso de rutas la libreria **Os**.
La documentacion de la librería principal de los scripts se anea en el siguiente link:

[Documentación-Pyautogui](https://pyautogui.readthedocs.io/en/latest/keyboard.html)