# Composición frontend de página web Isabelles

**Entrega Móvil y Tablet 01/04/2026**

En el diseño de esta web se ha tratado de organizar y refactorizar siguiendo la filosofía "Clean Code" y buenas prácticas aprendidas en IDB Projects por el jefe de Departamento de Diseño, en el que organizamos un Sistema de Variables jerarquizadas, creación de utilidades, componentes y refactorización de código duplicado.

El diseño de esta web es una migración fiel, dato a dato, del prototipo generado en Figma :

https://www.figma.com/proto/1Ma1hDGLYtjW2dEPHNAcVO/Isabelle%C2%B4s-Proyecto-Final?node-id=0-1&t=EX9OuH3rrgw1CJOc-1

En el directorio 'assets' de este proyecto se puede encontrar toda la documentación, guía de estilos, imágenes, iconos y thumbnails usados en la web. Además de la fuente bibliográfica en el nombre.

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

**Entrega Escritorio + Javascript Mayo 2026**

### CSS Escritorio `@media (min-width: 1024px)`
- Header móvil oculto, se activa `#nav-desktop`
- Nav centrado con `position: absolute + translateX(-50%)` para centrado perfecto
- Hover de enlaces mejorado respecto a Figma con `border-bottom` rosa
- Menú idiomas desktop con checkbox oculto y CSS puro, en columna por accesibilidad
- Tipografía escalada en secciones principales, contacto y catálogo
- BottomNav mantenido en escritorio a `300px` por usabilidad

### HTML añadido
- Bloque `#nav-desktop` en `index.html` con logo, enlaces, dropdown idioma y botón reservar
- Banner `#aviso-estudio` con mensaje bilingüe de proyecto académico y botón para cerrarlo
- Script menú idiomas móvil al final del `<body>`

### CSS corregido
- `#menu-idioma` refactorizado: eliminados `::before` y `::after`, ahora controlado por JS
- Selector `.catalogPage` con flex mantenido específico para páginas de reservas con `body:is(...)` para no romper otras páginas
- `.calSemana` y `.calGrid` cambiados de ancho fijo `297px` a `width: 100%` para responsive móvil

### Javascript
- **Menú idiomas móvil**: botón creado con JS, muestra/oculta lista con flecha animada
- **Flujo reservas con `localStorage`**:
  - Paso 1: guarda servicio seleccionado
  - Paso 2: guarda día y hora
  - Paso 3: valida campos y guarda nombre, email, teléfono y mensaje
  - Paso 4: lee localStorage y pinta el resumen dinámicamente
- Botón "Confirmar" cambiado a `type="button"` y eliminado `action/method` del form para evitar submit nativo
- Validación con clase `.error` controlada desde JS en lugar de `:user-invalid` CSS
- Resumen paso 4 ampliado con fila separada para teléfono y email

## 5- Webgrafía

Los bancos de imágenes que más me han servido has sido unplash y pexels. Y las palabras a usar para encontrarlas has sido:
Spa, beauty, skincare, makeup.

| Nombre nuevo                                                     | Origen o URL                                                                                                                                                                                                                      |
| ---------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `bienvenida-mujer-piscina-infinita.webp`                         | `FOTODE~4.WEBP` - unplash.com                                                                                                                                                                                                     |
| `servicio-diseno-cejas-con-hilo.webp`                            | `FOD828_1.webp` - origen no indicado en el nombre anterior                                                                                                                                                                        |
| `kaboompics-productos-skincare-bandeja.webp`                     | `www.kaboompics.com-httpswww.pexels.webp` - kaboompics.com / pexels.com                                                                                                                                                           |
| `kaboompics-productos-skincare-bandeja-duplicado.webp`           | `Foto-de-Karolina-Grabowska-www.kaboompics.com-httpswww.pexels.webp` - kaboompics.com / pexels.com                                                                                                                                |
| `pexels-brocha-tratamiento-facial.webp`                          | `Foto-de-Kerim-Eveyik-httpswww.pexels.comes-esfotomujer-pincel-cepillo-cepillar-22589363.webp` - pexels.com                                                                                                                       |
| `pexels-brocha-tratamiento-facial-duplicado.webp`                | `httpswww.pexels.comes-esfotomujer-pincel-cepillo-cepillar-22589363.webp` - pexels.com                                                                                                                                            |
| `pexels-esteticista-aplicando-tratamiento-facial.webp`           | `Foto-de-Ivan-S-httpswww.pexels.comes-esfotomujer-cama-clinica-acostado-5659055.webp` - pexels.com                                                                                                                                |
| `pexels-esteticista-aplicando-tratamiento-facial-duplicado.webp` | `httpswww.pexels.comes-esfotomujer-cama-clinica-acostado-5659055.webp` - pexels.com                                                                                                                                               |
| `pexels-limpieza-facial-clinica.webp`                            | `Foto-de-Anna-Shvets-httpswww.pexels.comes-esfotosano-mujer-profesional-clinica-5069493.webp` - pexels.com                                                                                                                        |
| `pexels-limpieza-facial-clinica-duplicado.webp`                  | `httpswww.pexels.comes-esfotosano-mujer-profesional-clinica-5069493.webp` - pexels.com                                                                                                                                            |
| `pexels-tecnologia-facial-rostro.webp`                           | `Foto-de-Anna-Shvets-httpswww.pexels.comes-esfotomanos-mujer-tecnologia-cara-4586745.webp` - pexels.com                                                                                                                           |
| `pexels-tecnologia-facial-rostro-duplicado.webp`                 | `httpswww.pexels.comes-esfotomanos-mujer-tecnologia-cara-4586745.webp` - pexels.com                                                                                                                                               |
| `unsplash-crema-manos-fondo-rosa.webp`                           | `producto4-unplash-free-license-1.webp` - unsplash.com                                                                                                                                                                            |
| `unsplash-cremas-faciales-bandeja-madera.webp`                   | `section2-unplash-free-license.webp` - unsplash.com                                                                                                                                                                               |
| `unsplash-cremas-faciales-bandeja-madera.jpg`                    | `section2-unplash-free-license.jpg` - unsplash.com                                                                                                                                                                                |
| `unsplash-figurita-ceramica-blanca-marron.webp`                  | `httpsunsplash.comes@enginakyurtutm_source=unsplash&utm_medium=referral&utm_content=creditCopyTextengin akyurta en a href=httpsunsplash.comesfotosfigurita-de-ceramica-blanca-y-marron-ZbzYDboN7fgutm_source.webp` - unsplash.com |
| `unsplash-foto-primer-plano-ojo-rojo-mujer.webp`                 | `httpsunsplash.comes@ernestonormanutm_source=unsplash&utm_medium=referral&utm_content=creditCopyTextErnesto Normana en a href=httpsunsplash.comesfotosfoto-de-primer-plano-del-ojo-rojo-de-una-mujer-R5CX8XD.webp` - unsplash.com |
| `unsplash-foto-vela-de-pilar-blanco.webp`                        | `httpsunsplash.comes@mediamodifierutm_source=unsplash&utm_medium=referral&utm_content=creditCopyTextMediamodifiera en a href=httpsunsplash.comesfotosvela-de-pilar-blanco-en-soporte-de-plata-W7AyAs7azHcutm.webp` - unsplash.com |
| `unsplash-locion-corporal-tela-blanca.webp`                      | `producto2-unplash-free-license.webp` - unsplash.com                                                                                                                                                                              |
| `unsplash-locion-spa-toalla-tulipanes.webp`                      | `section-unplash-free-license.webp` - unsplash.com                                                                                                                                                                                |
| `unsplash-mujer-acostada-posicion-prona.webp`                    | `httpsunsplash.comes@caishan119utm_source=unsplash&utm_medium=referral&utm_content=creditCopyTextalan caishana en a href=httpsunsplash.comesfotosmujer-acostada-con-posicion-prona-cU53ZFBr3lkutm_source=uns.webp` - unsplash.com |
| `unsplash-mujer-haciendose-las-unas-salon.webp`                  | `httpsunsplash.comes@giorgiotrovatoutm_source=unsplash&utm_medium=referral&utm_content=creditCopyTextGiorgio Trovatoa en a href=httpsunsplash.comesfotosuna-mujer-haciendose-las-unas-en-un-salon-de-unas-gb.webp` - unsplash.com |
| `unsplash-mujer-hojas-verdes-cabeza.webp`                        | `httpsunsplash.comes@ebadi__ahmadutm_source=unsplash&utm_medium=referral&utm_content=creditCopyTextAhmad Ebadia en a href=httpsunsplash.comesfotosmujer-con-hojas-verdes-en-la-cabeza-LgLzE5o93JUutm_source=.webp` - unsplash.com |
| `unsplash-persona-reloj-analogico-oro-plata.webp`                | `httpsunsplash.comes@jd_chonutm_source=unsplash&utm_medium=referral&utm_content=creditCopyTextChelson Tamaresa en a href=httpsunsplash.comesfotospersona-que-lleva-reloj-analogico-redondo-de-oro-y-plata-Xl.webp` - unsplash.com |
| `unsplash-rostro-mujer-luz-calida.webp`                          | `servicio-unplash-free-license.webp` - unsplash.com                                                                                                                                                                               |
| `unsplash-serum-manos-fondo-beige.webp`                          | `producto3-unplash-free-license.webp` - unsplash.com                                                                                                                                                                              |
| `unsplash-tratamiento-facial-camilla.webp`                       | `servicio2-unplash-free-license.webp` - unsplash.com                                                                                                                                                                              |
