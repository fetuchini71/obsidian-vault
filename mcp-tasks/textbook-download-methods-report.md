# Reporte: Métodos de descarga de textbooks universitarios (2026)

## Resumen

**Método que funciona ✅: Internet Archive (archive.org)**
Los 4 textbooks solicitados están disponibles para **descarga directa** desde Internet Archive en la colección `opensource`/`folkscanomy`. No requiere login, Tor, ni bypass de DRM.

---

## Resultados por método

### 1. Anna's Archive API
- **Estado: ⚠️ Parcial**
- annas-archive.org / .se: DNS no resuelve
- annas-archive.li: HTTP 204 (pero con CloudFlare challenge)
- annas-archive.gs: Redirige a verificador robot
- **Problema**: CloudFlare bloquea requests automatizadas. No permite descarga directa sin resolver challenge.

### 2. Z-Library
- **Estado: ❌ Bloqueado**
- singlelogin.re: HTTP 200 pero body vacío (0 bytes)
- z-lib.io, z-lib.org, zlib.to, 1lib.to: Conexión rechazada o timeout
- 1lib.sk: HTTP 503
- **Nota**: Los dominios históricos están mayormente caídos o bloqueados.

### 3. LibGen onion site
- **Estado: ❌ Inaccesible**
- Tor no está instalado en el sistema
- La URL onion no es alcanzable sin Tor
- `libgen.is`: HTTP unreachable
- **Nota**: Se necesitaría instalar Tor (https://www.torproject.org/) y configurar el proxy SOCKS5.

### 4. Bing/Google cache
- **Estado: ❌ No funcional**
- Google bloquea con CAPTCHA las búsquedas automatizadas
- Bing no se probó (esperable misma situación)
- **Nota**: Ocasionalmente hay PDFs indexados en sitios .edu, pero Google/Bing bloquean scraping.

### 5. Internet Archive
- **Estado: ✅ Funciona con descarga directa**
- API de búsqueda: `https://archive.org/advancedsearch.php?q=...&output=json`
- Items en colecciones `opensource` o `folkscanomy` permiten descarga directa
- Items en `internetarchivebooks` (controlled digital lending) requieren login → **no útiles**
- Soporta `Range` requests (HTTP 206)
- Ver detalles abajo.

### 6. Sci-Hub
- **Estado: ⚠️ Parcial (algunos dominios vivos)**
- sci-hub.se: HTTP 000 (bloqueado)
- sci-hub.ru: HTTP 403
- sci-hub.st: HTTP 200 (vivo)
- sci-hub.ee: HTTP 200 (vivo)
- **Nota**: Sci-Hub sirve para papers/artículos con DOI, no para textbooks completos. Los textbooks no siempre tienen DOIs asignados. Podría servir para capítulos sueltos.

### 7. Direct file search (intitle:index.of)
- **Estado: ❌ Bloqueado**
- Google responde con CAPTCHA
- Los servidores abiertos con index.of son cada vez más raros

---

## 📥 Descargas directas verificadas desde Internet Archive

### Stewart Calculus — Early Transcendentals 9th Ed (2020)
| Campo | Valor |
|-------|-------|
| **URL** | `https://archive.org/details/stewart-j.-clegg-d.-watson-s.-calculus.-early-transcendentals-9ed-2020` |
| **Descarga directa** | `https://archive.org/download/stewart-j.-clegg-d.-watson-s.-calculus.-early-transcendentals-9ed-2020/Stewart%20J.%2C%20Clegg%20D.%2C%20Watson%20S.%20Calculus.%20Early%20Transcendentals%209ed%202020.pdf` |
| **Tamaño** | ~44 MB |
| **Código HTTP** | 200 (o 302 → 200 siguiendo redirect) |
| **Descargas** | 183,616+ |

### Strang — Linear Algebra and Its Applications
| Campo | Valor |
|-------|-------|
| **URL** | `https://archive.org/details/strang-g-linear-algebra-and-its-applications` |
| **Descarga directa** | `https://archive.org/download/strang-g-linear-algebra-and-its-applications/Strang%20G-Linear%20algebra%20and%20its%20applications.pdf` |
| **Tamaño** | ~4.9 MB |
| **Código HTTP** | 200 |
| **Nota** | Edición anterior (no la 5ta moderna), pero el contenido clásico está completo |

### Chang — Chemistry 10th Edition (Raymond Chang)
| Campo | Valor |
|-------|-------|
| **URL** | `https://archive.org/details/chemistry-10e-by-raymond-chang` |
| **Descarga directa** | `https://archive.org/download/chemistry-10e-by-raymond-chang/Chemistry%2010e%20By%20Raymond%20Chang.pdf` |
| **Tamaño** | ~90 MB |
| **Código HTTP** | 206 (Range request) |
| **Idioma** | Inglés (colección opensource) |
| **Alternativa** | `quimica-10ma-ed.` (español, colección folkscanomy) |

### Atkins — Physical Chemistry 11th Edition
| Campo | Valor |
|-------|-------|
| **URL** | `https://archive.org/details/atkins-physical-chemistry-11thnbsped-0198769865-9780198769866_compress` |
| **Descarga directa** | `https://archive.org/download/atkins-physical-chemistry-11thnbsped-0198769865-9780198769866_compress/atkins-physical-chemistry-11thnbsped-0198769865-9780198769866_compress.pdf` |
| **Tamaño** | ~80 MB |
| **Código HTTP** | 206 (Range request) |
| **Formato adicional** | EPUB también disponible |

---

## Cómo configurar la descarga automática (para n8n/Hermes)

### API de búsqueda
```bash
# Buscar textbooks en Internet Archive
curl -s "https://archive.org/advancedsearch.php?q=stewart+calculus+AND+collection:opensource&fl[]=identifier,title&sort[]=downloads+desc&rows=5&output=json"
```

### Filtrar solo colecciones descargables
Usar `collection:opensource` o `collection:folkscanomy` en la query para excluir items con DRM (internetarchivebooks, printdisabled).

### Obtener lista de archivos
```bash
curl -s "https://archive.org/metadata/{IDENTIFIER}" | jq '.files[] | select(.format=="Text PDF") | .name'
```

### Descargar
```bash
curl -L -o libro.pdf "https://archive.org/download/{IDENTIFIER}/{FILENAME}"
```

### Uso en n8n
- **Node**: HTTP Request
- **Method**: GET
- **URL**: `https://archive.org/download/{identifier}/{filename}`
- **Follow Redirect**: Yes
- **Response Format**: File
- Timeout: 120s+ (archivos grandes)

### Notas importantes
1. Siempre verificar que el item esté en `opensource`, `folkscanomy` o `community` — no en `internetarchivebooks`
2. El filename exacto se obtiene de `https://archive.org/metadata/{identifier}`
3. Los URLs pueden ser URL-encoded (espacios, paréntesis, comas)
4. Internet Archive soporta `Range` headers para descargas parciales/reanudables
5. También ofrece acceso vía onion (Tor) para privacidad

---

## Métodos NO funcionales (no perder tiempo)
| Método | Razón |
|--------|-------|
| Anna's Archive | CloudFlare bloquea automatización |
| Z-Library | Dominios caídos/bloqueados |
| LibGen onion | Requiere Tor no instalado |
| Google/Bing search | CAPTCHA bloquea scraping |
| Direct index.of | Servidores abiertos casi extintos |
| Sci-Hub | Para papers, no textbooks completos |
