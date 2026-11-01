# Sitio web IK Developers

Landing page de la empresa de desarrollo de software **IK Developers**, construida con HTML y CSS a partir de una muestra en Figma. Deber grupal de Aplicaciones Web.

- **Página publicada:** `<URL de GitHub Pages>`

## Estructura de directorios y archivos

```text
ikdevelopers/
├── index.html        
├── css/
│   ├── base.css      # Variables, reset y componentes compartidos
│   ├── header.css    # Barra superior: logo, menú de navegación y botón "Contact us"
│   ├── hero.css      # Sección principal: título, mensaje, botón e imagen
│   ├── clientes.css  # Testimonios: cita, flechas y lista de personas con estrellas
│   ├── enfoque.css   # "Our design and development approach": 6 tarjetas con ícono
│   ├── recursos.css  # "Featured Resources": 4 tarjetas con imagen y enlace
│   └── footer.css    # Pie de página: columnas de enlaces, contacto, redes y copyright
├── img/              
├── README.md
└── .gitignore
```

## Función de cada archivo

- **index.html:** contiene toda la página. Usa `<header>` (con el `<nav>` adentro), `<main>` con las cuatro `<section>` y `<footer>`. Cada sección está delimitada por comentarios de inicio y fin con el integrante responsable; cada uno escribe solo dentro de su bloque.
- **base.css:** se carga antes que los demás CSS. Define las variables de diseño sacadas de Figma, el reset que iguala los estilos por defecto de Chrome y Firefox, y los componentes que usan varias secciones (`.container`, `.titulo-seccion`, `.btn`). No se modifica sin avisar al grupo.
- **header.css, hero.css, clientes.css, enfoque.css, recursos.css, footer.css:** estilos de una sola sección cada uno. Solo contienen clases con el prefijo de su sección.
- **img/:** recursos gráficos propios (logo e íconos). Las fotografías no se guardan aquí: se enlazan desde picsum.photos.

## División del trabajo

| Integrante | Sección | Archivos CSS | Rama |
| --- | --- | --- | --- |
| Bryan Ayala | Header y hero | `header.css`, `hero.css` | `feature/header-hero` |
| Lenin Jeréz | Clientes (testimonios) | `clientes.css` | `feature/clientes` |
| Juan Chugá | Enfoque (6 tarjetas) | `enfoque.css` | `feature/enfoque` |
| Recursos y Footer | Recursos y footer | `recursos.css`, `footer.css` | `feature/recursos-footer` |

## Variables de diseño

Todas las secciones usan **estas variables de `base.css`** en lugar de escribir colores o tamaños sueltos. Así la página mantiene los mismos valores de Figma en todas partes.

### Colores

| Variable | Valor | Uso |
| --- | --- | --- |
| `--color-marca-1` | `#57007B` | Morado de la marca |
| `--color-boton-azul` | `#3D63EA` | Botón "Let's get started!" |
| `--degradado-product` | degradado rosa | Palabra "Product" del hero |
| `--degradado-teams` | degradado rojo → azul | Palabra "teams" del hero |
| `--degradado-boton` | degradado azul → morado | Botón "Contact us" |
| `--color-texto-titulos` | `#1A202C` | Títulos (`h1`, `h2`, `h3`) |
| `--color-texto-recursos` | `#2D3748` | Títulos de las tarjetas de recursos |
| `--color-texto-footer` | `#4A5568` | Textos del footer |
| `--color-texto-gris` | `#718096` | Texto general de la página |
| `--borde-tarjetas` | `1px solid #E7DAED` | Borde de las tarjetas |
| `--color-fondo-1` | `#FFF` | Fondo blanco y texto de los botones |
| `--color-fondo-2` | `#F7F7FA` | Fondo gris de secciones |

### Tipografía

| Variable | Valor | Uso |
| --- | --- | --- |
| `--texto-fuente-principal` | Inter | Fuente de toda la página |
| `--texto-fuente-secundaria` | Poppins | Fuente secundaria |
| `--texto-sm` / `--texto-base` / `--texto-md` / `--texto-lg` | 14 / 16 / 18 / 20 px | Tamaños de texto |
| `--titulo-nav` | 24 px | Logo del menú |
| `--titulo-seccion` | 35 px | Títulos de sección |
| `--titulo-hero` | 45 px | Título del hero |
| `--texto-peso-fino` / `normal` / `medio` / `negrita` | 300 / 400 / 600 / 700 | Pesos de letra |
| `--texto-interlineado-normal` | 1.57 | Interlineado general (sin unidades) |
| `--texto-interlineado-largo` | 2 | Párrafos largos (hero y testimonio) |

Las dos fuentes se cargan desde Google Fonts en el `<head>` de `index.html`.

### Bordes, sombras y layout

| Variable | Valor | Uso |
| --- | --- | --- |
| `--radio-boton` | 5 px | Esquinas de los botones |
| `--radio-imagen` | 10 px | Esquinas de imágenes e íconos |
| `--radio-circulo` | 50 % | Fotos de testimonios e íconos de redes |
| `--sombra-sm` / `--sombra-md` / `--sombra-lg` | 30 / 40 / 49 px de difuminado, 5 / 10 / 15 % de opacidad | Sombras de Figma, de menor a mayor intensidad |
| `--ancho-contenedor` | 1190 px | Ancho máximo del contenido; cada sección lo ajusta si en Figma es distinto |

## Componentes compartidos

Definidos en `base.css` y usados por varias secciones:

```html
<!-- Contenedor centrado: todo el contenido de cada sección va dentro -->
<div class="container"> ... </div>

<!-- Título de sección de dos líneas (clientes, enfoque y recursos) -->
<h2 class="titulo-seccion">
  <span class="titulo-seccion__fina">Our design and</span>
  <span class="titulo-seccion__gruesa">development approach</span>
</h2>

<!-- Botones -->
<a href="#" class="btn btn--morado">Contact us</a>
<a href="#" class="btn btn--azul">Let's get started!</a>
```

## Convenciones

1. **Nombres de clases (BEM):** cada clase lleva el prefijo de su sección. `__` marca una parte de la sección y `--` una variante. Ejemplos: `.enfoque__tarjeta`, `.recursos__titulo`, `.clientes__persona--activa`.
2. **Sin selectores genéricos** en los CSS de sección (`h3 { }`, `img { }`), porque afectarían a toda la página.
3. **Unidades:** `rem` para textos, espacios y radios (`rem = px ÷ 16`). `px` solo para bordes de 1 px, sombras y el ancho del contenedor.
4. **Espaciados:** los `margin`, `padding` y `gap` se escriben exactos en el CSS de cada sección, con el valor de Figma en un comentario. Ejemplo: `margin-bottom: 1.4375rem; /* 23px */`.
5. **Layout:** Flexbox para filas (header, hero) y Grid para cuadrículas (enfoque y recursos). No se usa `position: absolute` para ubicar bloques.
6. **HTML semántico:** un solo `<h1>` (hero), `<h2>` para títulos de sección, `<h3>` para títulos de tarjetas, `<article>` para cada tarjeta y `alt` en todas las imágenes.
7. **Sin estilos en línea** (`style="..."`) ni etiquetas `<style>` en el HTML.