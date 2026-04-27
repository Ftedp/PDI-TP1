# 📷 PDI - Trabajo Práctico 1
Repositorio correspondiente al **Trabajo Práctico 1** de la materia **Procesamiento Digital de Imágenes I** de la carrera **TUIA - UNR**.
El TP abarca técnicas de ecualización de histograma y procesamiento automatizado de hojas de examen escaneadas.

---

## 📁 Archivos
| Archivo | Descripción |
|--------|-------------|
| `Resolucion_tp1_ecualizacion.py` | Implementación de ecualización de histograma global y local |
| `Resolucion_tp1_examenes.py` | Procesamiento y corrección automática de hojas de examen |
| `Exploracion_tp1_examenes.py` | Exploración y análisis previo de las imágenes de examen |

---

## ⚙️ Requisitos
- Python 3.14.3
- pip

---

## 🚀 Instalación y ejecución

### 1. Clonar el repositorio
```bash
git clone https://github.com/Ftedp/PDI-TP1.git
cd PDI-TP1
```

### 2. Crear el entorno virtual
```bash
python -m venv venv
```

### 3. Activar el entorno virtual

**Windows (PowerShell):**
```powershell
venv\Scripts\Activate.ps1
```

**Linux / macOS:**
```bash
source venv/bin/activate
```

### 4. Instalar las dependencias
```bash
pip install -r requirements.txt
```

### 5. Ejecutar los scripts
```bash
python Resolucion_tp1_ecualizacion.py
python Resolucion_tp1_examenes.py
```

---

## 🗂️ Funcionamiento — Corrección automática de examen

Pipeline de procesamiento para detectar y corregir automáticamente hojas de examen escaneadas, sin OCR ni librerías externas. Solo proyecciones, componentes conectadas y contornos.

### Paso 1 — Cargar y binarizar la imagen
> Umbralización de Otsu para separar tinta del fondo

### Paso 2 — Detectar líneas de la tabla con proyecciones
> Histogramas de filas y columnas sobre la imagen binaria

### Paso 3 — Agrupar detecciones duplicadas con `np.diff`
> Convertir píxeles individuales en segmentos únicos

### Paso 4 — Extraer celdas de la tabla
> Usar las líneas detectadas para recortar cada celda

### Paso 5 — Detectar campos del encabezado automáticamente
> Proyección de filas sobre el encabezado para encontrar segmentos

### Paso 6 — Detectar la letra marcada en cada celda
> Componentes conectadas y jerarquía de contornos (huecos por letra)

### Paso 7 — Validar respuestas y calcular puntaje
> Comparar respuestas detectadas contra la clave correcta

---

## 📦 Dependencias
```
opencv-python
numpy
matplotlib
```
