# Imágenes — Kimi Shop

Coloca las fotos en esta carpeta con los nombres exactos indicados abajo.
La web las carga automáticamente; mientras no exista el archivo muestra un placeholder de texto.

---

## Hero (foto principal de campaña)

| Archivo | Sección |
|---|---|
| `hero-clasico.jpg` | Banner principal — línea Clásico |
| `hero-street.jpg` | Banner principal — línea Kimi Street |

**Tamaño recomendado:** 800 × 1000 px · proporción 4:5 · formato JPG o WebP

---

## Productos — Línea Clásico

| Archivo | Producto | Precio |
|---|---|---|
| `clasico-01.jpg` | Vestido brasilero | S/ 129.00 |
| `clasico-02.jpg` | Conjunto Kimi | S/ 179.00 |
| `clasico-03.jpg` | Vestido drapeado chocolate | S/ 159.00 |
| `clasico-04.jpg` | Top halter blanco | S/ 99.00 |
| `clasico-05.jpg` | Vestido midi beige | S/ 189.00 |
| `clasico-06.jpg` | Conjunto top + falda rosa | S/ 169.00 |
| `clasico-07.jpg` | Top lazo espalda abierta | S/ 109.00 |
| `clasico-08.jpg` | Aretes perla Kimi | S/ 39.00 |

---

## Productos — Línea Kimi Street

| Archivo | Producto | Precio |
|---|---|---|
| `street-01.jpg` | Polera oversize Kimi logo | S/ 139.00 |
| `street-02.jpg` | Conjunto Kimi | S/ 40.00 |
| `street-03.jpg` | Casaca bomber rosa | S/ 219.00 |
| `street-04.jpg` | Polo básico blanco | S/ 89.00 |
| `street-05.jpg` | Jogger gris jaspe | S/ 149.00 |
| `street-06.jpg` | Polera washed negra | S/ 139.00 |
| `street-07.jpg` | Casaca denim Kimi | S/ 229.00 |
| `street-08.jpg` | Polo piqué rosa | S/ 99.00 |

---

## Fotos del pop-up (galería de ángulos)

Cuando un cliente hace clic en una prenda, se abre un pop-up con una **foto principal** y varias **fotos en distintos ángulos**. Cada prenda puede tener varias fotos.

### Cómo nombrar las fotos de ángulos

Usa el **mismo nombre del producto** y agrégale el ángulo al final:

| Ángulo | Cómo se nombra | Ejemplo (Vestido brasilero) |
|---|---|---|
| Frontal (foto principal) | `nombre.jpg` | `clasico-01.jpg` |
| Espalda | `nombre-espalda.jpg` | `clasico-01-espalda.jpg` |
| Lateral | `nombre-lateral.jpg` | `clasico-01-lateral.jpg` |
| Detalle | `nombre-detalle.jpg` | `clasico-01-detalle.jpg` |

> La foto **Frontal** es la misma que ya aparece en la tarjeta del producto. Solo necesitas agregar las fotos extra (espalda, lateral, detalle).

### Pasos para actualizar (3 pasos)

1. **Sube la foto** a esta carpeta `imagenes/` con el nombre del cuadro de arriba.
2. **Abre el archivo `index.html`** y busca el producto (ej: `clasico-01`).
3. Dentro de su bloque `details` → `gallery`, cambia `img:null` por la ruta de tu foto:

   **Antes:**
   ```js
   {img:null, label:"Espalda"},
   ```
   **Después:**
   ```js
   {img:"imagenes/clasico-01-espalda.jpg", label:"Espalda"},
   ```

> 💡 Mientras la foto no exista o esté en `null`, el pop-up muestra el texto *"Foto pendiente"*. No se rompe nada.

### Otros datos del pop-up que puedes editar

Dentro del mismo bloque `details` de cada producto en `index.html` también puedes cambiar:

- `description` → descripción de la prenda
- `colors` → colores disponibles
- `sizes` → tallas disponibles
- `measures` → tabla de medidas (busto, cintura, cadera, largo)
- `modelNote` → referencia de la modelo (ej: "La modelo mide 1.68 m y usa talla S")

> En `index.html` dejé un **ejemplo completo** en el primer producto y una **plantilla comentada** arriba de la lista de productos para que la copies.

---

## Pasarela de pago (QR de Yape y Plin)

Cuando el cliente hace clic en **"Ir al pago"** se abre una ventana con 3 opciones: **Yape**, **Plin** y **Transferencia bancaria**.
Para Yape y Plin se muestra tu **código QR** para que el cliente lo escanee.

### Cómo subir tus QR

| Archivo | Para qué |
|---|---|
| `qr-yape.jpg` | Tu código QR de Yape |
| `qr-plin.jpg` | Tu código QR de Plin |

**Pasos:**

1. Abre tu app de **Yape** → toca tu QR → guárdalo como imagen. Haz lo mismo en **Plin**.
2. **Sube** esas imágenes a esta carpeta `imagenes/` con los nombres del cuadro de arriba.
3. **Abre `index.html`**, busca el bloque `const pago = {` y pon la ruta del QR:

   **Antes:**
   ```js
   yape: { qr: null, titular: "Kimi Shop", numero: "999 999 999" },
   ```
   **Después:**
   ```js
   yape: { qr: "imagenes/qr-yape.jpg", titular: "Kimi Shop", numero: "999 999 999" },
   ```

> 💡 Mientras el QR esté en `null` o el archivo no exista, la ventana muestra *"QR pendiente"*. No se rompe nada.

**Tamaño recomendado del QR:** 500 × 500 px · cuadrado · formato JPG o PNG.

### Otros datos de pago que debes cambiar (en `index.html`, bloque `const pago`)

- `numero` → tu número de Yape / Plin
- `titular` → el nombre que aparece debajo del QR
- `banco`, `cuenta`, `cci` → datos para la transferencia bancaria
- `whatsapp` → tu número con código de país, **sin** `+` ni espacios (ej: `51999999999`). Aquí llega el comprobante del cliente.

---

## Especificaciones técnicas

- **Formato:** JPG o WebP (WebP pesa menos y carga más rápido)
- **Tamaño tarjetas de producto:** 600 × 800 px · proporción 3:4
- **Tamaño hero:** 800 × 1000 px · proporción 4:5
- **Peso máximo recomendado:** 300 KB por imagen
- **Fondo:** blanco o neutro para que encaje con el diseño de la web
