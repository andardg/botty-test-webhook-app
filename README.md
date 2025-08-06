# Meta Test Webhook App

Una aplicación webhook simple para recibir y procesar eventos de Meta (Facebook) utilizando Node.js y Express.

## 📋 Características

- ✅ Verificación de webhook de Meta
- 📨 Recepción y logging de eventos POST
- 🔒 Manejo seguro de tokens de verificación
- 📝 Logging detallado con timestamps
- 🚀 Fácil configuración y despliegue

## 🛠️ Instalación

1. Clona el repositorio:

```bash
git clone https://github.com/andardg/meta-test-webhook-app.git
cd meta-test-webhook-app
```

1. Instala las dependencias:

```bash
npm install
```

1. Configura las variables de entorno:

```bash
cp .env.example .env
```

1. Edita el archivo `.env` con tus valores:

```bash
PORT=3000
VERIFY_TOKEN=tu_token_de_verificacion_de_meta
```

## 🚀 Uso

### Ejecutar en modo desarrollo

```bash
npm start
```

### Ejecutar con nodemon (si está instalado)

```bash
npm run dev
```

La aplicación estará disponible en `http://localhost:3000`

## 🔧 Configuración del Webhook en Meta

1. Ve a [Meta for Developers](https://developers.facebook.com/)
2. Crea o selecciona tu aplicación
3. Añade el producto "Webhooks"
4. Configura la URL del webhook: `https://tu-dominio.com/`
5. Usa el mismo `VERIFY_TOKEN` que configuraste en tu `.env`

## 📡 Endpoints

### GET `/`

- **Propósito**: Verificación del webhook
- **Parámetros de consulta**:
  - `hub.mode`: Debe ser "subscribe"
  - `hub.challenge`: Valor que debe ser devuelto
  - `hub.verify_token`: Debe coincidir con tu VERIFY_TOKEN

### POST `/`

- **Propósito**: Recibir eventos del webhook
- **Respuesta**: 200 OK
- **Acción**: Registra el evento en la consola con timestamp

## 📁 Estructura del Proyecto

```text
meta-test-webhook-app/
├── app.js              # Aplicación principal
├── package.json        # Dependencias y scripts
├── .env.example        # Plantilla de variables de entorno
├── .env               # Variables de entorno (no versionado)
├── .gitignore         # Archivos a ignorar por Git
└── README.md          # Este archivo
```

## 🔒 Seguridad

- El archivo `.env` está incluido en `.gitignore` para proteger las credenciales
- La verificación del token es obligatoria para todos los requests GET
- Solo se aceptan tokens que coincidan exactamente

## 📝 Variables de Entorno

| Variable | Descripción | Valor por defecto |
|----------|-------------|-------------------|
| `PORT` | Puerto donde se ejecuta el servidor | `3000` |
| `VERIFY_TOKEN` | Token de verificación de Meta | Requerido |

## 🤝 Contribuir

1. Haz fork del proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📄 Licencia

Este proyecto está bajo la Licencia ISC - ver el archivo [LICENSE](LICENSE) para más detalles.

## 🐛 Reportar Problemas

Si encuentras algún problema, por favor abre un [issue](https://github.com/andardg/meta-test-webhook-app/issues) en GitHub.