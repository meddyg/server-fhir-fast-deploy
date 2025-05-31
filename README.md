# HAPI FHIR CLI Deployment Tool v1.0.0

Herramienta de línea de comandos para desplegar un servidor HAPI FHIR, cargar la guía de implementación HL7 FHIR Core de HIE-cr y registrar todos los recursos automáticamente.

## Requerimientos previos

- Docker instalado y en ejecución
- El archivo de configuración YAML debe estar correctamente configurado

## Características

- Despliega automáticamente la imagen Docker oficial de HAPI FHIR
- Descarga y extrae el paquete FHIR de HIE-cr desde build.fhir.org
- Carga todos los recursos FHIR JSON al servidor
- Configuración personalizable mediante archivo YAML externo
- Compatible con Windows y Linux

## Instrucciones de uso

```bash
./deploy-hapi <ruta-config-yaml> [puerto] [ruta-socket-docker]
```

### Argumentos

- `<ruta-config-yaml>`: Ruta absoluta al archivo de configuración YAML para HAPI
- `[puerto]`: Puerto para exponer el servidor HAPI (predeterminado: 8080)
- `[ruta-socket-docker]`: Ruta al socket de Docker (predeterminado: /var/run/docker.sock)

### Ejemplo

```bash
# Linux
./deploy-hapi /ruta/a/mi/config.yaml 8080 /var/run/docker.sock

# Windows
./deploy-hapi.exe C:\ruta\a\mi\config.yaml 8080 //./pipe/docker_engine
```

## Binarios incluidos

- `deploy-hapi` - Versión para Linux
- `deploy-hapi.exe` - Versión para Windows

## Configuración YAML

Crear un archivo `application.yaml` o descargar el archivo de ejemplo desde el repositorio. Este archivo debe contener la configuración del servidor HAPI y los recursos FHIR a cargar.

## Requisitos

- Docker instalado y en ejecución
- Acceso a Internet para descargar la imagen HAPI y el paquete FHIR
