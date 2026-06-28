# 📚 Catálogos de Muebles La Factoría

Sistema de gestión y visualización de catálogos en PDF para La Factoría.

## 📁 Estructura del Proyecto

```
catalogos-factoria/
├── README.md                      (Este archivo)
├── index.html                     (Página pública - ven los clientes)
├── admin.html                     (Panel privado - solo TÚ)
├── css/
│   └── styles.css                 (Estilos compartidos)
├── js/
│   ├── app.js                     (Lógica de página pública)
│   └── admin.js                   (Lógica del panel admin)
├── data/
│   └── catalogos.json             (Base de datos - TÚ EDITAS ESTO)
├── catalogos/                     (Tus PDFs organizados por categoría)
│   ├── Dormitorios/
│   │   ├── catalogo1.pdf
│   │   └── thumb1.jpg
│   ├── Salones/
│   ├── Colonial/
│   ├── Neoclasico/
│   ├── Juveniles/
│   ├── Tapiceria/
│   ├── Descanso/
│   ├── AltaDecoracion/
│   └── Auxiliares/
└── images/                        (Imágenes del sitio)
```

---

## 🚀 Cómo Usar

### 📍 **PÁGINA PÚBLICA (Lo que ven los clientes)**

1. Abre: `https://factoriajose-source.github.io/catalogos-factoria/`
2. Los clientes ven galerías por categoría
3. Pueden descargar PDFs en ventana nueva

### 🔐 **PANEL PRIVADO (Solo para TÍ)**

1. Abre: `https://factoriajose-source.github.io/catalogos-factoria/admin.html`
2. Ingresa contraseña: **`7557`**
3. Ahora puedes:
   - ✅ Mostrar/Ocultar familias (categorías)
   - ✅ Agregar nuevo catálogo
   - ✅ Editar catálogos existentes
   - ✅ Eliminar catálogos
   - ✅ Cambiar orden

---

## 📝 **EDITAR `data/catalogos.json`** (Lo más importante)

Este es el archivo donde defines TUS catálogos y familias.

### **Estructura básica:**

```json
{
  "familias": [
    {
      "id": 1,
      "nombre": "Dormitorios",
      "emoji": "🛏️",
      "activo": true
    }
  ],
  "catalogos": [
    {
      "id": 101,
      "familiaId": 1,
      "nombre": "Dormitorios Clásicos",
      "descripcion": "Colección tradicional de dormitorios",
      "proveedor": "Moycor",
      "pdf": "catalogos/Dormitorios/dormi-clasicos.pdf",
      "imagen": "catalogos/Dormitorios/thumb-dormi-clasicos.jpg",
      "activo": true
    }
  ]
}
```

### **Campos explicados:**

| Campo | Qué es | Ejemplo |
|-------|--------|---------|
| `id` | Número único | `1`, `2`, `3` |
| `nombre` | Nombre visible | "Dormitorios Clásicos" |
| `descripcion` | Texto bajo el nombre | "Colección tradicional..." |
| `proveedor` | De quién es | "Moycor", "Bizzotto" |
| `pdf` | Ruta al PDF | `catalogos/Dormitorios/archivo.pdf` |
| `imagen` | Miniatura/thumb | `catalogos/Dormitorios/thumb.jpg` |
| `activo` | ¿Mostrar? | `true` (sí) o `false` (no) |

---

## 📤 Cómo Subir Cambios a GitHub

### **Opción 1: GitHub Desktop (Más fácil)**
1. Descargar: https://desktop.github.com/
2. Abrir el repo `catalogos-factoria`
3. Cambias los archivos (localmente)
4. GitHub Desktop detecta cambios
5. Botón "Commit" → "Push"

### **Opción 2: Directamente en GitHub.com**
1. Entra en https://github.com/factoriajose-source/catalogos-factoria
2. Abre el archivo que quieres editar
3. Botón ✏️ (lápiz)
4. Edita
5. Abajo: "Commit changes"

---

## 🖼️ Cómo Agregar Catálogos

### **Paso 1: Sube el PDF**
1. En GitHub, abre la carpeta `catalogos/Dormitorios/` (por ejemplo)
2. "Add file" → "Upload files"
3. Arrastra tu PDF

### **Paso 2: Agrega la entrada en `catalogos.json`**
1. Abre `data/catalogos.json`
2. Agrega un nuevo objeto en el array `catalogos`:

```json
{
  "id": 102,
  "familiaId": 1,
  "nombre": "Dormitorios Modernos",
  "descripcion": "Diseños contemporáneos",
  "proveedor": "GNESIS",
  "pdf": "catalogos/Dormitorios/dormi-modernos.pdf",
  "imagen": "catalogos/Dormitorios/thumb-dormi-modernos.jpg",
  "activo": true
}
```

### **Paso 3: Commit**
1. Scroll abajo
2. "Commit changes"
3. **¡LISTO!** En 1-2 minutos aparece en la web

---

## 🎨 Agregar Imagen/Thumbnail

Cada catálogo puede tener una miniatura (JPG o PNG).

**Recomendación:**
- Tamaño: 400x250 píxeles
- Formato: JPG
- Peso: Menos de 500 KB

**Cómo:**
1. Sube la imagen a la carpeta del catálogo
2. En `catalogos.json`, actualiza el campo `imagen`
3. Si NO tiene imagen, deja vacío: `"imagen": ""`

---

## 🔄 Flujo Completo: Agregar un Nuevo Proveedor

**Ejemplo: Quiero agregar catálogos de "Bizzotto"**

1. **En GitHub:**
   - Abre `catalogos/Tapiceria/`
   - Crea carpeta: `Tapiceria/Bizzotto-2024.pdf`
   - Crea carpeta: `Tapiceria/thumb-bizzotto.jpg`

2. **En `catalogos.json`:**
   ```json
   {
     "id": 201,
     "familiaId": 6,
     "nombre": "Bizzotto",
     "descripcion": "Colección premium de tapicería italiana",
     "proveedor": "Bizzotto",
     "pdf": "catalogos/Tapiceria/Bizzotto-2024.pdf",
     "imagen": "catalogos/Tapiceria/thumb-bizzotto.jpg",
     "activo": true
   }
   ```

3. **Commit**

4. **¡LISTO!** En 2 minutos aparece en la web

---

## 🚨 Troubleshooting

### **"La web no se actualiza después de cambiar JSON"**
- GitHub tarda 1-2 minutos
- Recarga la página (Ctrl+Shift+R en Windows)
- Limpia caché: Ctrl+Mayús+Del

### **"El PDF no se descarga"**
- Verifica la ruta en `catalogos.json`
- Usa "/" no "\"
- Ejemplo: `catalogos/Dormitorios/archivo.pdf` ✅

### **"La imagen no se ve"**
- Verifica que la imagen existe
- Usa rutas correctas
- Soporta: JPG, PNG, GIF

---

## 📊 Panel Admin - Funciones

Acceso: `https://factoriajose-source.github.io/catalogos-factoria/admin.html`
Contraseña: **7557**

**Puedes:**
- ✅ Ver todas las familias
- ✅ Activar/Desactivar familias
- ✅ Ver todos los catálogos
- ✅ Activar/Desactivar catálogos
- ✅ Agregar nuevo catálogo (sin editar JSON)
- ✅ Eliminar catálogos
- ✅ Exportar datos (para backup)

---

## 💾 Backup de Datos

En el panel admin, botón "📥 Descargar Backup" descarga todo (JSON) con fecha.

Guarda en tu OneDrive como respaldo.

---

## 🌐 Activar GitHub Pages

(Ya debería estar activado, pero por si acaso)

1. Repo → Settings
2. Left menu → "Pages"
3. Source: "Deploy from a branch"
4. Branch: "main"
5. Folder: "/(root)"
6. Save

**Tu sitio estará en:** `https://factoriajose-source.github.io/catalogos-factoria/`

---

## 📞 Notas

- Los datos se guardan localmente en el navegador (localStorage)
- El panel admin NO toca GitHub directamente (más seguro)
- Para guardar cambios reales, edita `catalogos.json` en GitHub
- Todos los cambios quedan registrados en el historial de GitHub

---

## 🎯 Próximos Pasos

1. ✅ Sube tus PDFs a `catalogos/`
2. ✅ Completa `data/catalogos.json`
3. ✅ Accede a admin.html
4. ✅ Prueba agregar/eliminar catálogos
5. ✅ ¡Comparte con clientes!

---

**Creado por:** Claude + José Ángel López (La Factoría)  
**Última actualización:** Junio 2026
