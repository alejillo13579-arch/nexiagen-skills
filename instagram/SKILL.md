---
name: publicar-instagram
description: Publica un video en Instagram Business
---

# Skill: Publicar en Instagram

## Instrucciones
1. Recibe `video_url`, `titulo`, `descripcion`.
2. Crea contenedor: POST a `https://graph.facebook.com/v18.0/{$vars.INSTAGRAM_BUSINESS_ID}/media` con `media_type=VIDEO`, `video_url`, `caption`.
3. Publica: POST a `https://graph.facebook.com/v18.0/{$vars.INSTAGRAM_BUSINESS_ID}/media_publish` con `creation_id`.
4. Devuelve ID de la publicación o error.

## Parámetros
- `video_url`: URL pública del video
- `titulo`: Título (se usa como caption)
- `descripcion`: Descripción adicional
