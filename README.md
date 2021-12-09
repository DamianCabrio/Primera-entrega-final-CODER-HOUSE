# PRIMERA ENTREGA TP FINAL
### DAMIÁN CABRIO  

[Link al sitio en glitch.com](https://crystalline-onyx-apricot.glitch.me)

## Correr el proyecto
Para correr el proyecto localmente iniciar un servicio de nodemon desde la carpeta source.
`cd .\src\` y `nodemon .\app.js`

## Rutas disponibles:

### Productos
- `/api/productos` GET: Devuelve todos los productos.
- `/api/productos/:idProduct` GET: Devuelve un producto según su id. 
- `/api/productos` POST: Recibe y agrega un producto, y lo devuelve con su id asignando (Solo para admins). Campos requeridos: title, price, thubnail (archivo de foto), description, code y stock
- `/api/productos/:idProduct` PUT: Recibe y actualiza un producto según su id (Solo para admins).
- `/api/productos/:idProduct` DELETE: Elimina un producto según su id (Solo para admins).

### Cart
- `/api/carrito` POST: Crea un carrito y lo guarda en el servidor. Campos requeridos: products (array con ids de productos a agregar).
- `/api/carrito/:idCart/productos` POST: Agrega productos a un carrito existente. Campos requeridos: products (array con ids de productos a agregar).
- `/api/carrito/:idCart/productos` GET: Obtiene los datos de un carrito específico por ID.
- `/api/carrito/:idCart` DELETE: Vacia y elimina un carrito del servidor.
- `/api/carrito/:idCart/productos/:idProduct` DELETE: Elimina un producto específico de un carrito en particular.

### Login
- `/login` POST: Inicia sesión como administrador (por ahora solo cambia un booleano de forma temporal), y redirecciona al index.
- `/logout` GET: Cierra Sesión como administrador.

### Vistas
- `/`: Index, muestra los productos disponibles, permite ir a carrito, iniciar sesión, agregar un producto al carrito, y si somos administradores editar o eliminar un producto.
- `/agregar.html`: Formulario para agregar un producto de un producto (Solo para admins).
- `/edit.html?id=:idProduct`: Formulario de edición de un producto (Solo para admins).
- `/carrito.html`: Muestra los productos agregados a un carrito (si existen) y te permite vaciar el carrito completo, o eliminar un producto en particular de el.

**NOTA:** Se utilizó handlebars para trabajar el frontend, pero este fue trabajado desde el lado del cliente, no se generan las vistas en el servidor. Todos los datos se obtienen con fetch y awaits.
