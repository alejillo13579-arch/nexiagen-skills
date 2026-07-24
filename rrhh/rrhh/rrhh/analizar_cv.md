---
name: analizar-cv
description: Analiza hojas de vida (PDF o texto) y extrae información clave del candidato
---

# Skill: Analizar Hoja de Vida (CV)

## Descripción
Este skill extrae y estructura la información de una hoja de vida (CV) para facilitar su evaluación y comparación con vacantes.

## Cuándo usarlo
- Usuario sube o pega un CV y pide: "Analiza este CV", "Extrae la información de este CV".
- Se activa con archivos PDF o texto plano.

## Instrucciones
1. Recibe el CV (puede ser un texto pegado, un archivo PDF descargado o un enlace a un archivo en la nube).
2. Extrae la siguiente información:
   - **Datos personales:** Nombre completo, correo electrónico, teléfono, ciudad, país.
   - **Experiencia laboral:** Empresas, cargos, fechas, logros clave (máximo 3 por empresa).
   - **Educación:** Títulos, instituciones, años de graduación.
   - **Habilidades técnicas:** Lenguajes de programación, herramientas, certificaciones.
   - **Habilidades blandas:** Liderazgo, comunicación, trabajo en equipo, resolución de problemas.
   - **Idiomas:** Idiomas y niveles (nativo, avanzado, intermedio, básico).
   - **Referencias:** Nombres y contactos (si están disponibles).
3. Si el CV está en PDF, usa la herramienta `httpRequest` para descargarlo y extraer el texto.
4. Si el texto es muy largo, prioriza la información más relevante (experiencia, educación, habilidades).
5. Estructura la información en un formato tabular o de lista para facilitar la lectura.

## Parámetros de entrada
- `cv_texto` (string): Texto del CV o URL del archivo.
- `formato` (string): `"texto"` o `"pdf"`.

## Ejemplo de respuesta
