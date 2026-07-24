---
name: analisis-riesgo
description: Evalúa el nivel de riesgo de ciberseguridad de un dominio o IP basado en múltiples fuentes
---

# Skill: Análisis de Riesgo

## Descripción
Este skill combina los resultados de VirusTotal con un análisis contextual para determinar el nivel de riesgo real de un activo digital.

## Cuándo usarlo
- Después de un escaneo (skill `escaneo_virustotal`).
- Cuando el usuario pide: "Dime si esto es peligroso", "¿Qué nivel de riesgo tiene mi web?".

## Instrucciones
1. Recibe los hallazgos del skill `escaneo_virustotal`.
2. Aplica un modelo de ponderación:
   - **Malicious > 0:** +40 puntos
   - **Suspicious > 2:** +20 puntos
   - **Suspicious 1-2:** +10 puntos
   - **Reputación baja:** +15 puntos
   - **Score base:** 10 puntos
3. Calcula el puntaje final (0-100).
4. Clasifica:
   - **80-100:** 🔴 Critico
   - **60-79:** 🟠 Alto
   - **30-59:** 🟡 Medio
   - **0-29:** 🟢 Bajo
5. Genera un listado de vulnerabilidades probables y una acción inmediata.

## Parámetros de entrada
- `hallazgos` (array): Lista de detecciones de VirusTotal.
- `target` (string): Dominio o IP analizado.

## Ejemplo de respuesta
