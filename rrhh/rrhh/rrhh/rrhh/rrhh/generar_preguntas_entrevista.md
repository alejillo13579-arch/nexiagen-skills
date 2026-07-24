---
name: generar-preguntas-entrevista
description: Genera preguntas de entrevista personalizadas basadas en el CV y la vacante
---

# Skill: Generar Preguntas de Entrevista

## Descripción
Este skill crea preguntas de entrevista a medida para un candidato específico, basadas en su CV y la descripción de la vacante.

## Cuándo usarlo
- Después del matching de competencias (skill `matching_competencias`).
- Cuando el usuario pide: "Genera preguntas para esta entrevista", "Prepárame una entrevista para este candidato".

## Instrucciones
1. Recibe:
   - El perfil del candidato (del skill `analizar_cv`).
   - El informe de matching (del skill `matching_competencias`).
   - La descripción de la vacante (si está disponible).
2. Genera preguntas en 3 categorías:
   - **Preguntas técnicas (5):** Para evaluar habilidades específicas de la vacante.
   - **Preguntas de comportamiento (5):** Para evaluar habilidades blandas y experiencia.
   - **Preguntas personalizadas (3):** Basadas en las brechas y fortalezas del candidato.
3. Cada pregunta debe incluir:
   - La pregunta en sí.
   - Lo que se espera escuchar (criterios de evaluación).
   - Sugerencia para profundizar (follow-up).
4. Prioriza preguntas que aborden las **brechas** identificadas en el matching.

## Parámetros de entrada
- `perfil_candidato` (object): Datos del candidato.
- `vacante` (string): Descripción de la vacante.

## Ejemplo de respuesta
