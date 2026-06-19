
## Descargador de Textbooks — integración Internet Archive

**Fecha**: 2026-06-19

**Estado**: ✅ Completo

### Pipeline de descarga
1. **LibGen.li** (búsqueda + metadata) → rico en datos (MD5, edition_id, autores)
2. **Enriquecimiento** → edition_url, magnet_links, ipfs_pdf_links, onion_links
3. **Intento HTTP directo** (bloqueado en la mayoría de mirrors, timeout 25-30s)
4. **Fallback: aria2c** → intenta torrent con trackers públicos (120s timeout, generalmente sin seeders)
5. **Fallback: Internet Archive** → ✅ funciona con descarga directa HTTP

### Internet Archive
- API: `https://archive.org/advancedsearch.php?q={query}+AND+collection:opensource&output=json`
- Metadata: `https://archive.org/metadata/{identifier}`
- Descarga directa: `https://archive.org/download/{identifier}/{filename}`
- **Colecciones descargables**: `opensource`, `folkscanomy`, `community`
- **No descargable**: `internetarchivebooks` (DRM/préstamo controlado devuelve 401/403)
- Tamaño típico: 5-90 MB por libro
- Velocidad: ~30-60s para 34 MB (Stewart Calculus 8ed)

### Script
- **Ruta**: `~/scripts/descargador_libros.py`
- **17 funciones**, 1042 líneas
- **Uso principal**: `--search-only` (reporta JSON con metadata + links)
- **Funciones nuevas**:
  - `buscar_y_descargar_ia(título, autor, dest_path)` → busca y descarga
  - `try_download_ia(identifier, filename, dest_path)` → descarga directa
  - `_ia_search(query)` → busca en API de IA
  - `_ia_get_pdf_files(identifier)` → obtiene archivos PDF disponibles

### Cron
- **LibGen textbook search** → cada 4h (00,04,08,12,16,20), modo `--search-only`
- Entrega a Telegram con resumen formateado
