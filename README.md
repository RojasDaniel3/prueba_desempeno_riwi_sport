# RiwiSport — Informe y análisis (descripción exacta del repo)

Este repositorio contiene artefactos para el análisis de ventas de RiwiSport. El README a continuación describe únicamente los archivos que están presentes actualmente en la raíz del repo.

Contenido actual (archivos/carpetas presentes)

- `.env` — archivo de entorno local (contiene variables privadas: credenciales, host, puerto, etc.). NO debe subirse al repositorio.
- `.gitignore` — archivo presente y configurado para ignorar `.env`, entornos virtuales y cachés.
- `analisis_RIWI_Sport_Daniel-Rojas copy.ipynb` — notebook principal que contiene consultas SQL, funciones de carga/limpieza y análisis con pandas/matplotlib/seaborn.
- `requirements.txt` — lista mínima de dependencias detectadas (ver sección "Requisitos").
- `venv/` — entorno virtual local (carpeta presente; no subir).
- `__pycache__/` — caché generada por Python (ignorarla/omitida en commits).
- `LICENSE` — licencia del repositorio.

Resumen del notebook principal

El archivo `analisis_RIWI_Sport_Daniel-Rojas copy.ipynb` incluye (entre otras celdas):

- Conexión a una base de datos PostgreSQL usando SQLAlchemy y una URL con `psycopg2` (lee credenciales desde `.env` mediante `python-dotenv`).
- Consultas SQL que extraen:
	- ventas por ítem (con columnas: id_customer, full_name, city, id_order, product_name, category_name, amount, price, item_revenue)
	- ventas agregadas por ciudad, categoría, producto y cliente
- Funciones de limpieza y verificación (`clean_data`) que normalizan tipos y chequean nulos.
- Funciones de cálculo de estadísticas y KPI (media, mediana, desviación estándar, IQR, AOV).
- Funciones de visualización con Matplotlib/Seaborn (histogramas, boxplots, barras).
- Rutinas para generar insights (por ejemplo: producto con mayor variabilidad de precio, categoría top por ingresos, clientes más rentables).

Requisitos (contenido actual de `requirements.txt`)

```
pandas
numpy
matplotlib
seaborn
sqlalchemy
psycopg2-binary
python-dotenv
```

Instrucciones mínimas para reproducir localmente (si decides ejecutar el análisis)

1) Crear y activar un entorno virtual (opcional pero recomendado):

```bash
python -m venv .venv
source .venv/bin/activate
```

2) Instalar dependencias:

```bash
pip install -r requirements.txt
```

3) Crear un archivo `.env` en la raíz (NO subirlo) con las variables necesarias para la conexión a la base de datos, por ejemplo:

```
DB_HOST=localhost
DB_PORT=5432
DB_NAME=prueba_desempeno
DB_USER=tu_usuario
DB_PASSWORD=tu_contraseña
```

4) Abrir el notebook `analisis_RIWI_Sport_Daniel-Rojas copy.ipynb` (por ejemplo con Jupyter) y ejecutar las celdas que necesites. Si no trabajas con Jupyter, puedes extraer las funciones del notebook a un script Python y ejecutarlas desde la consola.

Daniel Fernando Rojas Echeverria 
CC 1002210129
Clan: Análitica de datos