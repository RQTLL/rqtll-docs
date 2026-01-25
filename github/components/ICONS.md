# Catálogo de Iconos (RQT2)

Este documento detalla la librería de iconos utilizados en el ecosistema **RQT2**. Todos los iconos son archivos **SVG** optimizados para ser escalables y ligeros.

## Estándares
- **Formato:** SVG v1.1
- **Dimensiones Base:** 1920x1920
- **Margenes**: 228

---

## Organización de carpetas
Cada icono se encuentra dentro de su propia subcarpeta en `assets/icons/`:
```text
assets/icons/<icon>/
├── default.svg
├── hover.svg
└── disabled.svg
```

---

## Categorias

- [Accesos directos](#accesos-directos)
- [Construcción](#construcción)
- [Ejecución](#ejecución)
- [Herramientas](#herramientas)
- [Botones de Ventana](#botones-de-ventana)

### Accesos directos

| Icono | Nombre | Comando relacionado | Rol |
| :---: | :----- | :------------------ | :--- |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/3d/default.svg"></kbd> | **3d** | `rviz2` | Acceso directo a RViz. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/emulator/default.svg"></kbd> | **emulator** | `gz sim` | Acceso directo a `gz sim` (Simulador de Gazebo). |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/widgets/default.svg"></kbd> | **widgets** | `rqt` | Acceso directo a rqt. |


### Construcción

| Icono | Nombre | Comando relacionado | Rol |
| :---: | :--- | :--- | :--- |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/compile/default.svg"></kbd> | **compile** | `rosdep install ; colcon build ; souce install/setup.bash` | Crea el espacio de trabajo de ROS2: Primero resuelve dependencias con `rosdep install` para construir el espacio de trabajo con `colcon build` y finalmente cargar el overlay generado. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/clean/default.svg"></kbd> | **clean** | `rm -rf build install log` | Elimina los directorios `build`, `install` y `log` creados por `colcon build`. 
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/load/default.svg"></kbd> | **load** | `source setup.bash` | Carga el overlay `install/setup.$SHELL` generado por `colcon build`. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/settings/default.svg"></kbd> | **settings** | nueva función de la IDE | Abre un fomulario para editar archivos de configuración de paquetes de ROS2 como **package.xml** o **CMakeList.txt**. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/new/default.svg"></kbd> | **new** | `ros2 pkg create` | Crea elementos nuevos (paquetes/lanzadores/nodos). |

### Ejecución

| Icono | Nombre | Comando relacionado | Rol |
| :---: | :--- | :--- | :--- |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/launch/default.svg"></kbd> | **launch** | nueva función de la IDE | Abre la ventana de nodos y lanzadores disponibles. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/run/default.svg"></kbd> | **run** | `ros2 run `/`ros2 launch` | Ejecuta nodos o lanzadores. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/stop/default.svg"></kbd> | **stop** | `kill`/`pkill` | Detiene nodos o lanzadores en ejecución. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/bug/default.svg"></kbd> | **bug** | `ros2 run --prefix 'gdb -ex run --args' ; (gdb) backtrace` | Obtener backtrace de nodos usando `gdb`. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/teleop/default.svg"></kbd> | **teleop** | `ros2 run teleop_twist_keyboard teleop_twist_keyboard` | Abre un formulario para enviar instrucciones de control manual con `ros2 teleop`. |

### Herramientas

| Icono | Nombre | Comando relacionado | Rol |
| :---: | :--- | :--- | :--- |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/list/default.svg"></kbd> | **list** | nueva función de la IDE | Abre la ventana de nodos y topicos en ejecución. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/nodes/default.svg"></kbd> | **nodes** | Nueva función de la IDE | Abre `node-graph` (una ventana parecida a `rqt_graph`). |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/params/default.svg"></kbd> | **params** | Nueva función de la IDE | Abre un fomulario para editar parametros de nodos (`ros2 param set`). |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/synchronize/default.svg"></kbd> | **unsynchronize** | función de la IDE | Se desconecta de topicos anteriormente conectado desde la IDE. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/unsynchronize/default.svg"></kbd> | **synchronize** | `ros2 echo`/`ros2 pub` | Se conecta a topicos como publicador o subscriptor. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/record/default.svg"></kbd> | **record** | `ros2 bag record -o subset ` | Graba los datos publicados sobre un topico con `ros2 bag`. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/play/default.svg"></kbd> | **play** | `ros2 bag play subset` | Reproduce los datos grabados de un topico con `ros2 bag`. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/daemon/default.svg"></kbd> | **daemon** | `ros2 daemon stop ; ros2 daemon start` | Reinicia el proceso de ROS2. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/ssh/default.svg"></kbd> | **ssh** | `ssh` | Abre un formulario para establecer una conexión SSH. |

### Botones de Ventana

| Icono | Nombre | Comando relacionado | Rol |
| :---: | :--- | :--- | :--- |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/close/default.svg"></kbd> | **close** | Window button | Cerrar ventana. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/minimize/default.svg"></kbd> | **minimize** | Window button | Minimizar ventana. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/restore/default.svg"></kbd> | **maximize** | Window button | Maximizar ventana. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/maximize/default.svg"></kbd> | **restore** | Window button | Restaura el tamaño de la ventana. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/tab/default.svg"></kbd> | **split** | Window button | Abre una terminal. |
| <kbd><img align="left" width="22px" alt="." src="https://github.com/RQT2/rqt2-components/blob/main/assets/icons/split/default.svg"></kbd> | **tab** | Window button | Cierra la terminal. |
