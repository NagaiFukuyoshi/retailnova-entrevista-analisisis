# 🏢 RetailNova S.A. - Ejercicio Técnico para Data Analyst

## 📋 Descripción del Proyecto
Este repositorio contiene mi solución al ejercicio técnico para la posición de **Data Analyst Jr** en **RetailNova S.A.**, una empresa simulada de retail. El ejercicio fue parte de un sumulacro de entrevista y demuestra mis habilidades en limpieza, transformación y análisis de datos con Python.

## 🎯 Objetivo del Ejercicio
Empresa: RetailNova S.A.
Rol: Data Analyst Jr / Data Analyst Semi-Jr
Equipo: Analytics & BI

Evaluar tu capacidad para:

- Entender datos sucios
- Tomar decisiones razonables
- Limpiar, transformar y analizar información con pandas
- Justificar tus elecciones

## 🛠️ Tecnologías Utilizadas
- **Python 3** 
- **Pandas** - Limpieza y transformación de datos
- **NumPy** - Operaciones numéricas
- **Matplotlib / Seaborn** - Visualizaciones
- **Jupyter Notebooks** - Análisis interactivo
- **Git / GitHub** - Control de versiones

## 📁 Estructura del Proyecto

```
retailnova-entrevista-analisis/
│
├── 📁 data/
│   ├── raw/
│   │   └── ventas_retailnova.csv
│   └── processed/
│       └── ventas_limpias.csv
│
├── 📁 notebooks/
│   └── Practica_1.ipynb
│
├── 📁 docs/
│   └── justificaciones.md
│
├── 📁 outputs/
│   └── 📁 graficos/
│       ├── compras_por_clientes.png
│       ├── descuento_por_producto.png
│       ├── ventas_por_canal.png
│       ├── ventas_por_categoria.png
│       └── ventas_por_vendedor.png
│
└── README.md
```


## 🔍 Problemas Encontrados y Soluciones Aplicadas

| Problema | Decisión | Justificación |
|----------|----------|---------------|
| Valores nulos en `precio_unitario` | Rellenar con promedio por categoría | Preservar datos sin distorsionar la distribución |
| Fechas en formato texto | Convertir a datetime con `dayfirst=True` | Habilitar análisis temporal con formato estándar |
| Registros duplicados | Eliminar duplicados exactos | Evitar sobreestimación de ventas |
| Valores erróneos en `cliente` y `vendedor` | Reemplazar por "Desconocido" | No inflar segmentaciones futuras |
| Nulos en `cantidad` | Reemplazar por valor mínimo (1) | Valor lógico de venta mínima |
| Nulos en `categoria` | Rellenar con moda | Mantener consistencia en análisis por categoría |

## 📊 Principales Hallazgos

### 1. Ventas duplicadas
- Se encontró **1 venta duplicada** (coincidían todos los datos), posible falla del sistema al generar la factura.

### 2. Desempeño por categoría
- La categoría **Electrónica** fue la más vendida en el segundo cuatrimestre con **$4,075** en ventas, representando el **88.39%** del total.

### 3. Análisis de clientes
- **Juan Pérez** fue el cliente que más compró: **$2,460** (53.36% del total).
- **Carlos Ruiz** y **María López** fueron los clientes con menor aporte (<1% cada uno).

### 4. Desempeño por vendedor
- **Ana** lideró ventas con **$2,780** (60.30% del total).
- **Luis** y **Pedro** no superaron el 10% cada uno.
- **27.66%** de las ventas no tienen vendedor asignado.

### 5. Análisis de productos
- **Laptop** generó mayores ingresos: **$2,400**.
- **Mouse** fue el producto más vendido en unidades: **4 unidades**.

### 6. Canales de venta
- **Online** concentró el **93%** de las ventas.
- **Tienda física** apenas superó el **5%**.
- **1.74%** de ventas no tenían canal asignado.

### 7. Descuentos aplicados
- Descuento promedio: **10%**.
- **Mouses y teclados** no recibieron descuentos.
- **Laptops, monitores y webcams** tuvieron descuentos superiores al promedio (>12%).

## 📈 Visualizaciones

### Ventas por Categoría
![Ventas por Categoría](https://github.com/NagaiFukuyoshi/retailnova-proyecto-analisis/blob/main/outputs/graficos/ventas_por_categoria.png?raw=true)

### Ventas por Canal
![Ventas por Canal](https://github.com/NagaiFukuyoshi/retailnova-proyecto-analisis/blob/main/outputs/graficos/ventas_por_canal.png?raw=true)

### Ventas por Vendedor
![Ventas por Vendedor](https://github.com/NagaiFukuyoshi/retailnova-proyecto-analisis/blob/main/outputs/graficos/ventas_por_vendedor.png?raw=true)

### Compras por Cliente
![Compras por Cliente](https://github.com/NagaiFukuyoshi/retailnova-proyecto-analisis/blob/main/outputs/graficos/compras_por_clientes.png?raw=true)

### Descuento por Producto
![Descuento por Producto](https://github.com/NagaiFukuyoshi/retailnova-proyecto-analisis/blob/main/outputs/graficos/descuento_por_producto.png?raw=true)

## 🚀 Cómo Reproducir el Análisis

### Requisitos previos
- Python 3.8 o superior
- pip (gestor de paquetes)

### Pasos
1. **Clonar el repositorio**
   ```bash
   git clone https://github.com/NagaiFukuyoshi/retailnova-proyecto-analisis.git
   cd retailnova-proyecto-analisis
   
### Instalar dependencias

- bash
pip install pandas numpy matplotlib seaborn jupyter
Ejecutar Jupyter Notebook

- bash
jupyter notebook
Abrir y ejecutar el archivo notebooks/Practica_1.ipynb

### 💡 Decisiones Clave

- Todas las decisiones de limpieza y transformación están documentadas en detalle en docs/justificaciones.md. Las más importantes:

- Manejo de nulos en precios: Se usó el promedio por categoría para no perder información valiosa

- Tratamiento de outliers: Se identificaron pero no eliminaron porque representan ventas reales de alto valor

- Estandarización de fechas: Formato datetime para análisis temporal robusto

- Datos faltantes en categorías: Imputación con moda para mantener consistencia

### 📬 Contacto

- **Nombre:** Kevin Andres Arango

- **LinkedIn:** www.linkedin.com/in/kevin-vasquez-73547a29b

- **GitHub:** https://github.com/NagaiFukuyoshi

- **Correo:** vaskev1116@gmail.com

### 📝 Nota Final
Este proyecto fue desarrollado como parte de un ejercicio técnico de entrevista y forma parte de mi portafolio como aspirante a Data Analyst. Los datos son simulados y no corresponden a ninguna empresa real.