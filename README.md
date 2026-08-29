# El Convite de Sangre Fría — Oneshot

Landing + fichas de personaje para una sesión única de D&D 5e. Sitio 100% estático (HTML/CSS puro, sin build ni dependencias), listo para GitHub Pages, Netlify o Cloudflare Pages.

## Estructura

```
├── index.html                    → landing (tablón con las 5 fichas)
├── style.css                     → estilos compartidos (paleta, tipografías, componentes)
├── assets/
│   └── pj1.svg … pj5.svg         → retratos placeholder (reemplazar por fotos reales)
└── personajes/
    ├── personaje-1.html          → ficha sin conjuros (marcial)
    ├── personaje-2.html          → ficha con sección "Conjuros" (lanzador)
    ├── personaje-3.html
    ├── personaje-4.html
    └── personaje-5.html
```

## Editar contenido

1. Abrí `index.html` y completá el gancho de la oneshot (sistema, duración, nivel, fecha) y el nombre/clase de cada personaje en las tarjetas del tablón.
2. Abrí cada archivo en `personajes/` y reemplazá todo lo marcado como `EDITAR` o `Nombre del PJ N`: características, salvaciones, habilidades, trasfondo (rasgo/ideal/vínculo/defecto), equipo y rasgos de clase.
3. Si un personaje lanza conjuros, copiá la sección `<section class="sheet-panel"><h2>Conjuros</h2>…` de `personaje-2.html` a su ficha.
4. Borrá el aviso `<p class="placeholder-note">…</p>` de cada ficha una vez completada.

## Reemplazar los retratos

Cada personaje usa una sola imagen, referenciada como `assets/pjN.png` tanto en la tarjeta del tablón (`index.html`) como en el encabezado de su ficha (`personajes/personaje-N.html`) — subí un solo archivo por personaje y se actualiza en los dos lugares.

- **Formato:** PNG (también sirve JPG, solo cambiá la extensión en el `src` de ambos archivos).
- **Dimensiones:** cuadrado, recomendado **500×500px o más** (mínimo 300×300px). Se recorta automáticamente en círculo, así que centrá la cara/el sujeto en el medio de la imagen.
- Los `.svg` que vienen en `assets/` son siluetas de referencia — podés borrarlos una vez que subas las fotos reales.

## El mapa

Hay una página propia para el mapa: `mapa.html`, enlazada desde el botón "🗺 Ver el mapa" en la landing.

- La imagen se referencia como `assets/map.png` (ajustá el nombre/extensión en el `<img>` de `mapa.html` si tu archivo se llama distinto, por ejemplo `.jpg`).
- No hay una medida obligatoria: la imagen ocupa el ancho del contenedor (hasta ~1080px) y se ajusta sola en alto. Cuanto más grande y nítida la subas, mejor se ve al hacer zoom.
- Editá o borrá el texto "EDITAR — pie de foto o leyenda del mapa" debajo de la imagen, según necesites.
- Está pensado para más adelante sumar un menú lateral que permita ver el mapa junto con la ficha de un personaje seleccionado — por ahora es una página simple con solo el mapa.

## Desplegar en GitHub Pages

```bash
git init
git add .
git commit -m "Sitio de la oneshot"
git branch -M main
git remote add origin <URL_DE_TU_REPO>
git push -u origin main
```

Después, en el repo de GitHub: **Settings → Pages → Source: `main` / carpeta raíz (`/`)**. El sitio queda publicado en `https://<usuario>.github.io/<repo>/`.

## Personalización rápida

Los colores, tipografías y componentes están centralizados como variables CSS al inicio de `style.css` (bloque `:root`), así que podés cambiar la paleta entera editando esos valores.
