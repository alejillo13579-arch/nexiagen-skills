---
name: escaneo-virustotal
description: Consulta VirusTotal para detectar amenazas en dominios e IPs
---

# Skill: Escaneo VirusTotal

## Descripción
Este skill permite consultar la API de VirusTotal para obtener detecciones de malware, phishing y otras amenazas asociadas a un dominio o IP.

## Cuándo usarlo
- Usuario solicita: "Escanea este dominio", "Verifica esta IP", "¿Está limpio este sitio?".
- Se activa cuando el usuario proporciona un dominio (ej. `mipyme.com`) o una IP (ej. `192.168.1.1`).

## Instrucciones
1. Extrae el dominio o IP de la consulta del usuario.
2. Usa la herramienta `httpRequest` para llamar a la API de VirusTotal:
   - **Endpoint para IP:** `https://www.virustotal.com/api/v3/ip_addresses/{ip}`
   - **Endpoint para dominio:** `https://www.virustotal.com/api/v3/domains/{domain}`
   - **Headers:** `x-apikey: {{ $vars.VIRUSTOTAL_API_KEY }}`
3. Procesa la respuesta y extrae:
   - `last_analysis_stats`: `malicious`, `suspicious`, `undetected`, `harmless`
   - `reputation` (si existe)
   - `last_analysis_date`
4. Clasifica el resultado:
   - **🔴 Critico:** `malicious > 0`
   - **🟠 Alto:** `suspicious > 2`
   - **🟡 Medio:** `suspicious <= 2`
   - **🟢 Bajo:** `malicious === 0 && suspicious === 0`
5. Devuelve el resultado con una recomendación clara.

## Parámetros de entrada
- `target` (string): Dominio o IP a escanear.
- `tipo` (string): `"dominio"` o `"ip"`.

## Ejemplo de respuesta
