---
name: reporte-ejecutivo
description: Genera informes ejecutivos de ciberseguridad para gerentes y dueños de PYMEs
---

# Skill: Reporte Ejecutivo

## Descripción
Este skill traduce hallazgos técnicos de ciberseguridad en un lenguaje claro y accionable para tomadores de decisiones no técnicos.

## Cuándo usarlo
- Cuando el usuario pide: "Dame un resumen para mi gerente", "Genera un informe ejecutivo".
- Al final de un análisis completo (escaneo + riesgo + predicción).

## Instrucciones
1. Recopila los resultados de:
   - `escaneo_virustotal` (detecciones)
   - `analisis_riesgo` (puntaje y vulnerabilidades)
   - `prediccion_ataque` (probabilidad y amenazas)
2. Genera un informe estructurado en secciones:
   - **Resumen ejecutivo** (1 párrafo en lenguaje sencillo)
   - **Hallazgos clave** (máximo 5 puntos)
   - **Riesgo actual** (nivel y puntaje)
   - **Recomendaciones** (3-5 acciones prioritarias)
   - **Próximos pasos** (calendario sugerido)
3. Asegura que el informe sea breve, claro y accionable.
4. Incluye una nota: "Este informe es generado automáticamente y debe ser revisado por un experto en ciberseguridad."

## Ejemplo de respuesta
