# Power-BI
Práctica final
# Proyecto de Análisis de Datos de Marketing con Power BI

# Power BI Marketing Campaign Analysis

## Preparación

### Paso 1: Descargar los datos
1. Visita el enlace: [Kaggle Marketing Campaign Dataset](https://www.kaggle.com/datasets/rodsaldanha/arketing-campaign?resource=download).
2. Inicia sesión en Kaggle o crea una cuenta si aún no tienes una.
3. Descarga el archivo CSV haciendo clic en el botón de descarga.
4. Guarda el archivo en una ubicación accesible en tu computadora.

### Paso 2: Configurar Power BI Desktop
1. Abre Power BI Desktop.
2. Guarda tu proyecto inmediatamente para evitar la pérdida de datos. Ve a "Archivo" > "Guardar" y elige una ubicación para tu archivo PBIX.

## Proceso de Extracción, Transformación y Carga de Datos (ETL)

### Extracción de datos
1. En Power BI Desktop, ve a la pestaña "Inicio" y selecciona "Obtener datos".
2. Selecciona "Texto/CSV".
3. Navega hasta la ubicación donde guardaste el archivo CSV descargado y selecciónalo. Haz clic en "Abrir".
4. Aparecerá una vista previa de los datos. Haz clic en "Cargar" para importar los datos a Power BI.

### Transformaciones de datos

#### Abrir el Power Query Editor:
1. En la pestaña "Inicio", selecciona "Transformar datos".

#### Limpieza y transformación de datos
1. **Revisar y cambiar los nombres de las columnas**:
    - Haz doble clic en los nombres de las columnas para renombrarlas de manera más descriptiva. Por ejemplo, renombra "ID" a "ClienteID", "Income" a "Ingreso", etc.
2. **Eliminar columnas o filas vacías**:
    - Selecciona las columnas o filas vacías, haz clic derecho y selecciona "Eliminar".
3. **Uso de Lenguaje M para transformaciones avanzadas**:
    - En el editor de Power Query, puedes usar Lenguaje M para realizar transformaciones avanzadas. Por ejemplo, si deseas combinar columnas, puedes usar `Table.CombineColumns`.
4. **Combinación y tratamiento de columnas**:
    - Si tienes columnas que representan diferentes aspectos del mismo atributo, puedes combinarlas. Por ejemplo, si tienes "Estado Civil" y "Educación", puedes combinarlas usando "Combinar columnas".
5. **Creación de tablas de dimensiones**:
    - Para crear tablas de dimensiones, selecciona las columnas relevantes y crea una nueva tabla. Por ejemplo, puedes crear una tabla de dimensiones para "Estado Civil" y "Educación".
6. **Carga de datos en el modelo**:
    - Una vez completadas las transformaciones, haz clic en "Cerrar y aplicar" para cargar los datos transformados en el modelo de Power BI.

## Desarrollo del Modelo de Datos

### Implementar un modelo de datos adecuado

1. **Crear un modelo de datos en estrella**:
    - En la vista de modelo, asegúrate de que la tabla de hechos (la principal) esté en el centro y que las tablas de dimensiones estén conectadas a ella.

### Métricas de DAX

1. **Total de clientes**:
    ```DAX
    TotalClientes = COUNTROWS(TablaDeHechos)
    ```
2. **Ingreso medio de los clientes**:
    ```DAX
    IngresoMedio = AVERAGE(TablaDeHechos[Ingreso])
    ```
3. **Totales de compras por producto**:
    ```DAX
    TotalComprasPorProducto = SUM(TablaDeHechos[Compras])
    ```
4. **Totales por campañas**:
    ```DAX
    TotalPorCampañas = SUM(TablaDeHechos[Campañas])
    ```

### Creación de la tabla calendario

1. **Crear una tabla calendario**:
    - Ve a la vista de datos, haz clic derecho en el panel de tablas y selecciona "Nueva tabla".
    - Crea la tabla calendario usando DAX:
    ```DAX
    Calendario = 
    ADDCOLUMNS (
        CALENDAR (DATE(2020, 1, 1), DATE(2023, 12, 31)),
        "Año", YEAR([Date]),
        "Mes", MONTH([Date]),
        "NombreMes", FORMAT([Date], "MMMM"),
        "Trimestre", QUARTER([Date])
    )
    ```

## Desarrollar Visualizaciones

### Paso 1: Crear visualizaciones

1. **Visión general de los datos**:
    - Crea una página con gráficos que den una visión general de los datos, como ventas totales, número de clientes, etc.
    - Usa gráficos de líneas, barras, anillos, tablas y matrices.
2. **Datos analizando las campañas**:
    - Crea una página que se enfoque en el análisis de las campañas de marketing.
    - Usa gráficos de barras apiladas y tablas para mostrar el rendimiento de cada campaña.
3. **Datos analizando los productos**:
    - Crea una página que se enfoque en el análisis de los productos.
    - Usa gráficos de anillos y tablas para mostrar las ventas por producto.
4. **Hoja cero oculta para anotaciones**:
    - Agrega una nueva página y déjala en blanco para realizar anotaciones internas.

### Paso 2: Configurar interacciones y filtros

1. **Agregar filtros**:
    - En cada visualización, usa el panel de filtros para agregar filtros de página o filtros de visualización.
2. **Configurar interacciones**:
    - Selecciona una visualización, luego en la pestaña "Formato", selecciona "Editar interacciones".
    - Configura cómo las visualizaciones interactúan entre sí para que las selecciones afecten adecuadamente a todas las visualizaciones relacionadas.

## Publicar y compartir el informe

### Paso 1: Publicar el informe
1. En la pestaña "Inicio", selecciona "Publicar".
2. Inicia sesión en tu cuenta de Power BI Service.
3. Selecciona el área de trabajo donde deseas publicar el informe y haz clic en "Seleccionar".

### Paso 2: Compartir el enlace
1. Abre Power BI Service en tu navegador.
2. Navega hasta el informe publicado.
3. Selecciona "Archivo" > "Obtener enlace" y copia el enlace para compartirlo.

## Entrega

1. **Guardar el archivo PBIX**.
2. **Exportar el informe como PDF**:
    - En Power BI Desktop, ve a "Archivo" > "Exportar" > "Exportar a PDF".
3. **Crear un archivo con las métricas de DAX**:
    - Utiliza DAX Studio para crear un archivo con las métricas solicitadas.
4. **Comprimir los archivos en un ZIP y nómbralo con tu nombre y apellido**. Asegúrate de que no supere los 20 MB.

### Archivos a entregar
- Archivo PBIX.
- PDF exportado.
- Archivo de DAX Studio con las métricas.
