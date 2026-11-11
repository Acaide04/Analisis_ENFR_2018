# Análisis de la Encuesta Nacional de Factores de Riesgo 2018

Trabajo Práctico Especial de **Fundamentos de la Ciencia de Datos** (cursada 2026).

**Grupo 10**
- Joan Martin Lenti
- Valentina Bianchi
- Manuel Taboada

## Descripción

Análisis exploratorio y estadístico de la base usuario de la 4.° Encuesta Nacional de Factores de Riesgo (ENFR 2018), publicada por el INDEC y la Secretaría de Gobierno de Salud de la Nación.

El trabajo incluye:

1. Carga de la base y limpieza de los datos.
2. Barrido general de las variables, organizado según los bloques del manual de la base usuario.
3. Planteo y validación de tres hipótesis propias:
   - **Univariada:** olvido de la medicación en personas hipertensas.
   - **Bivariada:** uso de sal en las comidas y prevalencia de hipertensión.
   - **Multivariada:** colesterol elevado, consumo de frutas y verduras y percepción de la propia alimentación.
4. Validación de las tres hipótesis del enunciado:
   - **Univariada:** consumo diario de frutas y verduras frente a la recomendación de la OMS.
   - **Bivariada:** índice de masa corporal según el nivel de actividad física.
   - **Multivariada:** relación lineal entre IMC, presión sistólica, perímetro de cintura, edad y glucemia.

## Contenido del repositorio

| Archivo | Descripción |
|---|---|
| `main.ipynb` | Notebook de Jupyter con todo el análisis, organizado en secciones |
| `Informe.pdf` | Informe con los principales hallazgos y conclusiones |
| `ENFR 2018 - Base usuario.txt` | Base de datos usuario de la ENFR 2018 |
| `manual_base_usuario_enfr2018.pdf` | Manual de uso de la base de datos usuario (INDEC) |
| `Cuestionario.pdf` | Cuestionario de la ENFR 2018 |
| `enfr_2018_resultados_definitivos.pdf` | Informe de resultados definitivos de la ENFR 2018 |
| `requirements.txt` | Librerías necesarias para ejecutar el notebook |
| `README.md` | Este archivo |

## Requisitos

- Python 3.10 o superior.
- `pip` (incluido con Python).
- Conexión a internet: el notebook descarga la base de datos desde la rama `main` de este repositorio.

## Instalación

**1. Clonar el repositorio:**

```bash
git clone https://github.com/Acaide04/Analisis_ENFR_2018.git
cd Analisis_ENFR_2018
```

También se puede descargar como ZIP desde GitHub (botón **Code → Download ZIP**) y descomprimirlo.

**2. (Recomendado) Crear y activar un entorno virtual:**

En Windows (símbolo del sistema o PowerShell):

```bash
python -m venv venv
venv\Scripts\activate
```

Si PowerShell bloquea la activación por la política de ejecución de scripts, ejecutar antes `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned`, o usar el símbolo del sistema (`cmd`). Si el comando `python` no se reconoce, probar con `py`.

En Linux o macOS:

```bash
python3 -m venv venv
source venv/bin/activate
```

**3. Instalar las dependencias** (en todos los sistemas operativos, con el entorno virtual activado):

```bash
pip install -r requirements.txt
```

## Ejecución

**1. Abrir Jupyter desde la carpeta del repositorio:**

Windows
```bash
jupyter lab
```
Linux/MacOs
```bash
jupyter-lab
```
Si no funciona con el anterior comando, probar con el siguiente 

```bash
jupyter notebook
```

**2.** En el navegador, abrir el archivo `main.ipynb`.

**3.** Ejecutar todas las celdas en orden desde el menú **Kernel → Restart & Run All** (en Jupyter Notebook 7: **Run → Run All Cells**).

El notebook es secuencial: cada sección usa los dataframes creados en las anteriores, por lo que las celdas deben ejecutarse en orden, de principio a fin.

También puede abrirse con Visual Studio Code (con la extensión de Jupyter) o JupyterLab, seleccionando como kernel el entorno virtual creado en la instalación.


## Posibles problemas

- **Error al importar `statsmodels`** (`TypeError: deprecate_kwarg() got an unexpected keyword argument 'klass'`): se debe a una incompatibilidad con pandas 3. Se resuelve instalando las versiones del `requirements.txt` (`pip install -r requirements.txt`) y reiniciando el kernel.
- **El notebook no encuentra los datos:** la base se descarga en la sección 2 desde
  `https://raw.githubusercontent.com/Acaide04/Analisis_ENFR_2018/refs/heads/main/ENFR%202018%20-%20Base%20usuario.txt`.
  Si no hay conexión a internet, se puede usar el archivo incluido en el repositorio: en la celda de carga de la sección 2, reemplazar el valor de `url` por `"ENFR 2018 - Base usuario.txt"` (el notebook tiene que estar en la misma carpeta que el archivo).
- **`pip install` falla con el error `externally-managed-environment`** (frecuente en algunas distribuciones de Linux): crear y activar el entorno virtual del paso 2 de la instalación antes de instalar las dependencias.
