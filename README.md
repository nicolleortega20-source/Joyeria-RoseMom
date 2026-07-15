# RoseMom — Catálogo de Joyería

Sitio web estático desarrollado con **HTML**, **CSS** y **JavaScript** para mostrar el catálogo digital de joyería de **RoseMom**.

El proyecto está orientado a ofrecer una experiencia elegante y responsiva, permitiendo visualizar los productos organizados por categorías sin necesidad de un backend o base de datos.

## Sitio en producción

**Vercel**

https://joyeria-rose-mom.vercel.app

---

# Tecnologías utilizadas

- HTML
- CSS
- JavaScript
- Git
- GitHub
- Vercel

---

## Estructura del proyecto

## Estructura del proyecto

```text
Joyeria-RoseMom/
├── css/
│   └── estilos.css
├── imagenes/
│   ├── Aretes/
│   ├── Collares/
│   ├── Pulseras/
│   ├── Anillos/
│   ├── Conjuntos/
│   ├── Tobilleras/
│   └── Religiosos/
├── img/
│   ├── logo.png
│   └── logo2.png
├── .gitignore
├── README.md
└── index.html
```
---

# Categorías del catálogo

- Aretes
- Collares
- Pulseras
- Anillos
- Conjuntos
- Tobilleras
- Artículos Religiosos

Cada categoría muestra sus productos mediante tarjetas que incluyen:

- Imagen
- Nombre
- Descripción
- Precio

---

# Agregar un nuevo producto

1. Copiar una tarjeta (`<article class="card">`) existente.
2. Pegarla dentro de la categoría correspondiente.
3. Cambiar:
   - Imagen
   - Nombre
   - Descripción
   - Precio
4. Guardar la fotografía dentro de:

```
imagen/Categoria/
```

5. Guardar los cambios.

El contador de productos se actualiza automáticamente.

---

# Eliminar un producto

1. Buscar la tarjeta del producto.
2. Eliminar el bloque completo:

```html
<article class="card">
...
</article>
```

3. Guardar.

El contador se actualizará automáticamente.

---

# Contador automático

El número de productos por categoría se calcula automáticamente mediante JavaScript al cargar la página, por lo que no es necesario modificarlo manualmente.

---

# Diseño Responsive

El sitio está optimizado para:

- Computadoras
- Tablets
- Teléfonos móviles

El menú de navegación se adapta a pantallas pequeñas mediante Media Queries.

---

# Despliegue

El proyecto está conectado a **GitHub** y **Vercel**.

Cada vez que se realiza:

```bash
git add .
git commit -m "Descripción del cambio"
git push
```

Vercel genera automáticamente una nueva versión del sitio.

---

# Clonar el proyecto

```bash
git clone https://github.com/nicolleortega20-source/Joyeria-RoseMom.git
```

---

# Autora

**Nicolle Ortega Moreno**

Proyecto desarrollado para **RoseMom**.
