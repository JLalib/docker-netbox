# netbox-docker

![GitHub release](https://img.shields.io/github/v/release/netbox-community/netbox-docker)
![GitHub stars](https://img.shields.io/github/stars/netbox-community/netbox-docker)
![GitHub closed pull requests](https://img.shields.io/github/issues-pr-closed/netbox-community/netbox-docker)
![Docker Pulls](https://img.shields.io/docker/pulls/netboxcommunity/netbox)
![License](https://img.shields.io/github/license/netbox-community/netbox-docker)

## Introducción

**NetBox** es una herramienta de código abierto ampliamente utilizada para la **documentación y gestión de infraestructuras**, incluyendo redes, direcciones IP (IPAM), racks, dispositivos y virtualización.

Este repositorio, **netbox-docker**, proporciona todo lo necesario para desplegar NetBox de forma **rápida, reproducible y sencilla** utilizando contenedores Docker, evitando instalaciones complejas y facilitando su uso tanto en entornos de laboratorio como en producción.

El proyecto está desarrollado y mantenido por la **comunidad oficial de NetBox**, y las imágenes se construyen y publican de forma regular en distintos registros de contenedores.

---

## Descripción del proyecto

El repositorio de GitHub contiene todos los componentes necesarios para ejecutar **NetBox** como aplicación contenerizada.

Las imágenes Docker se generan automáticamente a partir del código de este repositorio y se publican en:

- Docker Hub  
- Quay.io  
- GitHub Container Registry  

**NetBox Docker** es un proyecto comunitario, mantenido activamente y alineado con las versiones oficiales de NetBox.

---

## Soporte y comunidad

¿Tienes alguna pregunta o problema?  
Antes de abrir una *issue* en GitHub, te recomendamos:

- Unirte al **Slack de NetBox**
- Pedir ayuda en el canal **#netbox-docker**
- O iniciar una nueva **GitHub Discussion**

Esto ayuda a mantener el repositorio ordenado y facilita una respuesta más rápida.

---

## Quickstart

A continuación se muestran los pasos mínimos para poner NetBox Docker en funcionamiento.  
Existe una guía más completa en el **wiki oficial** que explica cada paso en detalle.

### 1. Clonar el repositorio

```bash
git clone -b release https://github.com/netbox-community/netbox-docker.git
cd netbox-docker
```

### 2. Crear el archivo de configuración

Copia el archivo de ejemplo:

```bash
cp docker-compose.override.yml.example docker-compose.override.yml
```

Edita el archivo `docker-compose.override.yml` según tus necesidades (usuarios, base de datos, variables de entorno, etc.).

### 3. Descargar imágenes y levantar el entorno

```bash
docker compose pull
docker compose up
```

Tras unos minutos, la aplicación estará disponible en:

```
http://0.0.0.0:8000/
```

Deberías ver la página principal de NetBox en tu navegador.

---

## Crear el primer usuario administrador

Para crear el primer usuario administrador, ejecuta el siguiente comando:

```bash
docker compose exec netbox /opt/netbox/netbox/manage.py createsuperuser
```

Sigue las instrucciones en pantalla para definir el usuario, correo electrónico y contraseña.

### Creación automática del superusuario (opcional)

Si necesitas reiniciar NetBox frecuentemente desde una base de datos vacía, puedes definir las variables:

- `SUPERUSER_NAME`
- `SUPERUSER_EMAIL`
- `SUPERUSER_PASSWORD`

en el archivo `docker-compose.override.yml`, para que el usuario administrador se cree automáticamente al arrancar.

---


## Referencias

- Repositorio oficial: https://github.com/netbox-community/netbox-docker
- Documentación NetBox: https://netbox.readthedocs.io/


<img width="600" height="200" alt="image" src="https://github.com/user-attachments/assets/d98bbf2e-a80c-4835-9f16-ba18dbce20bd" />

