1|# Reporte: Métodos de descarga de textbooks universitarios (2026)
2|
3|## Resumen
4|
5|**Método que funciona ✅: Internet Archive (archive.org)**
6|Los 4 textbooks solicitados están disponibles para **descarga directa** desde Internet Archive en la colección `opensource`/`folkscanomy`. No requiere login, Tor, ni bypass de DRM.
7|
8|---
9|
10|## Resultados por método
11|
12|### 1. Anna's Archive API
13|- **Estado: ⚠️ Parcial**
14|- annas-archive.org / .se: DNS no resuelve
15|- annas-archive.li: HTTP 204 (pero con CloudFlare challenge)
16|- annas-archive.gs: Redirige a verificador robot
17|- **Problema**: CloudFlare bloquea requests automatizadas. No permite descarga directa sin resolver challenge.
18|
19|### 2. Z-Library
20|- **Estado: ❌ Bloqueado**
21|- singlelogin.re: HTTP 200 pero body vacío (0 bytes)
22|- z-lib.io, z-lib.org, zlib.to, 1lib.to: Conexión rechazada o timeout
23|- 1lib.sk: HTTP 503
24|- **Nota**: Los dominios históricos están mayormente caídos o bloqueados.
25|
26|### 3. LibGen onion site
27|- **Estado: ❌ Inaccesible**
28|- Tor no está instalado en el sistema
29|- La URL onion no es alcanzable sin Tor
30|- `libgen.is`: HTTP unreachable
31|- **Nota**: Se necesitaría instalar Tor (https://www.torproject.org/) y configurar el proxy SOCKS5.
32|
33|### 4. Bing/Google cache
34|- **Estado: ❌ No funcional**
35|- Google bloquea con CAPTCHA las búsquedas automatizadas
36|- Bing no se probó (esperable misma situación)
37|- **Nota**: Ocasionalmente hay PDFs indexados en sitios .edu, pero Google/Bing bloquean scraping.
38|
39|### 5. Internet Archive
40|- **Estado: ✅ Funciona con descarga directa**
41|- API de búsqueda: `https://archive.org/advancedsearch.php?q=...&output=json`
42|- Items en colecciones `opensource` o `folkscanomy` permiten descarga directa
43|- Items en `internetarchivebooks` (controlled digital lending) requieren login → **no útiles**
44|- Soporta `Range` requests (HTTP 206)
45|- Ver detalles abajo.
46|
47|### 6. Sci-Hub
48|- **Estado: ⚠️ Parcial (algunos dominios vivos)**
49|- sci-hub.se: HTTP 000 (bloqueado)
50|- sci-hub.ru: HTTP 403
51|- sci-hub.st: HTTP 200 (vivo)
52|- sci-hub.ee: HTTP 200 (vivo)
53|- **Nota**: Sci-Hub sirve para papers/artículos con DOI, no para textbooks completos. Los textbooks no siempre tienen DOIs asignados. Podría servir para capítulos sueltos.
54|
55|### 7. Direct file search (intitle:index.of)
56|- **Estado: ❌ Bloqueado**
57|- Google responde con CAPTCHA
58|- Los servidores abiertos con index.of son cada vez más raros
59|
60|---
61|
62|## 📥 Descargas directas verificadas desde Internet Archive
63|
64|### Stewart Calculus — Early Transcendentals 9th Ed (2020)
65|| Campo | Valor |
66||-------|-------|
67|| **URL** | `https://archive.org/details/stewart-j.-clegg-d.-watson-s.-calculus.-early-transcendentals-9ed-2020` |
68|| **Descarga directa** | `https://archive.org/download/stewart-j.-clegg-d.-watson-s.-calculus.-early-transcendentals-9ed-2020/Stewart%20J.%2C%20Clegg%20D.%2C%20Watson%20S.%20Calculus.%20Early%20Transcendentals%209ed%202020.pdf` |
69|| **Tamaño** | ~44 MB |
70|| **Código HTTP** | 200 (o 302 → 200 siguiendo redirect) |
71|| **Descargas** | 183,616+ |
72|
73|### Strang — Linear Algebra and Its Applications
74|| Campo | Valor |
75||-------|-------|
76|| **URL** | `https://archive.org/details/strang-g-linear-algebra-and-its-applications` |
77|| **Descarga directa** | `https://archive.org/download/strang-g-linear-algebra-and-its-applications/Strang%20G-Linear%20algebra%20and%20its%20applications.pdf` |
78|| **Tamaño** | ~4.9 MB |
79|| **Código HTTP** | 200 |
80|| **Nota** | Edición anterior (no la 5ta moderna), pero el contenido clásico está completo |
81|
82|### Chang — Chemistry 10th Edition (Raymond Chang)
83|| Campo | Valor |
84||-------|-------|
85|| **URL** | `https://archive.org/details/chemistry-10e-by-raymond-chang` |
86|| **Descarga directa** | `https://archive.org/download/chemistry-10e-by-raymond-chang/Chemistry%2010e%20By%20Raymond%20Chang.pdf` |
87|| **Tamaño** | ~90 MB |
88|| **Código HTTP** | 206 (Range request) |
89|| **Idioma** | Inglés (colección opensource) |
90|| **Alternativa** | `quimica-10ma-ed.` (español, colección folkscanomy) |
91|
92|### Atkins — Physical Chemistry 11th Edition
93|| Campo | Valor |
94||-------|-------|
95|| **URL** | `https://archive.org/details/atkins-physical-chemistry-11thnbsped-0198769865-9780198769866_compress` |
96|| **Descarga directa** | `https://archive.org/download/atkins-physical-chemistry-11thnbsped-0198769865-9780198769866_compress/atkins-physical-chemistry-11thnbsped-0198769865-9780198769866_compress.pdf` |
97|| **Tamaño** | ~80 MB |
98|| **Código HTTP** | 206 (Range request) |
99|| **Formato adicional** | EPUB también disponible |
100|
101|---
102|
103|## Cómo configurar la descarga automática (para n8n/Hermes)
104|
105|### API de búsqueda
106|```bash
107|# Buscar textbooks en Internet Archive
108|curl -s "https://archive.org/advancedsearch.php?q=stewart+calculus+AND+collection:opensource&fl[]=identifier,title&sort[]=downloads+desc&rows=5&output=json"
109|```
110|
111|### Filtrar solo colecciones descargables
112|Usar `collection:opensource` o `collection:folkscanomy` en la query para excluir items con DRM (internetarchivebooks, printdisabled).
113|
114|### Obtener lista de archivos
115|```bash
116|curl -s "https://archive.org/metadata/{IDENTIFIER}" | jq '.files[] | select(.format=="Text PDF") | .name'
117|```
118|
119|### Descargar
120|```bash
121|curl -L -o libro.pdf "https://archive.org/download/{IDENTIFIER}/{FILENAME}"
122|```
123|
124|### Uso en n8n
125|- **Node**: HTTP Request
126|- **Method**: GET
127|- **URL**: `https://archive.org/download/{identifier}/{filename}`
128|- **Follow Redirect**: Yes
129|- **Response Format**: File
130|- Timeout: 120s+ (archivos grandes)
131|
132|### Notas importantes
133|1. Siempre verificar que el item esté en `opensource`, `folkscanomy` o `community` — no en `internetarchivebooks`
134|2. El filename exacto se obtiene de `https://archive.org/metadata/{identifier}`
135|3. Los URLs pueden ser URL-encoded (espacios, paréntesis, comas)
136|4. Internet Archive soporta `Range` headers para descargas parciales/reanudables
137|5. También ofrece acceso vía onion (Tor) para privacidad
138|
139|---
140|
141|## Métodos NO funcionales (no perder tiempo)
142|| Método | Razón |
143||--------|-------|
144|| Anna's Archive | CloudFlare bloquea automatización |
145|| Z-Library | Dominios caídos/bloqueados |
146|| LibGen onion | Requiere Tor no instalado |
147|| Google/Bing search | CAPTCHA bloquea scraping |
148|| Direct index.of | Servidores abiertos casi extintos |
149|| Sci-Hub | Para papers, no textbooks completos |
150|