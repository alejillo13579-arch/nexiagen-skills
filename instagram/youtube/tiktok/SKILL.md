---
name: publicar-tiktok
description: Publica un video en TikTok vía Blotato
---

# Skill: Publicar en TikTok

## Instrucciones
1. Recibe `video_url`, `titulo`, `descripcion`.
2. Envía POST a `https://api.blotato.com/v1/upload` con `Authorization: Bearer {$vars.BLOTATO_API_KEY}` y body `{"url": video_url, "caption": titulo + "\n\n" + descripcion}`.
3. Devuelve ID del video o error.

## Parámetros
- `video_url`: URL pública del video
- `titulo`: Título (usado como caption)
- `descripcion`: Descripción adicional
