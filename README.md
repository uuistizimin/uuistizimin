# UUIS Tizimín — Sitio estático

Este repositorio contiene la versión estática del sitio web de la Unidad Universitaria de Inserción Social (UUIS) Tizimín. El objetivo de este README es describir las partes principales de la página y cómo probarla o mantenerla localmente.

## Estructura importante

- `index.html` — Página principal con todas las secciones (header, hero, servicios, nosotros, eventos, footer).
- `img/` — Imágenes utilizadas en las tarjetas; la página usa placeholders si faltan archivos.
- `js/` — contiene el `package.json` (si se quiere añadir herramientas de desarrollo) y scripts relacionados.

## Partes de la página (descripción)

- Header: Logos (`img/logo_uady.svg`, `img/LogoUUIS.jpg`), navegación (Inicio, Servicios, Nosotros, Contacto) y menú móvil (función `toggleMobileMenu()` en `index.html`).
- Hero: Bloque de introducción con título, descripción y botón hacia `#servicios`.
- Servicios (`#servicios`): Grid responsivo (1–3 columnas según ancho). Cada tarjeta representa un servicio o grupo de servicios:
	- Consulta médica — incluye atención prenatal, planificación familiar, sutura menor, extracción de cuerpos extraños, atención a personas con diabetes e hipertensión, visitas domiciliarias.
	- Consultorio de odontología — consulta, extracciones, limpieza y aplicación de resina.
	- Estimulación temprana / prenatal — capacitaciones a cuidadores y embarazadas.
	- Cuidados de enfermería — lista detallada de servicios (inyecciones, instalación de IV, curación de heridas, glicemia/glucometría, medición de tensión arterial, vendajes, cuantificación de colesterol/triglicéridos, entre otros).
	- Visita domiciliaria — atención integral en domicilio.
	- Proyectos comunitarios — lista de proyectos: "Cuidando a mi familia", "UUIS en tu colonia", "Salud responsable" y "Estimulación temprana / prenatal".
- Nosotros (`#nosotros`): Misión y visión.
- Próximos Eventos: Tarjetas con eventos, fechas y enlaces de acción.
- Footer / Contacto (`#contacto`): Teléfono, enlaces a redes sociales (Facebook: `https://www.facebook.com/UUISTizimin`, Instagram: `https://www.instagram.com/UUISTizimin`), horario, ubicación y mapa embebido.

## Convenciones y notas de mantenimiento

- Tailwind se carga desde CDN (`https://cdn.tailwindcss.com`) y las fuentes desde Google Fonts — por ello no hay paso de build necesario para ver la página.
- Mantén las rutas de imagen en `img/` con los mismos nombres si quieres que las tarjetas muestren fotos reales. Si no existen, la página utiliza el `placeholder.svg`.
- Las clases de Tailwind y la jerarquía HTML están diseñadas para ser sencillas de editar: cada tarjeta de servicio está encapsulada en un `div` con clases de Tailwind.

## Cómo probar localmente

1) Abrir `index.html` directamente en el navegador (doble clic) funciona para ver la mayoría del contenido.
2) Si quieres servirlo con un servidor local (recomendado para evitar restricciones de iframes u otras políticas), en PowerShell puedes ejecutar:

```powershell
# desde la raíz del repo (donde está index.html)
python -m http.server 8000
# luego abrir http://localhost:8000 en el navegador
```

3) Si prefieres usar Node (si añades herramientas): instala dependencias en `js/` y configura un servidor estático.

## Cambios recientes relevantes

- Se actualizaron los enlaces a redes sociales en el footer (Facebook e Instagram apuntan a los perfiles oficiales de UUISTizimin).
- Se añadió la tarjeta de "Proyectos comunitarios" dentro de la sección `#servicios` y se desglosaron los servicios clínicos según la lista proporcionada.

## Siguientes pasos útiles

- Subir imágenes reales en `img/` usando los mismos nombres referenciados en `index.html` para reemplazar los placeholders.
- Si quieres internacionalizar el sitio, extraer textos a un JSON y agregar un pequeño script para cambiar idioma.

Si quieres que el README incluya instrucciones de despliegue concretas (GitHub Pages, Netlify, etc.) o que genere thumbnails de las imágenes automáticamente, dímelo y lo añado.
