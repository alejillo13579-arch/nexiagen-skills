---
name: evaluar-candidato
description: Genera un informe completo de evaluación de un candidato con fortalezas, debilidades y recomendaciones
---

# Skill: Evaluar Candidato

## Descripción
Este skill genera un informe integral de evaluación de un candidato, combinando análisis de CV, matching de competencias y recomendaciones para el proceso de selección.

## Cuándo usarlo
- Después de completar el análisis y matching.
- Cuando el usuario pide: "Evalúa a este candidato", "Dame un veredicto sobre este candidato".

## Instrucciones
1. Recopila la información de:
   - `analizar_cv` (perfil del candidato)
   - `matching_competencias` (puntaje y brechas)
   - (Opcional) `generar_preguntas_entrevista` (si se usó)
2. Genera un informe estructurado:
   - **Resumen ejecutivo:** ¿El candidato es recomendable? (Sí / No / Condicional)
   - **Puntaje de ajuste:** (0-100%)
   - **Fortalezas:** Top 3 fortalezas.
   - **Debilidades / Brechas:** Top 3 brechas.
   - **Riesgos:** Factores que podrían afectar el desempeño.
   - **Recomendaciones:** Acciones concretas para el equipo de selección.
   - **Veredicto final:** Recomendación de contratación (contratar, considerar, descartar).
3. Incluye siempre una nota: "Esta evaluación es automatizada y debe ser validada por el equipo de selección."

## Parámetros de entrada
- `perfil_candidato` (object): Datos del candidato.
- `puntaje_ajuste` (number): Puntaje del matching.
- `brechas` (array): Lista de brechas identificadas.

## Ejemplo de respuesta
