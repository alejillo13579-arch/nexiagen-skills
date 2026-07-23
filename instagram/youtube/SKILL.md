---
name: publicar-youtube
description: Publica un video en YouTube (upload resumable)
---

# Skill: Publicar en YouTube

## Instrucciones
1. Recibe `video_url`, `titulo`, `descripcion`.
2. Inicia sesión resumable: POST a `https://www.googleapis.com/upload/youtube/v3/videos?uploadType=resumable&part=snippet,status` con `Authorization: Bearer {$vars.YOUTUBE_ACCESS_TOKEN}`.
3. Captura header `Location` y sube el video con PUT.
4. Devuelve ID del video o error.

## Parámetros
- `video_url`: URL pública del video
- `titulo`: Título del video
- `descripcion`: Descripción del video
