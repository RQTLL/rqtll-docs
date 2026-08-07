# rqtll-docs

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github.com/RQTLL/rqtll-components/blob/main/assets/branding/logo-main-light.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://github.com/RQTLL/rqtll-components/blob/main/assets/branding/logo-main-dark.svg">
  <img alt="RQTLL Logo" src="https://github.com/RQTLL/rqtll-components/blob/main/assets/branding/logo-main-color.svg" width="50px">
</picture>

Repositorio de documentación centralizada y capturas de pantalla oficiales para el ecosistema RQTLL. Este repositorio almacena las guías generales, manuales y recursos multimedia para los READMEs y wikis del proyecto.

## Table of Contents
- [rqtll-docs](#rqtll-docs)
  - [Table of Contents](#table-of-contents)
  - [Estructura de Capturas](#estructura-de-capturas)
    - [Taxonomía de Nombres de Archivo](#taxonomía-de-nombres-de-archivo)
  - [Captura Global Vectorial (F12)](#captura-global-vectorial-f12)
    - [Métodos de Captura](#métodos-de-captura)
  - [Documentos](#documentos)
  - [Cómo contribuir](#cómo-contribuir)
  - [Security](#security)
  - [License](#license)
  - [Maintainers](#maintainers)

---

## Estructura de Capturas

Las capturas de pantalla de la interfaz de usuario se organizan de forma jerárquica para mantener la modularidad y optimización web:

```text
screenshot/
├── dark/                   # Capturas con Tema Oscuro (Dark Theme)
│   ├── pdf/                # Documentos vectoriales PDF imprimibles
│   ├── svg/                # Capturas vectoriales SVG puras (con fuentes incrustadas)
│   └── web/                # Capturas en formato WebP optimizadas para visualización web
└── light/                  # Capturas con Tema Claro (Light Theme)
    ├── pdf/
    ├── svg/
    └── web/
```

### Taxonomía de Nombres de Archivo
- `A1-WIZARD-*`: Capturas correspondientes a los pasos del asistente de instalación de ROS 2.
- `A2-START-*`: Capturas de la pantalla de bienvenida y cargador de espacios de trabajo.
- `A3-WORKSPACE-*`: Capturas del área de trabajo activa de la IDE (Editor de código, Lanzador, Control, terminal virtual, etc.).

---

## Captura Global Vectorial (F12)

La IDE (`rqtll-ide`) incluye un filtro global de eventos de teclado que permite tomar capturas de la ventana activa en cualquier momento:

### Métodos de Captura
* **Atajos**: Presiona **`F12`** o **`Ctrl + Shift + S`** con la ventana de la IDE enfocada.
* **Proceso**:
  1. Se abrirá un diálogo del sistema para elegir la ruta de guardado (`.svg`).
  2. La aplicación temporalmente desactivará el renderizado de caché de todos los elementos gráficos complejos (`QGraphicsItem` en la vista de nodos) para forzar un repintado vectorial puro.
  3. Todos los elementos gráficos, bordes y estilos QSS se pintan directamente en el archivo SVG.
  4. Se incrustan las fuentes tipográficas locales (`Nunito Sans` y `Ubuntu Mono`) codificadas en **Base64** dentro de un elemento `<defs><style>` del SVG.
  5. Se restablece la configuración de caché de los elementos de forma transparente.
  6. Es necesario exportar el archivo SVG a PDF y WEBM por separado para tener una vista previa del documento (se recomienda usar [Inkscape](https://inkscape.org) o [Adobe Illustrator](https://adobe.com/es/products/illustrator.html)).

> En ocasiones la captura puede incluir elementos no deseados, se recomienda editar el archivo SVG con un editor de gráficos vectoriales para eliminar dichos elementos.

---

## Documentos

Los documentos de cada repositorio se mantienen dentro de los mismos para mantener la coherencia del proyecto. Puedes encontrar los siguientes documentos:

- [CONTRIBUTING.md](CONTRIBUTING.md)
- [README.md](README.md)
- [SECURITY.md](SECURITY.md)
- [LICENSE](LICENSE)

```text
rqtll-api/              # API para interacción entre el sistema y Qt.
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── SECURITY.md
rqtll-components/       # Iconos, imágenes, estilos QSS, fuentes, etc.
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── SECURITY.md
rqtll-distro/           # Empaquetado de RQTLL
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── SECURITY.md
rqtll-ide/              # Entorno de desarrollo RQTLL
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── SECURITY.md
rqtll-service/          # Backend de RQTLL
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── SECURITY.md
rqtll-widgets/          # Frontend de RQTLL
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── SECURITY.md
```

## Cómo contribuir

- Lee [CONTRIBUTING.md](CONTRIBUTING.md) antes de enviar un Pull Request.
- Si generas nuevas capturas con el atajo `F12`, recuerda convertirlas a `.webp` usando herramientas como `cwebp` o `ffmpeg` y subirlas a la carpeta `web/` respectiva para optimizar el tamaño de descarga en GitHub.
- Los archivos `.svg` pesados con fuentes incrustadas deben almacenarse en la carpeta `svg/`.

## Security

Consulta [SECURITY.md](SECURITY.md) para conocer el procedimiento de reporte de vulnerabilidades.

## License

Este proyecto está bajo la licencia **MIT**. Consulta el archivo [LICENSE](LICENSE) para más detalles.

## Maintainers

* **adnKSharp** <adnksharp@gmail.com>
