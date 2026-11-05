# Auction Watch — repositorio de add-ons para Home Assistant

Este repositorio es el que agregás en Home Assistant para instalar
**Auction Watch**, un monitor de remates públicos que corre entero dentro de tu
instancia: no manda tus datos a ningún servicio y no necesita cuenta.

Si llegaste acá buscando el código, el desarrollo pasa en
[`Pisnaquio/auction-watch`](https://github.com/Pisnaquio/auction-watch). Este
repo es sólo el espejo que Supervisor sabe leer.

## Instalar

[![Add repository to my Home Assistant](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2FPisnaquio%2Fauction-watch-ha-addon)

Con ese botón se agrega solo. A mano, en Home Assistant andá a
**Settings → Add-ons → Add-on Store** (en las versiones nuevas el menú se llama
**Apps**), abrí el menú **⋮ → Repositories** y pegá:

```
https://github.com/Pisnaquio/auction-watch-ha-addon
```

Después buscá **Auction Watch** en el store e instalalo. La primera vez compila
la imagen en tu equipo, así que puede tardar varios minutos.

**La guía completa de instalación y configuración está en
[docs/INSTALL.md](https://github.com/Pisnaquio/auction-watch/blob/main/docs/INSTALL.md)**:
opciones del add-on, avisos por mail, perfiles de búsqueda, actualizaciones,
backups y troubleshooting.

## Antes de instalar

- **Necesitás Home Assistant OS o Supervised.** Los add-ons los instala
  Supervisor; con Home Assistant Container o Core no tenés store de add-ons.
  La guía explica cómo correrlo con Docker en ese caso.
- **Arquitectura `amd64` o `aarch64`** (un mini PC, un NUC, una Raspberry Pi 4
  o 5 con el sistema de 64 bits). Las placas de 32 bits (`armv7`) no están
  soportadas.
- **Las fuentes son uruguayas:** Bavastro, Castells, Remotes, TodoRemates y
  Prado. Si no te interesan remates en Uruguay, el add-on va a funcionar pero
  no te va a encontrar nada útil.

El add-on se publica en etapa **Experimental** y Home Assistant lo muestra con
esa etiqueta. No esconde nada ni bloquea la instalación.

## Qué hace

Definís perfiles de búsqueda —libros, discos, herramientas, lo que sea— con
keywords, frases exactas, exclusiones, límites de precio y las fuentes donde
mirar. El add-on escanea según la frecuencia de cada perfil y te avisa sólo
cuando aparece algo nuevo o cambia algo relevante, nunca con un mail de "no
encontré nada".

Viene con un perfil de ejemplo de consolas y juegos retro, que podés correr,
pausar y clonar para armar el tuyo.

## Actualizaciones

Activá el switch **Auto update** en la página del add-on y Supervisor aplica
cada versión nueva por su cuenta. Las actualizaciones no tocan tus perfiles ni
tu historial: viven en el almacenamiento persistente del add-on.

Las novedades de cada versión están en el
[CHANGELOG](https://github.com/Pisnaquio/auction-watch/blob/main/CHANGELOG.md).

## Reportar un problema

Los issues van al repositorio de la aplicación:
[Pisnaquio/auction-watch/issues](https://github.com/Pisnaquio/auction-watch/issues).

Si adjuntás el log del add-on, no incluyas `options.json` ni tus variables de
entorno: ahí están tus credenciales de SMTP.
