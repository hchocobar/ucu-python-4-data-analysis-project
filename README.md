# Proyecto

## Análisis Interactivo de Datos con Streamlit

**Objetivos:** 
- Realizar el Análisis Exploratorio de Datos (EDA) de un conjunto de datos utilizando **Pandas**.
- Desarrollar una aplicación interactiva en **Streamlit** que cargue y visualice un conjunto de datos estándar, aplicando conceptos de manipulación de datos con **Pandas** e integración de *widgets* interactivos.

## Dataset seleccionado: California House Prices (modificado)

Utilizaremos el *dataset* de precios de viviendas de California, un conjunto de datos clásico.

* **Librería de Origen:** `sklearn.datasets`
* **Fuente:** Este dataset fue creado a partir de datos del censo de 1990 en California.

### Descripción del Dataset

El *dataset* de California contiene datos sobre la mediana de ingresos, la edad de las casas y otras métricas geográficas y socioeconómicas a nivel de grupo de bloques (la unidad geográfica más pequeña para la que la Oficina del Censo de EE. UU. publica datos de muestra).

| Característica       | Descripción                                                        |
|:---------------------|:-------------------------------------------------------------------|
| MedInc               | Mediana de ingresos del grupo de bloques.                          |
| HouseAge             | Mediana de la edad de las casas dentro del grupo de bloques.       |
| AveRooms             | Promedio de habitaciones por hogar.                                |
| AveBedrms            | Promedio de dormitorios por hogar.                                 |
| Population           | Población del grupo de bloques.                                    |
| AveOccup             | Promedio del número de miemros del hogar.                          |
| Latitude             | Latitud del centro geográfico del grupo de bloques.                |
| Longitude            | Longitud del centro geográfico del grupo de bloques.               |
| MedHouseVal (Target) | Mediana del valor de la vivienda (en cientos de miles de dólares). |

---

## Actividades Requeridas del Proyecto

El proyecto se dividirá en dos fases:

La primera fase realizada en el archivo `practice.ipynb` consiste en:
- Carga y Preparación de Datos (Pandas en Jupyter Notebook), 
- Análisis Exploratorio de Datos (Pandas en Jupyter Notebook)
- Grabación del dataframe resultante en un archivo CSV

La segunda fase realizada en el archivo `app.py` consiste en:
- Análisis Descriptivo Interactivo (Streamlit), y 
- Visualización Dinámica (Streamlit).
- Despliegue en la Nube (Streamlit Community Cloud).

### Primera Fase

En el archivo `notebooks/practice.ipynb`: 

1. **Carga y Estructura:** Cargar el archivo `data/california_housing.csv` y conviértelo en un DataFrame de Pandas.
2. **EDA**: Realiza un Análisis Exploratorio de Datos (EDA) del DataFrame utilizando Pandas, límpialo y obtiene un nuevo dataframe.
3. **Grabar**: Graba el DataFrame en un archivo CSV con un nuevo nombre descriptivo en el directorio `data/`.

### Segunda Fase

En el archivo `app.py`:

#### Análisis Descriptivo Interactivo (Streamlit Widgets)
Esta fase se centra en usar los *widgets* de Streamlit para permitir al usuario explorar los datos.

1.  **Sidebar de Control (`st.sidebar`):**
    * Implementar un `st.sidebar.markdown()` para el título y descripción de los filtros.
2.  **Filtro por Estilo de Vivienda (`st.slider`):**
    * Crear un **slider** que permita al usuario seleccionar un rango de la Edad Mediana de la Casa (HouseAge).
    * Rango: El rango del slider debe ir desde el mínimo hasta el máximo de la columna HouseAge.
    * Filtrar el DataFrame para incluir solo las viviendas cuya edad mediana caiga dentro del rango seleccionado por el usuario.
3.  **Filtro de Vecindario (`st.checkbox`):**
    * Implementar un campo de entrada numérico (`st.number_input`) que permita al usuario establecer la Latitud Mínima.
    * Filtrar el DataFrame para incluir solo los grupos de bloques con una Latitude mayor o igual al valor ingresado.
4.  **Resumen Descriptivo:**
    * Mostrar la mediana y el rango (Máximo - Mínimo) del valor de la vivienda MedHouseVal del DataFrame resultante después de aplicar todos los filtros.

#### Visualización Dinámica

Deberás mostrar la relación entre las variables utilizando gráficos que se actualicen automáticamente con los filtros anteriores.

1.  **Gráfico de Distribución del Target (`st.pyplot` o `st.plotly_chart`):**
    * Crear un **histograma** de la variable objetivo (**MedHouseVal**) utilizando una librería externa (como Matplotlib o Plotly).
    * **Requisito:** El gráfico debe reflejar la distribución de los datos **después** de aplicar los filtros del usuario.
2.  **Gráfico de Dispersión (Regresión):**
    * Crear un gráfico de dispersión (scatter plot) que muestre la relación entre la Mediana de Ingresos (MedInc) (eje X) y el Valor Mediano de la Vivienda (MedHouseVal) (eje Y).
    * **Requisito:** Este gráfico también debe actualizarse con los datos filtrados y ser lo suficientemente informativo (ej. incluir etiquetas y un título).
3.  ** Opcional - Mapa Geográfico** (Streamlit Nativo o Plotly):
    * Utilizar la función nativa de Streamlit (st.map()) o un gráfico de dispersión de Plotly con st.plotly_chart() para mapear los grupos de bloques filtrados usando las columnas Latitude y Longitude.
    * Requisito: El mapa debe mostrar la distribución geográfica de las viviendas filtradas por el usuario.

---

#### Despliegue en la Nube

Deberás preparar tu proyecto para el despliegue.

1.  **Git/GitHub:** Crear un **repositorio público** en GitHub a partir de este template.

2.  **Estructura de Carpeta:**
    * `app.py` (código de Streamlit).
    * `notebooks/practice.ipynb` en este archivo puedes realizar un análisis previo del dataset propuesto
    * `requirements.txt` (listado de dependencias: `streamlit`, `pandas`, `scikit-learn`, `matplotlib` o `plotly`).

3.  **Despliegue:** Desplegar la aplicación final utilizando **Streamlit Community Cloud** (share.streamlit.io).

## Entrega

Deberás entregar:
- el **enlace al repositorio de GitHub**.
- el **enlace a la aplicación desplegada**
