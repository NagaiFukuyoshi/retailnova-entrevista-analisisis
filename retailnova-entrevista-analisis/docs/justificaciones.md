# 🧠 Justificaciones Técnicas - Ejercicio RetailNova S.A

## 📋 Resumen ejecutivo de decisiones

| Problema | Decisión | Justificación breve |
|----------|----------|---------------------|
| Valores nulos en `precio_unitario` | Rellenar con el promedio por categoría | Preservar datos sin distorsionar la distribución |
| Fechas en formato texto | Convertir a datetime con `dayfirst=True` | Habilitar análisis temporal con formato estándar |
| Registros duplicados | Eliminar duplicados exactos | Evitar sobreestimación de ventas |
| Valores erroneos en `clientes` y `vendedor` | Se reemplazo por Desconocido | Se usó Desconocido para no inflar futuros calculos si se segmentan por clientes y/o vendedor |
| Nulos en `cantidad` | Se reemplazo por la cantidad minima de venta (1) | Se opto por reemplazar los NaN por 1 para evitar posibles inflaciones en resultados futuros |
| Nulos en `categoria` | Se usó la moda para obtener la categoria que mas se repetia | Se usó la moda para obtener la categoria que mas se repetia |

---

## 🔍 Detalle de cada decisión técnica

### 1. Valores nulos en `precio_unitario`

**Cantidad:** 1 registros (10% del total)

**Decisión:** Rellenar con el **promedio** agrupada por categoría de producto.

**Código:**
```python
df_ventas["precio_unitario"] = df_ventas["precio_unitario"].fillna(df_ventas.groupby("categoria")["precio_unitario"].transform("mean"))
```

---

### 2. Fechas en formato texto

**Cantidad:** 10 registros (100% del total)

**Decisión:** Convertir a datetime con `dayfirst=True`

**Código:**
```python
df_ventas["fecha"] = pd.to_datetime(
    df_ventas["fecha"],
    errors="coerce",
    dayfirst=True
)
df_ventas["fecha"] = df_ventas["fecha"].fillna(method="ffill")
```

---

### 3. Registros duplicados

**Cantidad:** 1 registros (10% del total)

**Decisión:** Eliminar duplicados exactos

**Código:**
```python
df_ventas = df_ventas.drop_duplicates()
```

---

### 4. Valores erroneos en `clientes` y `vendedor`

**Cantidad:** 1 registros (10% del total)

**Decisión:** Se reemplazo los valores erroneos por `Desconocido`

**Código:**
```python
def rellenar_desconocido (columnas):
    for columna in columnas:
        df_ventas[columna] = df_ventas[columna].fillna("Desconocido")

rellenar_desconocido(["canal","vendedor"])
```

---

### 5. Nulos en `cantidad`

**Cantidad:** 1 registros (10% del total)

**Decisión:** Se reemplazo por la cantidad minima de venta (1)

**Código:**
```python
df_ventas["cantidad"] = df_ventas["cantidad"].fillna(1).astype(int)
```

---

### 6. Nulos en `categoria`

**Cantidad:** 1 registros (10% del total)

**Decisión:** Se usó la moda para obtener la categoria que mas se repetia

**Código:**
```python
df_ventas["categoria"] = df_ventas["categoria"].fillna(df_ventas["categoria"].mode()[0])
```