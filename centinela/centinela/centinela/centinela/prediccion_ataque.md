---
name: prediccion-ataque
description: Predice la probabilidad de un ataque cibernético basado en patrones históricos y hallazgos actuales
---

# Skill: Predicción de Ataque

## Descripción
Este skill utiliza análisis de patrones y machine learning básico (basado en reglas) para predecir la probabilidad de que un activo digital sea comprometido en el corto plazo.

## Cuándo usarlo
- Después de un análisis de riesgo (skill `analisis_riesgo`).
- Cuando el usuario pregunta: "¿Estoy en peligro?", "¿Me van a atacar?".

## Instrucciones
1. Recibe el puntaje de riesgo del skill `analisis_riesgo`.
2. Aplica reglas predictivas:
   - **Riesgo crítico (80-100):** Probabilidad 85%, tiempo estimado: 24-48 horas.
   - **Riesgo alto (60-79):** Probabilidad 60%, tiempo estimado: 3-5 días.
   - **Riesgo medio (30-59):** Probabilidad 30%, tiempo estimado: 1-2 semanas.
   - **Riesgo bajo (0-29):** Probabilidad 10%, tiempo estimado: 1+ mes.
3. Ajusta la probabilidad según:
   - Si hay detecciones maliciosas recientes (últimos 7 días) → +15%.
   - Si el dominio tiene reputación baja → +10%.
   - Si tiene certificado SSL válido y actualizado → -5%.
4. Genera una lista de amenazas probables según el riesgo:
   - **Crítico:** Ransomware, Data Breach, APT, Phishing Dirigido.
   - **Alto:** Phishing, Fuerza Bruta, SQL Injection, Credential Stuffing.
   - **Medio:** Malware Genérico, Scan Activo, Enumeración DNS.
   - **Bajo:** Bots de Escaneo, Spam Dirigido.
5. Devuelve la predicción con acciones recomendadas.

## Ejemplo de respuesta
