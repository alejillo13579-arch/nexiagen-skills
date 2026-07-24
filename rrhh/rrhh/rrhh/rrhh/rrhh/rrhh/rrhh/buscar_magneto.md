---
name: buscar-magneto
description: Busca y filtra candidatos desde la plataforma Magneto Empleos (Banco Nacional de Talentos)
---

# Skill: Buscar en Magneto Empleos

## Descripción
Este skill permite buscar candidatos en la plataforma **Magneto Empleos** (Banco Nacional de Talentos del gobierno colombiano) utilizando palabras clave, competencias y perfiles.

## Cuándo usarlo
- Cuando el usuario pide: "Busca candidatos en Magneto", "Encuentra talento para esta vacante", "Filtra candidatos de Magneto por competencias".

## Instrucciones
1. Recibe la consulta del usuario (palabras clave, competencias, ubicación, etc.).
2. (Opcional) Conecta a la API de Magneto Empleos si está disponible. Si no, simula la búsqueda usando la información disponible.
3. Filtra los candidatos según:
   - **Palabras clave:** Coincidencia en experiencia, educación o habilidades.
   - **Competencias específicas:** Ej. "Python", "Liderazgo", "SQL".
   - **Ubicación:** Ciudad o departamento.
4. Devuelve una lista de los mejores candidatos (máximo 5) con:
   - Nombre, experiencia clave, habilidades destacadas, puntaje de relevancia.
5. Recomienda contactar a los candidatos con mayor puntaje.

## Parámetros de entrada
- `palabras_clave` (string): Términos de búsqueda.
- `competencias` (array): Lista de competencias requeridas.
- `ubicacion` (string): Ciudad o departamento (opcional).

## Ejemplo de respuesta
