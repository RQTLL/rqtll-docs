# rqt2-components

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/branding/logo-main-light.svg">
  <source media="(prefers-color-scheme: light)" srcset="./assets/branding/logo-main-dark.svg">
  <img alt="RQT2 Logo" src="./assets/branding/logo-main-color.svg" width="50px">
</picture>

Sistema de diseño y librería de recursos visuales para **[RQT2](https://github.com/RQT2)**.

> [!CAUTION]
> Este es un repositorio núcleo. Cualquier cambio en la paleta o iconos se propagará a todos los módulos que lo consumen.

## Table of Contents
- [Quickstart](#quickstart)
- [Estructura del Repositorio](#estructura-del-repositorio)
- [Recursos Visuales](#recursos-visuales)
- [Tipografía](#tipografía)
- [Uso de Estilos (QSS)](#uso-de-estilos-qss)
- [Cómo contribuir](#cómo-contribuir)
- [License](#license)
- [Maintainers](#maintainers)

## Quickstart

Este repositorio está diseñado para ser consumido como un **Git Submodule**. Esto permite que los recursos estén disponibles *offline*

### Añadir a un módulo nuevo
```bash
# Usa la carpeta external/ para recursos compartidos
git submodule add https://github.com/RQT2/rqt2-components.git external/rqt2-components
git submodule update --init --recursive

```

### Sincronizar cambios

```bash
git submodule update --remote --merge
```

## Estructura del Repositorio

```text
./
├── assets/
│   ├── branding/       # Identidad de marca (Isotipos)
│   ├── icons/          # Librería de iconos para acciones de ROS 2
├── media/
│   └── fonts/          # Fuentes Nunito Sans y Ubuntu Mono/Nerd Font Mono
├── styles/
│   ├── themes/         # Hojas de estilo .qss (light/dark)
│   └── palette.json    # Definición maestra de colores (Hex)
├── releases/           # Capturas soficiales para documentación (.deb)
└── README.md

```

## Recursos Visuales

Para mantener la agilidad del repositorio, la documentación detallada se ha segmentado:

* **Catálogo de Iconos ([ICONS.md](https://github.com/RQT2/rqt2-docs/github/components/ICONS.md))**: Tabla completa de iconos, comandos asociados y sus roles.
* **Identidad de Marca ([BRANDING.md)](https://github.com/RQT2/rqt2-docs/github/components/BRANDING.md))**: Guía de uso del isotipo, márgenes de seguridad para iconos y exportación.
* **Paleta Detallada ([PALETTE.md)](https://github.com/RQT2/rqt2-docs/github/components/PALETTE.md))**: Muestrario completo de colores para temas Claro y Oscuro.

## Tipografía

El proyecto utiliza fuentes locales para garantizar consistencia sin conexión a internet.

| Fuente | Uso | Licencia |
| --- | --- | --- |
| **Nunito Sans** | Interfaz de Usuario (UI) | OFL |
| **Ubuntu Mono** | Terminal, Logs y Código | UFL |
| **Ubuntu Nerd Font Mono** | Glifos técnicos e iconos integrados | UFL |

## Uso de Estilos (QSS)

Los estilos siguen un formato **Flat Modern Minimalist** con bordes redondeados calculados al **18.75%** de la dimensión mínima.

```python
# Ejemplo de carga en PySide6
from PySide6.QtWidgets import QApplication

def load_theme(app, theme_name="dark"):
    with open(f"external/rqt2-components/styles/themes/{theme_name}.qss", "r") as f:
        app.setStyleSheet(f.read())

```

## Cómo contribuir

- Lee [CONTRIBUTING.md](CONTRIBUTING.md) antes de enviar PR.
- Para añadir un icono nuevo:
  1. Añadir capas para los estatus `default`, `hover` y `click` a **assets/icons/window-buttons.xcf**
  2. Añadir SVGs a **assets/icons/<nombre_del_icono>**.
  3. Actualizar **assets/ICONS.md** con el icono, nombre, comando y rol.
  4. Crear PR con descripción y captura.

## License

Este proyecto está bajo la licencia **MIT**. Consulta el archivo [LICENSE](LICENSE) para más detalles.

## Maintainers

* **adnKSharp** <adnksharp@gmail.com>

