# Hospedaje Centenario UNADECA 2027

Sitio promocional estático para el hospedaje del Centenario de la Universidad
Adventista de Centro América (UNADECA), 2027. Evento para 84 personas, 4
noches en Alajuela, Costa Rica. Presenta 10 hoteles agrupados en 3 niveles,
con tarifas, fotos y datos de contacto, para que los asistentes reserven
directamente con cada hotel.

## Stack

Next.js 16 (App Router, export estático) · React 19 · TypeScript · Tailwind CSS 4 · pnpm

## Estructura

- `src/app` — páginas: inicio, ficha de cada hotel (`/hoteles/[slug]`).
- `src/components` — UI por sección: tarjetas de hotel, layout, galería de fotos.
- `src/lib/datos` — los 10 hoteles, tarifas y contenido. Único lugar que se
  edita para actualizar precios o agregar un hotel.
- `scripts/` — optimización de imágenes y precompresión (Brotli/gzip) para el build.

## Comandos

```bash
pnpm install
pnpm dev             # http://localhost:3000
pnpm typecheck
pnpm build           # exporta el sitio estático y precomprime los assets
pnpm build:imagenes  # genera las variantes AVIF/WebP de las fotos
```

## Cómo se calculan los precios

El precio mostrado por hotel es el costo de las 4 noches para 2 personas, no
un precio por persona por noche. Cada hotel cobra distinto (por persona o por
habitación), así que el cálculo normaliza eso y siempre indica de qué tarifa
salió el mínimo mostrado.

## Estado

Datos cargados para los 10 hoteles. El plan de mejoras pendiente, con qué se
verificó en cada una, está en `docs/MEJORAS.md`.
