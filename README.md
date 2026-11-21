# GestorPro - Control Empresarial, Inventario, Caja Multimoneda y Catálogo WhatsApp

**Autor / Desarrollador:** Joelbi José Salazar Vargas  
**Versión:** 3.0 (Lista para PWABuilder / Google Play Store)

## Descripción General
**GestorPro** es una Progressive Web App (PWA) optimizada para Android y Google Play Store diseñada para adaptarse a cualquier modelo de negocio (**Productos físicos, Servicios, Comida preparada y bebidas, o Negocios personalizados**). Permite administrar múltiples tiendas de forma independiente, sincronizar en tiempo real con socios, encargados y empleados mediante códigos QR únicos por tienda, gestionar inventario con lector de código de barras, controlar caja en moneda local, dólares y banco, vender por catálogo digital en WhatsApp y emitir facturas/reportes ejecutivos en PDF.

## Estructura de Archivos
- `index.html`: Aplicación completa (UI responsiva, motor de traducción en 10 idiomas, autenticación con verificación por correo/SMS, Firestore en tiempo real, escáner de códigos de barras y QR, gráficas financieras, impresión Bluetooth/Web y generador de reportes PDF).
- `manifest.json`: Configuración PWA con soporte para iconos adaptativos (`icono-192.png`, `icono-512.png`) y orientación vertical.
- `sw.js`: Service Worker con estrategia *Stale-While-Revalidate* y tolerancia a fallos para operación offline ultrarrápida.
- `icono-192.png` e `icono-512.png`: Iconos oficiales listos para PWA y Google Play.
- `PRIVACIDAD_Y_TERMINOS.md`: Términos de uso y Política de Privacidad listos para publicar en Google Play Console y Firebase.

## Configuración Necesaria antes de Publicar en Google Play
1. **Firebase Authentication & Firestore:**
   - En la consola de Firebase (`gestorpro-sync-8b047`), habilita **Authentication** -> **Correo electrónico/Contraseña** y **Teléfono (SMS)**.
   - Configura las reglas de seguridad de **Cloud Firestore** para proteger las colecciones `users` y `stores`.
2. **Google Play Billing & AdMob (Puentes Nativos):**
   - En `index.html`, busca la sección marcada con `// === PUENTE GOOGLE PLAY BILLING (DIGITAL GOODS API) ===` e inserta tus IDs de producto (`gestorpro_mensual_5usd`, `gestorpro_anual_45usd`) y tus unidades de anuncios (`Banner` y `Rewarded Video` cada 6 horas) al compilar con PWABuilder / Android Studio.
