## Descripción de los Datos

Este directorio contiene el dataset procesado de PISA 2022 para Costa Rica utilizado en el análisis.

### Archivo Principal

**`pisa_2022_costarica.csv`**
- **Fuente**: PISA 2022 - OECD
- **Registros**: 6,113 estudiantes
- **Variables**: 6 (5 predictores + 1 respuesta)
- **Formato**: CSV con codificación UTF-8

---

## Descripción de Variables

| Variable | Nombre Completo | Tipo | Rango/Valores | Descripción |
|----------|-----------------|------|---------------|-------------|
| `mat` | Puntaje Matemáticas | Numérica continua | 0-800 | Puntaje estandarizado (μ=500, σ=100) |
| `pro_an` | Ansiedad Matemática | Numérica continua | 1-4 | Promedio de 6 ítems (AM1-AM6) |
| `pro_cd` | Clima Disciplinario | Numérica continua | 1-4 | Promedio de 6 ítems (CD1-CD6) |
| `pro_bu` | Recepción Bullying | Numérica continua | 1-4 | Promedio de 6 ítems (BU1-BU6) |
| `sex` | Sexo | Categórica | Masculino/Femenino | Sexo del estudiante |
| `pub` | Tipo Institución | Categórica | Privada/Pública | Sector educativo |

---

## Fuente de los Datos

Los datos provienen de la evaluación PISA 2022 realizada por la OECD:

- **Sitio oficial**: https://www.oecd.org/pisa/
- **Base de datos completa**: https://www.oecd.org/pisa/data/2022database/
- **País**: Costa Rica (CRI)
- **Año de evaluación**: 2022

---

## Procesamiento de Datos

### Variables Derivadas

Las variables `pro_an`, `pro_cd` y `pro_bu` fueron creadas mediante:

```r
# Ejemplo de cálculo de promedios
pro_an = rowMeans(cbind(AM1, AM2, AM3, AM4, AM5, AM6), na.rm = TRUE)
pro_cd = rowMeans(cbind(CD1, CD2, CD3, CD4, CD5, CD6), na.rm = TRUE)
pro_bu = rowMeans(cbind(BU1, BU2, BU3, BU4, BU5, BU6), na.rm = TRUE)
```

### Tratamiento de Valores Faltantes

- Se aplicó `na.rm = TRUE` en el cálculo de promedios
- Casos con más del 50% de datos faltantes en ítems fueron excluidos
- La muestra final quedó en 6,113 casos completos

---

## Consideraciones Éticas y de Uso

✅ **Datos Públicos**: Los datos PISA son de acceso público y abierto
✅ **Anonimizados**: No contienen información que permita identificar individuos
✅ **Uso Educativo**: Este dataset es para investigación y fines educativos

---

## Cómo Descargar los Datos Originales

Si deseas trabajar con los datos originales completos de PISA:

1. Visita: https://www.oecd.org/pisa/data/2022database/
2. Descarga el archivo correspondiente a Costa Rica
3. Sigue la documentación de PISA para códigos de variables

---

## Citar los Datos

Si usas estos datos en tu investigación, cita como:

```
OECD (2023), PISA 2022 Database, www.oecd.org/pisa/data/2022database/
```

---

## Contacto

Para preguntas sobre el procesamiento de estos datos específicos:

📧 luisdiego.1703@gmail.com