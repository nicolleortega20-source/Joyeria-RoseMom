# Joyeria-RoseMom
Sitio estático (HTML + CSS, sin backend ni base de datos) para el catálogo de joyería de RoseMom. Muestra los productos organizados por categoría, con la identidad visual de la marca (colores, tipografías e ícono de rosa definidos en el Manual de Identidad Visual).

Sitio en producción: desplegado en Vercel desde la rama main.


Estructura del proyecto

├── index.html          → toda la estructura y contenido de la página
├── css/
│   └── estilos.css     → todos los estilos (colores, tipografías, layout, responsive)
├── img/
│   └── logo.png         → ícono de la rosa (marca), usado en header, hero y footer
└── imagenes/
    ├── aretes/
    ├── collares/
    ├── pulseras/
    ├── anillos/
    ├── conjuntos/
    ├── tobilleras/
    └── religiosos/       → fotos de producto, una carpeta por categoría


Categorías actuales

CategoríaID de secciónPiezasAretes#aretes44Collares#collares21Pulseras#pulseras21Anillos#anillos7Conjuntos#conjuntos16Tobilleras#tobilleras4Artículos religiosos#religiosos5

El número de piezas de cada sección se calcula solo al cargar la página (ver sección de contador más abajo) — no hay que actualizarlo a mano.


Cómo agregar un producto


Copia un bloque <article class="card">...</article> que ya exista dentro de la sección correspondiente (busca <section class="seccion" id="aretes">, por ejemplo).
Pégalo justo antes del </div> que cierra el <div class="grid"> de esa sección.
Edita dentro de la copia:

src de la imagen → ruta a la foto en imagenes/<categoria>/tu-foto.jpg
alt y el texto del <h3> → nombre del producto
<p class="desc"> → descripción corta
<span class="precio"> → precio, formato $XXX MXN



Sube la foto a la carpeta imagenes/<categoria>/ correspondiente.
El contador de piezas de esa sección se actualiza solo, no hay que tocarlo.


Cómo dar de baja un producto


Busca la tarjeta (<article class="card">) del producto en el HTML.
Bórrala completa, desde <article class="card"> hasta su </article> de cierre.
Listo — el contador de esa sección baja solo al recargar la página.



El contador automático de piezas

Cada sección tiene un badge (<span class="conteo">) que muestra cuántas piezas hay. Al final del index.html hay un script que recalcula ese número contando las tarjetas reales que existan en cada sección:

html<script>
document.querySelectorAll('.seccion').forEach(sec => {
  const n = sec.querySelectorAll('.card').length;
  const contador = sec.querySelector('.conteo');
  if (contador) contador.textContent = n + (n === 1 ? ' pieza' : ' piezas');
});
</script>

Gracias a esto, agregar o quitar tarjetas a mano nunca desincroniza el número — siempre se recalcula solo.


Identidad visual (variables CSS)

Todos los colores están centralizados como variables al inicio de estilos.css, así que para ajustar la paleta solo se edita ahí, una sola vez:

css:root{
  --fucsia:#B5235A;         /* color principal / acentos */
  --fucsia-oscuro:#8C1A44;  /* hover, texto fuerte */
  --rosa:#D4527E;           /* acento secundario */
  --rosa-pastel:#FCE8EC;    /* fondos suaves, badges */
  --rosa-pastel-2:#FAECEF;
  --crema:#FDF6F7;          /* fondo general de la página */
  --tinta:#26232B;          /* texto principal / footer */
  --tinta-suave:#4B4650;    /* texto secundario */
}

Tipografías: Cormorant Garamond (títulos, logo) + DM Sans (texto de cuerpo, UI), cargadas desde Google Fonts en el <head>.


Despliegue en Vercel

El proyecto está conectado a GitHub y se despliega automáticamente en cada push a la rama main.

Si haces un cambio y no lo ves reflejado en el sitio:


Revisa en Vercel → pestaña Deployments que el deploy más reciente corresponda a tu último commit.
Si el deploy es correcto pero el navegador sigue mostrando la versión vieja, es caché del navegador/CDN. Para forzarlo, sube la versión del CSS en el <link> del <head>:


html   <link rel="stylesheet" href="css/estilos.css?v=3">

Solo incrementa el número (?v=4, ?v=5, …) cada vez que quieras forzar que se descargue la versión más reciente.
