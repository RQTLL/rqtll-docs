# rqt2-api

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github.com/RQT2/rqt2-components/blob/main/assets/branding/logo-main-light.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://github.com/RQT2/rqt2-components/blob/main/assets/branding/logo-main-dark.svg">
  <img alt="RQT2 Logo" src="https://github.com/RQT2/rqt2-components/blob/main/assets/branding/logo-main-color.svg" width="50px">
</picture>

API gRPC/protobuf que define los contratos entre la IDE (`rqt2-ide` / frontends PySide6) y los backends (`rqt2-rcl-utils`, agentes, daemons) del ecosistema RQT2.

## Table of Contents
- [Quickstart](#quickstart)
- [Estructura del Repositorio](#estructura-del-repositorio)
- [Cómo contribuir](#cómo-contribuir)
- [Security](#security)
- [License](#license)
- [Maintainers](#maintainers)

## Quickstart

Este crate genera los stubs Rust (clientes y servidores) a partir de los `.proto` en `proto/` usando `tonic-build` en `build.rs`.

### Requirements

- Rust (stable, 1.70+ recommended)
- `protoc` (Protocol Buffers compiler)

### Build / Generar stubs

```bash
# Desde la raíz del crate
cd rqt2-api
cargo build
```

El comando anterior invocará `build.rs` que compila todos los `.proto` usando `tonic_build` y `prost`.

### Uso desde Rust

`rqt2_api::` contiene los módulos generados; los servicios se encuentran bajo `rqt2_api::rqt2.api.v1` (incluidos por `tonic::include_proto!("rqt2.api.v1")`).

## Estructura del Repositorio

```
./
├── proto/           # Definición de contratos protobuf (services, messages)
├── src/             # Código de arranque/examples que usan los stubs generados
├── build.rs         # Generación de stubs con tonic_build
├── Cargo.toml
└── README.md
```

## Cómo contribuir

Lee `CONTRIBUTING.md` para normas sobre modificación de `.proto`, versionado y pruebas.

En resumen:

- Modifica los `.proto` en la carpeta `proto/` y añade `reserved` cuando retires campos.
- Mantén compatibilidad hacia atrás: no reusar números de campo.
- Ejecuta `cargo build` para regenerar stubs y validar la compilación.
- Abre PR describiendo el cambio y el impacto en clientes.

## Security

Consulta `SECURITY.md` para el proceso de reporte de vulnerabilidades.

## License

Este proyecto está bajo la licencia **MIT**. Consulta el archivo [LICENSE](LICENSE) para más detalles.

## Maintainers
* **adnKSharp** <adnksharp@gmail.com>