---
name: matching-competencias
description: Compara un CV con una descripción de cargo y calcula un puntaje de ajuste
---

# Skill: Matching de Competencias

## Descripción
Este skill compara el perfil de un candidato (extraído de su CV) con los requisitos de una vacante y calcula un **puntaje de ajuste** (0-100%). También identifica fortalezas y brechas.

## Cuándo usarlo
- Después de analizar un CV (skill `analizar_cv`).
- Cuando el usuario pide: "Compara este CV con esta vacante", "¿Qué tan bien encaja este candidato?".

## Instrucciones
1. Recibe:
   - El perfil del candidato (del skill `analizar_cv`).
   - La descripción de la vacante (texto proporcionado por el usuario o URL de Magneto Empleos).
2. Extrae los requisitos clave de la vacante:
   - **Requisitos obligatorios:** Educación mínima, años de experiencia, habilidades técnicas específicas.
   - **Requisitos deseables:** Idiomas, certificaciones, habilidades blandas.
3. Compara el perfil del candidato con cada requisito y asigna un peso:
   - **Requisitos obligatorios:** 60% del puntaje total.
   - **Requisitos deseables:** 40% del puntaje total.
4. Calcula el puntaje de ajuste (0-100%).
5. Identifica:
   - **Fortalezas:** Áreas donde el candidato supera los requisitos.
   - **Brechas:** Áreas donde no cumple los requisitos.
   - **Riesgos:** Posibles problemas (ej. falta de experiencia en una tecnología clave).
6. Genera un informe con el puntaje y recomendaciones.

## Parámetros de entrada
- `perfil_candidato` (object): Datos del candidato (del skill `analizar_cv`).
- `descripcion_vacante` (string): Texto de la vacante o URL de Magneto.

## Escala de puntaje
- **90-100%:** ✅ Excelente ajuste — candidato ideal.
- **70-89%:** ⚠️ Buen ajuste — cumple la mayoría de requisitos.
- **50-69%:** 🟡 Ajuste parcial — cumple algunos requisitos clave.
- **0-49%:** ❌ Ajuste bajo — no cumple requisitos clave.

## Ejemplo de respuesta
