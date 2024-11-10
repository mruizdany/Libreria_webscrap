# SCRAP DE LIBROS
Scrapping de los datos de libros de la libreria "La casa de los libros".   

# :notebook: Urbanismo Literature Scraper

## Descripción
Urbanismo Literature Scraper es una herramienta profesional de web scraping diseñada específicamente para recopilar y analizar información sobre libros y revistas relacionados **con urbanismo y transporte** de las principales **librerías online españolas**. La herramienta utiliza técnicas avanzadas de scraping respetuoso y procesamiento inteligente para identificar y extraer contenido relevante.

![Python Version](https://img.shields.io/badge/python-3.8+-blue.svg)
![BeautifulSoup4](https://img.shields.io/badge/BeautifulSoup4-4.9+-green.svg)
![Requests](https://img.shields.io/badge/requests-2.25+-yellow.svg)
![Pandas](https://img.shields.io/badge/pandas-1.2+-red.svg)

## 🌟 Características Principales

- **Scraping Multi-Librería**: Compatible con las principales plataformas (Casa del Libro, Fnac, Amazon)
- **Filtrado Inteligente**: Sistema avanzado de palabras clave para identificar contenido relevante
- **Control de Tiempo**: Monitorización detallada del rendimiento por chunk y operación
- **Gestión de Errores**: Sistema robusto de manejo de excepciones y reintentos
- **Logging Completo**: Registro detallado de todas las operaciones y tiempos
- **Exportación Flexible**: Salida en formato CSV con resumen estadístico

## 📋 Requisitos Previos

```bash
Python 3.8 o superior
pip (gestor de paquetes de Python)
```

## 🛠 Instalación

1. Clonar el repositorio:
```bash
git clone https://github.com/yourusername/urbanismo-scraper.git
cd urbanismo-scraper
```

2. Crear un entorno virtual (recomendado):
```bash
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
```

3. Instalar dependencias:
```bash
pip install -r requirements.txt
```

## 📖 Uso

### Uso Básico
```python
from urbanismo_scraper import UrbanismoScraper

scraper = UrbanismoScraper()
libros = scraper.scrapear_libros(max_paginas=5)
```

### Ejemplo Completo
```python
from urbanismo_scraper import UrbanismoScraper
import logging

# Configurar logging
logging.basicConfig(level=logging.INFO)

# Inicializar scraper
scraper = UrbanismoScraper()

try:
    # Ejecutar scraping
    libros = scraper.scrapear_libros(max_paginas=5)
    
    # Guardar resultados
    scraper.guardar_resultados(libros, 'libros_urbanismo')
    
except Exception as e:
    logging.error(f"Error en la ejecución: {str(e)}")
```

## 📊 Estructura de Datos

Los datos se exportan en formato CSV con los siguientes campos:

| Campo | Descripción |
|-------|-------------|
| titulo | Título del libro |
| autor | Autor(es) del libro |
| precio | Precio actual |
| isbn | Número ISBN (10 o 13 dígitos) |
| url | URL canónica del libro |
| fecha_extraccion | Timestamp de la extracción |

## ⚙️ Configuración

El script permite configurar varios parámetros:

```python
# config.py
CONFIGURACION = {
    'DELAY_MIN': 2,          # Delay mínimo entre peticiones (segundos)
    'DELAY_MAX': 5,          # Delay máximo entre peticiones (segundos)
    'MAX_REINTENTOS': 3,     # Número máximo de reintentos por petición
    'TAMANO_CHUNK': 10,      # Número de libros por chunk
    'USER_AGENT': 'Mozilla/5.0 ...'  # User agent personalizado
}
```

## 📝 Logging

El sistema genera dos tipos de logs:

1. **Log de Operaciones** (`scraping_urbanismo_YYYYMMDD.log`):
   - Tiempos de ejecución
   - Errores y excepciones
   - Información de progreso

2. **Resumen Estadístico** (`libros_urbanismo_resumen.txt`):
   - Total de libros extraídos
   - Autores únicos
   - Rango de precios
   - Fecha de extracción

## ⚠️ Consideraciones Éticas y Legales

1. **Respeto a robots.txt**:
   - Verificar y respetar las políticas de robots.txt
   - Mantener delays apropiados entre peticiones

2. **Uso Responsable**:
   - No saturar los servidores
   - Implementar límites de velocidad
   - Respetar los términos de servicio de cada sitio

3. **Datos Personales**:
   - No extraer información personal
   - Cumplir con GDPR/LOPD cuando aplique

## 🔧 Mantenimiento y Contribución

### Reportar Problemas
Utilice el sistema de issues de GitHub para reportar problemas:
- Describa el problema detalladamente
- Incluya logs relevantes
- Proporcione pasos para reproducir el error

### Contribuir
1. Fork del repositorio
2. Crear rama feature (`git checkout -b feature/NuevaCaracteristica`)
3. Commit de cambios (`git commit -am 'Añadir nueva característica'`)
4. Push a la rama (`git push origin feature/NuevaCaracteristica`)
5. Crear Pull Request

## 📈 Rendimiento

El script incluye mediciones de rendimiento detalladas:
- Tiempo por petición
- Tiempo por chunk de procesamiento
- Tiempo total de ejecución
- Estadísticas de éxito/fallo

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

## 👥 Autores

- Nombre del Autor - [Correo](mailto:autor@ejemplo.com)

## 🙏 Agradecimientos

- BeautifulSoup4 por su excelente biblioteca de parsing HTML
- Requests por su robusta biblioteca HTTP
- Pandas por el manejo eficiente de datos

---
⌨️ con ❤️ por [Tu Nombre/Organización]


He creado un README profesional y completo que incluye:

1. **Badges** de versiones y dependencias
2. **Documentación detallada** de instalación y uso
3. **Consideraciones éticas** importantes para web scraping
4. **Estructura clara** con emojis para mejor legibilidad
5. **Ejemplos de código** prácticos
6. **Sección de mantenimiento** y contribución
7. **Tablas** para explicar la estructura de datos
8. **Información sobre logging** y rendimiento

¿Necesitas que expanda alguna sección o que añada información adicional?