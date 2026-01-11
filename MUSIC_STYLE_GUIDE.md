# Guía de la Página Music Style

## 📋 Descripción

La página Music Style permite explorar música por géneros usando una **imagen interactiva con áreas clicables**. Cuando haces clic en una sección de la imagen, se filtra la colección para mostrar solo la música de ese género.

## 🎨 Cómo Funciona

### Diseño de la Imagen

La imagen está dividida en una **cuadrícula de 3x2** (3 columnas, 2 filas) = 6 secciones:

```
┌─────────────┬─────────────┬─────────────┐
│   Urbano y  │   Música    │    Rock     │
│ Electrónica │  Española   │ Alternativo │
├─────────────┼─────────────┼─────────────┤
│    Jazz     │   Banda     │  Synth-pop  │
│             │   Sonora    │             │
└─────────────┴─────────────┴─────────────┘
```

### Áreas Clicables

Cada sección tiene:
- **Top-left (0%, 0%)**: Urbano y Electrónica
- **Top-center (33.33%, 0%)**: Música Española  
- **Top-right (66.66%, 0%)**: Rock Alternativo
- **Bottom-left (0%, 50%)**: Jazz
- **Bottom-center (33.33%, 50%)**: Banda Sonora
- **Bottom-right (66.66%, 50%)**: Synth-pop

## 🖼️ Crear Tu Imagen Personalizada

### Paso 1: Dimensiones Recomendadas
- **Ancho**: 1400px
- **Alto**: 800px
- **Proporción**: 16:9 o similar

### Paso 2: Diseñar la Imagen

Crea una imagen dividida en 6 secciones iguales. Cada sección debe representar visualmente un género musical:

1. **Urbano y Electrónica** (arriba-izquierda)
   - Sugerencias: DJ mixer, luces neón, auriculares, sintetizadores

2. **Música Española** (arriba-centro)
   - Sugerencias: Guitarra flamenca, rosas, abanico, elementos españoles

3. **Rock Alternativo** (arriba-derecha)
   - Sugerencias: Guitarra eléctrica, amplificador, pedales de efectos

4. **Jazz** (abajo-izquierda)
   - Sugerencias: Saxofón, trompeta, ambiente de club de jazz

5. **Banda Sonora** (abajo-centro)
   - Sugerencias: Rollo de película, partitura, batuta de director

6. **Synth-pop** (abajo-derecha)
   - Sugerencias: Sintetizador retro, colores neón años 80

### Paso 3: Guardar la Imagen

Guarda tu imagen como:
```
assets/background.jpeg
```

O si prefieres otro nombre, actualiza la línea 130 en `_layouts/music_style.html`:
```html
<img src="{{ '/assets/TU_IMAGEN.jpg' | relative_url }}" 
```

## 🎯 Personalización Avanzada

### Cambiar el Layout de la Cuadrícula

Si quieres un diseño diferente (por ejemplo, 2x3 o 4x2), edita las clases CSS en `_layouts/music_style.html`:

```css
/* Ejemplo para 2 columnas x 3 filas */
.area-urbano { top: 0; left: 0; width: 50%; height: 33.33%; }
.area-espanola { top: 0; left: 50%; width: 50%; height: 33.33%; }
.area-rock { top: 33.33%; left: 0; width: 50%; height: 33.33%; }
.area-jazz { top: 33.33%; left: 50%; width: 50%; height: 33.33%; }
.area-banda { top: 66.66%; left: 0; width: 50%; height: 33.34%; }
.area-synth { top: 66.66%; left: 50%; width: 50%; height: 33.34%; }
```

### Añadir Más Géneros

1. Añade una nueva área clicable en el HTML:
```html
<div class="genre-area area-NUEVO" onclick="filterByGenre('Nombre del Género')">
    <div class="genre-tooltip">Nombre del Género</div>
</div>
```

2. Define su posición en el CSS:
```css
.area-NUEVO { top: X%; left: Y%; width: W%; height: H%; }
```

### Cambiar Géneros Existentes

Para cambiar qué género representa cada área, simplemente modifica el parámetro en `onclick`:

```html
<div class="genre-area area-urbano" onclick="filterByGenre('TU NUEVO GÉNERO')">
    <div class="genre-tooltip">TU NUEVO GÉNERO</div>
</div>
```

**Importante**: El nombre debe coincidir exactamente con el valor en la columna `genero` de tu archivo CSV.

## 🎨 Efectos Visuales

### Hover Effect
Cuando pasas el mouse sobre una sección:
- Aparece un borde blanco semi-transparente
- Se muestra un tooltip con el nombre del género
- Fondo semi-transparente con efecto blur

### Click Effect
Al hacer clic:
- La sección se ilumina brevemente
- Navega a la vista de filtrado del género

## 📝 Notas Técnicas

- El sistema usa **posicionamiento absoluto** para las áreas clicables
- Las áreas son **responsivas** y se ajustan al tamaño de la imagen
- Los tooltips aparecen con **transición suave**
- Compatible con dispositivos móviles y tablets

## 🚀 Próximos Pasos

1. Crea tu imagen personalizada con las 6 secciones
2. Guárdala en `assets/background.jpeg`
3. Recarga la página `/music_style.html`
4. ¡Prueba haciendo clic en diferentes secciones!

## 💡 Tips de Diseño

- Usa **colores distintivos** para cada sección
- Añade **texto o iconos** en la imagen para identificar géneros
- Mantén un **estilo visual coherente** entre secciones
- Considera usar **gradientes** o **líneas divisorias** entre secciones
- Asegúrate de que la imagen se vea bien en **diferentes tamaños de pantalla**
