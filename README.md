# Composición frontend de página web Isabelles

**Entrega Móvil y Tablet 01/04/2026**

En el diseño de esta web se ha tratado de organizar y refactorizar siguiendo la filosofía "Clean Code" y buenas prácticas aprendidas en IDB Projects por el jefe de Departamento de Diseño, en el que organizamos un Sistema de Variables jerarquizadas, creación de utilidades, componentes y refactorización de código duplicado.

En esta web se ha garantizado:

- El estándar de accesibilidad AA WCAG.
- Usabilidad sencilla para todos los usuarios.
- Diseño Mobile First
- Diseño Responsive
- La preservación de los valores principales de Figma. Estos se han trasladado y aplicado en el diseño CSS uno a uno.

En esta composición se ha utilizado como herramienta la inteligencia artificial para:

- Para los efectos de CSS más complejos que no encontré otra manera de conseguir (ejemplo uso de clases :placeholder :invalid:not o efecto de cerrar menú desplegable pinchando fuera usando un label extra).
- Para la composición correcta de los formularios con estilos específicos que no conocía (ejemplos: outline, resize, usos correctos de grid, pointer-events...).
- Tratamiento de todo el volumen de información de estilos de figma y encontrar los estilos base para las variables sobre todo en espacios y márgenes.
- Refactorización y organización del código. Encontrar patrones y estilos repetidos y unificarlos.

Todo estos usos me han servido para aprender de su existencia y de como se aplican.

## 1- Medidas, márgenes y spacing

Los espacios, paddings, gap, height, width y demás controles de márgenes y espacios están en píxeles medida fija muchas veces para preservar los datos que da Figma.

Para mi gusto prefiero trabajar con rem y porcentajes, pero para conservar y trasladar al pie de la letra lo que se compuso, mantuve las medidas en px.

Si es preciso por legibilidad, mantenimiento o por buenas prácticas manejar los espacios de otra manera, lo haré como me indiques así en la próxima entrega.

## 2- Accesibilidad y usabilidad

El diseño original en Figma no permitía toda la accesibilidad y usabilidad que necesitaba y deseaba, por ello los botones estáticos de formularios y navegación web que aparecían haciendo scroll hasta abajo del todo, los mejoré para diseño móvil y tablet usándolos como un nav flotante y fixed.

## 3- Menú desplegable

El menú de idiomas cuando se agregue javascript, será dinámico. Al estar el input dentro de otro input, no podía conseguir el efecto de que se desplegara uno dentro de otro.

## 4- Web

Para conseguir dar realismo y trasladar de la manera más fiel posible esta composición web. Se deplegó la web para ver los efectos reales desde navegadores móviles y de escritorio a través del dominio https://isabelles.duckdns.org/index.html .
