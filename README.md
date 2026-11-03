# AgroSoft — Frontend

Interfaz web del sistema de gestión de planta y granjas.
No requiere compilación: es HTML, CSS y JavaScript puro.

## Configuración

Antes de usarlo, edita `config.js` y pon la URL de tu backend:

```js
window.AGROSOFT_CONFIG = {
  API_URL: 'http://localhost:3000'      // en producción: https://api.tudominio.com
};
```

## Uso local

Ábrelo con cualquier servidor estático. Por ejemplo:

```
npx serve .
```

O simplemente abre `index.html` en el navegador (si el backend permite el origen).

## Despliegue

Al ser archivos estáticos, se puede servir con Nginx (igual que el sitio web de
la empresa) o subir a cualquier hosting estático. Solo asegúrate de que
`config.js` apunte al backend correcto y que la URL del frontend esté incluida
en la variable `FRONTEND_URL` del backend (para CORS).

## Usuario de pruebas
- Correo: jonatanbotero0105@gmail.com
- Contraseña temporal: CambiarEsta2026  (cámbiala al entrar)
