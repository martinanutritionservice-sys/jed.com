# Catálogo JED

Sitio estático del catálogo de filtros JED. Son archivos sueltos: no hay servidor,
ni base de datos, ni nada que instalar. Se abre `index.html` y funciona.

## Qué hay adentro

- `index.html` — el sitio entero: el catálogo, los dos buscadores, el comparador y las fichas.
  Los 88 productos están embebidos en el propio archivo, en un array de JavaScript.
- `images/productos/` — las 41 fotos de producto, recortadas sobre fondo blanco.
- `images/texturas/` — las texturas de marca (chevrones, puntos y rayas) en sus cuatro colores.
- `images/` — los logos y la foto de la banda del pie.
- `vercel.json` — le dice a Vercel que guarde las imágenes en caché un año y el HTML nunca,
  así los cambios se ven al instante y las fotos no se bajan de nuevo cada vez.

## Publicarlo en Vercel

1. Subir esta carpeta a un repositorio de GitHub.
2. En vercel.com → Add New → Project → importar ese repositorio.
3. Framework Preset: **Other**. No hay que tocar build command ni output directory:
   Vercel sirve la carpeta tal cual.
4. Deploy. Queda una dirección `.vercel.app` funcionando.

Desde ahí, cada `git push` publica solo.

## Conectar el dominio

En Vercel: Project → Settings → Domains → Add. Vercel muestra los registros DNS
que hay que cargar en nic.ar. El certificado HTTPS lo emite y lo renueva Vercel solo.

## Cómo se actualiza el catálogo

Los productos no se cargan desde un panel: se regeneran desde la planilla de JED
y se vuelve a escribir el array dentro de `index.html`. Ese paso lo hace Martina.
