# Galosoft Marketing · sitio web

Este sitio usa el mismo sistema de diseño que Contable, Support y Web, con paleta propia: base clara cálida #FBF7F4, carbón #1F1918 y acento coral #FF6B4A. Los títulos usan Outfit.

## Estructura
- **Sitio:**
  - `index.html`: Inicio
  - `servicios.html`
  - `paquetes.html` (sin precio visible)
  - `nosotros.html`
  - `contacto.html`
  - `aviso-de-privacidad.html`
- **Landings** (sin menú, con el formulario arriba):
  - `google-business.html`
  - `anuncios.html`
  - `prospectos-whatsapp.html`
- **`assets/`:** estilos, JS, favicon y `og-marketing.png`, la imagen para las vistas previas.

## Publicar
1. Sube todo a `public_html` de galosoftmarketing.com. La URL canónica es **https://galosoftmarketing.com**, sin `www`.
2. **Redirección 301** del sitio anterior, en el `.htaccess` de galosoft.com:
   ```
   RedirectMatch 301 ^/marketing/?(.*)$ https://galosoftmarketing.com/$1
   ```
3. En `assets/main.js`, pon la URL de tu webhook de n8n en `WEBHOOK`.
4. En el nodo Webhook de n8n:
   - Método POST.
   - Responder con código 200.
   - CORS: agrega `https://galosoftmarketing.com`.

   El JSON que recibe trae estos campos: `nombre`, `telefono`, `negocio`, `interes`, `acepto`, `marca`, `origen`, `pagina`, `utm` y `fecha`.

   El campo `negocio` te permite buscar la ficha de Google del prospecto antes de responderle.

## Pendientes antes de publicar
- [ ] URL del webhook de n8n.
- [ ] Contenido de cada paquete (Presencia, Crecimiento, Captación) y plazo mínimo, si existe.
- [ ] Cookies: si instalas Meta Pixel o Google Analytics (lo normal en una agencia de marketing), menciónalo en el aviso de privacidad.
- [ ] Casos de clientes: la sección está comentada en `index.html`. Actívala solo con autorización y cifras reales medidas.
- [ ] Confirmar los supuestos del texto:
  - Tú administras las campañas.
  - La inversión en anuncios se paga directo a Meta o Google.
  - El asistente virtual de WhatsApp forma parte de la oferta.
  - Las fichas de Google y las cuentas de anuncios quedan a nombre del cliente.
- [ ] Logo definitivo. La "G" es provisional.
