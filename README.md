# Power-BI
Práctica final
# Proyecto de Análisis de Datos de Marketing con Power BI

Este proyecto ha sido desarrollado como parte del curso de Power BI y tiene como objetivo analizar una serie de datos del departamento de marketing de DH Marketing Consultants. A continuación, se detallan los pasos para realizar el proyecto.

## Preparación

### Paso 1: Descargar los datos
1. Visita el enlace: [Kaggle Marketing Campaign Dataset](https://www.kaggle.com/datasets/rodsaldanha/arketing-campaign?resource=download).
2. Inicia sesión en Kaggle o crea una cuenta si aún no tienes una.
3. Descarga el archivo CSV haciendo clic en el botón de descarga. Guarda el archivo en una ubicación accesible en tu computadora.

### Paso 2: Conectar los datos a Power BI
1. Abre Power BI Desktop.
2. En la pestaña "Inicio", selecciona "Obtener datos".
3. Selecciona "Texto/CSV".
4. Navega hasta la ubicación donde guardaste el archivo CSV descargado y selecciónalo. Haz clic en "Abrir".
5. Aparecerá una vista previa de los datos. Haz clic en "Cargar" para importar los datos a Power BI.

### Paso 3: Revisar los datos en Power Query
1. En la pestaña "Inicio", selecciona "Transformar datos". Esto abrirá el Power Query Editor.
2. Revisa cada columna para entender su contenido y estructura. Verifica los nombres de las columnas y los datos que contienen.

### Paso 4: Analizar y modificar los tipos de datos
1. Selecciona una columna para revisar su tipo de datos.
2. Para cambiar el tipo de datos, selecciona la columna, haz clic derecho y selecciona "Cambiar tipo". Elige el tipo de datos correcto (por ejemplo, "Fecha", "Número entero", "Texto").
3. Repite este paso para cada columna que necesite un cambio de tipo de datos.

## Limpieza de Datos

### Paso 1: Buscar errores en los datos
1. Revisar valores atípicos:
   - Filtra las columnas numéricas para identificar valores que no sean realistas (por ejemplo, edades mayores de 100 años).
   - Haz clic en el icono de filtro en la cabecera de la columna y selecciona "Número de filtros" para buscar valores extremos.
2. Revisar datos en blanco:
   - Filtra las columnas para mostrar solo las filas que contienen valores en blanco. Haz clic en el icono de filtro y selecciona "Filtrar por valor" y luego marca la opción "(Blanks)".
3. Revisar errores de escritura:
   - Filtra columnas de texto para buscar inconsistencias en los nombres o categorías.
   - Usa el "Filtro de texto" en la cabecera de la columna para buscar variaciones en los datos de texto.

### Paso 2: Corregir errores
1. Reemplazar valores erróneos:
   - Selecciona la columna que contiene el valor erróneo.
   - Haz clic derecho sobre la celda con el valor incorrecto y selecciona "Reemplazar valores".
   - Introduce el valor que deseas reemplazar y el nuevo valor. Haz clic en "Aceptar".
2. Eliminar filas con datos incorrectos:
   - Selecciona la fila que deseas eliminar haciendo clic en el número de fila.
   - Haz clic derecho y selecciona "Eliminar" para eliminar la fila completa.
3. Eliminar valores en blanco:
   - Filtra las columnas para mostrar solo las filas con valores en blanco (como se explicó antes).
   - Selecciona las filas y haz clic derecho para elegir "Eliminar filas".

## Transformación de Datos

### Paso 1: Renombrar columnas
1. En el Power Query Editor, haz doble clic en el nombre de la columna para renombrarla.
2. Escribe el nuevo nombre que sea claro y descriptivo. Repite este paso para todas las columnas que necesiten un nombre más adecuado.

### Paso 2: Organizar columnas
1. Reordena las columnas arrastrando la cabecera de la columna a la posición deseada.
2. Proporciona la razón de los cambios en las columnas, por ejemplo:
   - "Renombré la columna 'ID' a 'ClienteID' para clarificar que se refiere a la identificación del cliente."
   - "Moví la columna 'Fecha' al inicio para facilitar la referencia temporal en los análisis posteriores."

## Modelado de Datos

### Paso 1: Crear un modelo de datos
1. Cambia a la vista de modelo seleccionando el icono de "Modelo" en el panel izquierdo.
2. Crear relaciones:
   - Arrastra una columna de una tabla (por ejemplo, "ClienteID") y suéltala sobre la columna correspondiente en otra tabla.
   - Aparecerá una ventana de configuración de relación. Verifica las columnas y ajusta la cardinalidad si es necesario (por ejemplo, "Uno a muchos").
   - Haz clic en "Aceptar" para crear la relación.
3. Estructura de estrella:
   - Asegúrate de que tu tabla de hechos esté en el centro y que las tablas de dimensiones estén conectadas a ella en una disposición de estrella.

## Métricas de DAX

### Total de clientes
1. En la vista de informe, selecciona "Nueva Medida" en la pestaña "Modelado".
2. Escribe la siguiente fórmula DAX:
   ```DAX
   TotalClientes = COUNTROWS(Tabla)

