# Vegeta Ultra Ego — tema para Kino TV

Tema para toda la app inspirado en **Vegeta Ultra Ego**: interfaz **morado neón**, bordes afilados, aura eléctrica y un logo propio que dice **VEGETA** en morado eléctrico. Funciona en el celular y en la TV.

Es un plugin que **solo trae un tema**: son datos en el manifiesto, no corre código, no usa la red y no pide ninguna capacidad.

## Requisitos

- Kino **0.9.81** o posterior (`apiVersion` 18, temas de la app).
- Los bordes neón (`colors.border`, `shape.*Border`) se dibujan desde Kino **0.9.82**. En 0.9.81 el tema se ve igual, pero sin bordes.

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `kino-plugin.json` | Manifiesto: datos del plugin y el tema `ultra-ego` (colores, fondo, formas, logo, reproductor) |
| `plugin.js` | Vacío a propósito (`export {};`): Kino lo exige pero no lo llama |
| `icon.png` | Icono del plugin, 512×512, cuadrado, con las esquinas cortadas en transparente |
| `README.md` | Este archivo |

## Instalación

1. Sube la carpeta a un repositorio de GitHub (los cuatro archivos en la raíz).
2. En Kino, instala el plugin con su dirección `owner/repo`.
3. Activa el tema en **Ajustes ▸ Apariencia ▸ Vegeta Ultra Ego**. Kino te preguntará si quieres usar también la **experiencia completa** (sombras, efectos y esquinas redondeadas); el tema se ve mejor con ella.

Si lo publicas, no cambies el `id` del tema (`ultra-ego`) después: de él cuelgan la elección y los ajustes de cada persona.

## Paleta

| Token | Valor | Uso |
|---|---|---|
| `accent` | `#AA22FF` | Morado eléctrico: botones, selección, barra de progreso |
| `onAccent` | `#FFFFFF` | Texto e íconos sobre el acento |
| `background` | degradado `#07030F` → `#0E0524` → `#1E0A4D` | Fondo oscuro con un resplandor morado hacia abajo |
| `surface` / `surfaceHigh` / `railPanel` | `#120A24` / `#1D1038` / `#0D0620` | Tarjetas, paneles elevados y riel del TV |
| `textPrimary` / `textSecondary` | `#F3E9FF` / `#B9A6D6` | Texto |
| `focus` / `onFocus` | `#E3B5FF` / `#0A0414` | Marcador de foco del TV |
| `border` / `outline` | `#8F2BFF` / `#3A1F66` | Bordes y contornos |
| `favorite` | `#FF3DCB` | Favoritos (magenta) |

Los pares de color cumplen las protecciones de legibilidad de Kino (texto 4,5:1; acento sobre fondo 3:1; fondo oscuro).

## Qué cambia en la app

- **Formas afiladas:** esquinas casi rectas (4–8 dp) y bordes de 1–2 dp en tarjetas, paneles, cabeceras, menús y diálogos.
- **Reproductor:** botones un 10 % más grandes, botón de reproducir 1,3×, barra de progreso 1,3× y botones con esquinas redondeadas.
- **Movimiento:** zoom de foco 1,08, fundido de 280 ms y deriva del héroe activada.
- **Logo propio:** el wordmark **VEGETA** (menú, cabecera del celular, riel abierto del TV) y una marca cuadrada con una «V» y cresta (riel cerrado del TV). Son vectores en capas: sombra profunda, sombra media, morado eléctrico `#BF00FF` y un destello superior. Kino conserva su logo en la pantalla de inicio y en las pantallas de decisión.
- **Colores de otros plugins:** `pluginColors: "respect"`; cada plugin conserva sus propios colores.

## Personalizar (Ajustes ▸ Apariencia ▸ Personalizar)

- Color de acento: tres muestras de morado (`#AA22FF`, `#7C3CFF`, `#9A1EF0`), compatibles con control remoto.
- Redondeo de tarjetas: de 0 a 20.
- Tamaño del texto: de 0,95 a 1,2.
- Fondo: la persona puede cambiarlo.

## Probar antes de publicar

Con el kit de plugins de Kino, desde la carpeta del plugin:

```
node sdk/validate.mjs .
```

Debe pasar sin advertencias en celular ni en TV. Los colores no se pueden ver con el kit: revisa el resultado en Kino, en la vista previa de **Ajustes ▸ Apariencia**.

## Notas

- `icon.png` pesa menos de 128 KB (el máximo que admite el manifiesto) y es cuadrado.
- En el manifiesto, `entry` e `icon` van sin `./` al principio, como pide Kino.
- Fan-made: Vegeta y Dragon Ball son propiedad de sus dueños; este tema no es oficial.
