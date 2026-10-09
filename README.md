# Chika · Landing de experiencias capilares

Landing tipo catálogo de Chika Beauty Center & Spa. Next.js 16 (App Router) + TypeScript, CSS propio.

## Desarrollo

```bash
npm install
npm run dev      # http://localhost:3000
npm run build    # build de producción
```

## Publicar en Vercel

1. En [vercel.com/new](https://vercel.com/new) importá el repositorio `estebanetwo18-collab/CHIKA`.
2. Framework: **Next.js** (se detecta solo). No hace falta cambiar comandos.
3. En *Environment Variables* agregá (también se pueden cargar después y volver a desplegar):
   - `NEXT_PUBLIC_CHIKA_WHATSAPP`: número oficial, solo dígitos con código de país (ej. `506XXXXXXXX`).
   - `NEXT_PUBLIC_CHIKA_INSTAGRAM`: URL completa del perfil.
   - `NEXT_PUBLIC_CHIKA_SITE_URL` (opcional): dominio final, ej. `https://chika.cr`.
4. *Deploy*. Cada push a `main` vuelve a publicar.

Sin `NEXT_PUBLIC_CHIKA_WHATSAPP`, los botones abren WhatsApp con el mensaje listo pero sin destinatario.

## Dónde editar

- Experiencias, precios, sesiones, vigencias y mensajes de WhatsApp: `src/lib/chika/experiences.ts`
- Textos generales, preguntas frecuentes, selector: `src/lib/chika/content.ts`
- Contacto (dirección, horario) y enlaces de WhatsApp: `src/lib/chika/config.ts`
- Fotos: reemplazá el archivo en `public/chika/` con el mismo nombre (ver `public/chika/CREDITOS.md`).
- QR: agregá `public/chika/chika-whatsapp-qr.png` y aparece solo.

Los datos pendientes se marcan en magenta solo en desarrollo (`npm run dev`); en producción se ven en tono neutro.

## Analítica

Eventos enviados a GTM (dataLayer), GA4 (gtag) y Meta Pixel si están instalados:
`whatsapp_click`, `experience_cta_click`, `curl_love_cta_click`, `selector_answer`,
`selector_recommendation`, `scroll_depth`, `nav_click`, `faq_open`
(parámetros `location`, `experience`, `cta_type`).
