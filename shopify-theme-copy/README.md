# LostGenClub Theme - Replica Personalizable

Un tema de Shopify completo basado en [lostgenclub.com](https://mx.lostgenclub.com/), diseñado para ser fácilmente personalizable.

## 📋 Características

- ✅ **Página de inicio completa** con hero, productos destacados, colecciones, testimonios
- ✅ **Páginas de producto** con galería, variantes, y botón de WhatsApp
- ✅ **Páginas de colección** con filtros y paginación
- ✅ **Carrito de compras** con checkout por WhatsApp y tradicional
- ✅ **Páginas informativas**: Nosotros, Contacto, FAQ
- ✅ **Shell de configuración** en el admin de Shopify
- ✅ **Variables CSS** para colores de marca fácilmente editables
- ✅ **JavaScript modular** para funcionalidad interactiva

## 🎨 Personalización Rápida

### 1. Colores de Marca
Edita `config/settings_schema.json`:
```json
{
  "id": "primary_color",
  "default": "#d4af37"  // ← Cambia aquí tu color primario
}
```

### 2. Información de Contacto
En `config/settings_data.json`:
```json
{
  "whatsapp_number": "5215512345678",  // ← Tu número
  "email": "info@lostgenclub.com",     // ← Tu email
  "free_shipping_threshold": 1800      // ← Monto envío gratis
}
```

### 3. Contenido del Hero
En `templates/index.liquid`:
```liquid
{%- assign hero_config = hash |
  | assign_key: 'title', 'Tu Título Aquí' |
  | assign_key: 'subtitle', 'Tu subtítulo aquí' |
  | assign_key: 'cta_text', 'Ver Productos' |
-%}
```

### 4. Productos
Los productos se cargan automáticamente desde tu admin de Shopify. Solo necesitas:
1. Crear productos en el admin
2. Asignarlos a colecciones
3. El tema los mostrará automáticamente

## 🛠️ Instalación

1. **Copia los archivos** a tu directorio de tema de Shopify:
   ```
   shopify-theme-copy/
   ├── assets/
   │   ├── main.css.liquid
   │   └── theme.js.liquid
   ├── config/
   │   ├── settings_schema.json
   │   └── settings_data.json
   ├── layout/
   │   └── theme.liquid
   ├── snippets/
   │   └── meta.liquid
   ├── templates/
   │   ├── index.liquid
   │   ├── product.liquid
   │   ├── collection.liquid
   │   ├── cart.liquid
   │   ├── page.about.liquid
   │   └── page.contact.liquid
   └── README.md
   ```

2. **Sube a Shopify**:
   ```bash
   shopify theme push
   ```

3. **Personaliza en el admin**:
   - Ve a Online Store → Themes → Customize
   - Ajusta colores, textos, y productos

## 📁 Estructura de Archivos

| Archivo | Propósito |
|---------|-----------|
| `layout/theme.liquid` | Estructura HTML base, header, footer, navbar |
| `templates/index.liquid` | Página de inicio con todas las secciones |
| `templates/product.liquid` | Página de detalle de producto |
| `templates/collection.liquid` | Listado de productos por colección |
| `templates/cart.liquid` | Carrito de compras y checkout |
| `templates/page.about.liquid` | Página "Nosotros" |
| `templates/page.contact.liquid` | Página de contacto y FAQ |
| `snippets/meta.liquid` | Configuración centralizada de la marca |
| `assets/main.css.liquid` | Todos los estilos CSS |
| `assets/theme.js.liquid` | JavaScript para interactividad |
| `config/settings_schema.json` | Esquema de configuración del admin |
| `config/settings_data.json` | Valores por defecto |

## 🔧 Variables de Configuración

### En `meta.liquid`:
```liquid
brand_name: "LostGenClub"           # Nombre de tu marca
brand_tagline: "Jewelry That Lasts" # Eslogan
primary_color: "#d4af37"            # Color principal (dorado)
whatsapp_number: "5215512345678"    # Número de WhatsApp
free_shipping_threshold: 1800       # Envío gratis en MXN
```

### En `theme.js.liquid`:
```javascript
const shopifyConfig = {
    whatsappNumber: "5215512345678",
    email: "info@lostgenclub.com",
    freeShippingThreshold: 1800,
    shippingDays: "4-9"
};
```

## 📱 Funcionalidad de WhatsApp

El checkout por WhatsApp está integrado automáticamente:
- **Botón flotante** en todas las páginas
- **Botón "Comprar por WhatsApp"** en productos
- **Resumen de orden** en el carrito con texto pre-llenado

El texto generado incluye:
- Lista de productos
- Cantidades
- Total
- Enlace directo para completar la compra

## 🎯 Próximos Pasos

1. **Agrega tu logo** en `config/settings_schema.json`
2. **Configura tu email** de newsletter
3. **Personaliza el hero** con tu mensaje
4. **Sube tus productos** al admin
5. **Prueba en preview** antes de publicar

## 📝 Notas

- Este tema usa Bootstrap 5.3 para el grid system
- Font Awesome 6 para iconos
- Fuentes: Cinzel (títulos), Inter (texto), Playfair Display (testimonios)
- Compatible con Shopify 2.0

---

**Creado con ❤️ para replicar lostgenclub.com de forma personalizable**
