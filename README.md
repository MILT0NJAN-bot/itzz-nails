# Itzz Nails

Aplicación profesional de agenda y administración para Itzz Nails.

## Ejecutar

```powershell
node server.js
```

Abre `http://localhost:8080`. No requiere instalar paquetes: usa SQLite incluido en Node 22.

## Funciones

- Base de datos SQLite persistente.
- Catálogo de servicios, variantes, precios, duración y descanso posterior.
- Disponibilidad calculada por el servidor.
- Transacciones que previenen dobles reservaciones.
- Calendario administrativo mensual y detalle de cada cita.
- Bloqueos de agenda por asuntos personales, comida o días especiales.
- Horarios configurables por día.
- Galería de trabajos almacenada en la base de datos.
- Autenticación con contraseña cifrada y cookie de sesión HTTP-only.
- Confirmación administrativa y aviso por WhatsApp.
- Panel separado en `admin.html`, con pestaña y mes persistentes al refrescar.

## Acceso administrativo inicial

- Correo: `admin@itznails.local`
- Contraseña: `ItzNails2026!`

Para producción define `ADMIN_PASSWORD` antes del primer arranque, configura HTTPS y realiza respaldos de `data/itznails.db`.

## WhatsApp automático

La confirmación siempre prepara el mensaje y el número. Sin credenciales abre WhatsApp para que la administradora solamente pulse **Enviar**. Para envío totalmente automático configura estas variables del entorno con una cuenta de WhatsApp Business Cloud API:

```text
WHATSAPP_TOKEN
WHATSAPP_PHONE_NUMBER_ID
WHATSAPP_TEMPLATE_NAME
WHATSAPP_TEMPLATE_LANGUAGE=es_MX
WHATSAPP_GRAPH_VERSION=v23.0
```

La plantilla aprobada en Meta debe tener cuatro variables en el cuerpo, en este orden: nombre de la clienta, servicio, fecha y hora.

Los precios iniciales fueron transcritos de las imágenes proporcionadas. Los servicios con precios por largo o acabado incluyen variantes dentro de la base de datos.
