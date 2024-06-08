# Power-BI
Práctica final
Vamos a abordar el proyecto paso a paso con todo el detalle necesario para que puedas seguirlo fácilmente en Power BI.

Preparación
Paso 1: Descargar los datos
Visita el enlace: Kaggle Marketing Campaign Dataset.
Inicia sesión en Kaggle o crea una cuenta si aún no tienes una.
Descarga el archivo CSV haciendo clic en el botón de descarga. Guarda el archivo en una ubicación accesible en tu computadora.
Paso 2: Configurar Power BI Desktop
Abre Power BI Desktop.
Guarda tu proyecto inmediatamente para evitar la pérdida de datos. Ve a "Archivo" > "Guardar" y elige una ubicación para tu archivo PBIX.
Proceso de Extracción, Transformación y Carga de Datos (ETL)
Extracción de datos
En Power BI Desktop, ve a la pestaña "Inicio" y selecciona "Obtener datos".
Selecciona "Texto/CSV".
Navega hasta la ubicación donde guardaste el archivo CSV descargado y selecciónalo. Haz clic en "Abrir".
Aparecerá una vista previa de los datos. Haz clic en "Cargar" para importar los datos a Power BI.
Transformaciones de datos
Abrir el Power Query Editor:
En la pestaña "Inicio", selecciona "Transformar datos".
Limpieza y transformación de datos
Revisar y cambiar los nombres de las columnas:

Haz doble clic en los nombres de las columnas para renombrarlas de manera más descriptiva. Por ejemplo, renombra "ID" a "ClienteID", "Income" a "Ingreso", etc.
Eliminar columnas o filas vacías:

Selecciona las columnas o filas vacías, haz clic derecho y selecciona "Eliminar".
Uso de Lenguaje M para transformaciones avanzadas:

En el editor de Power Query, puedes usar Lenguaje M para realizar transformaciones avanzadas. Por ejemplo, si deseas combinar columnas, puedes usar Table.CombineColumns.
Combinación y tratamiento de columnas:

Si tienes columnas que representan diferentes aspectos del mismo atributo, puedes combinarlas. Por ejemplo, si tienes "Estado Civil" y "Educación", puedes combinarlas usando "Combinar columnas".
Creación de tablas de dimensiones:

Para crear tablas de dimensiones, selecciona las columnas relevantes y crea una nueva tabla. Por ejemplo, puedes crear una tabla de dimensiones para "Estado Civil" y "Educación".
Carga de datos en el modelo:

Una vez completadas las transformaciones, haz clic en "Cerrar y aplicar" para cargar los datos transformados en el modelo de Power BI.
Desarrollo del Modelo de Datos
Implementar un modelo de datos adecuado
Crear un modelo de datos en estrella:
En la vista de modelo, asegúrate de que la tabla de hechos (la principal) esté en el centro y que las tablas de dimensiones estén conectadas a ella.
Métricas de DAX
Total de clientes:
Crea una medida en la tabla de hechos para contar los clientes:
DAX
Copiar código
TotalClientes = COUNTROWS(TablaDeHechos)
Ingreso medio de los clientes:
Crea una medida para calcular el ingreso promedio:
DAX
Copiar código
IngresoMedio = AVERAGE(TablaDeHechos[Ingreso])
Totales de compras por producto:
Crea una medida para calcular el total de compras por producto:
DAX
Copiar código
TotalComprasPorProducto = SUM(TablaDeHechos[Compras])
Totales por campañas:
Crea una medida para calcular el total por campañas:
DAX
Copiar código
TotalPorCampañas = SUM(TablaDeHechos[Campañas])
Creación de la tabla calendario
Crear una tabla calendario:
Ve a la vista de datos, haz clic derecho en el panel de tablas y selecciona "Nueva tabla".
Crea la tabla calendario usando DAX:
DAX
Copiar código
Calendario = 
ADDCOLUMNS (
    CALENDAR (DATE(2020, 1, 1), DATE(2023, 12, 31)),
    "Año", YEAR([Date]),
    "Mes", MONTH([Date]),
    "NombreMes", FORMAT([Date], "MMMM"),
    "Trimestre", QUARTER([Date])
)
Desarrollar Visualizaciones
Paso 1: Crear visualizaciones
Visión general de los datos:

Crea una página con gráficos que den una visión general de los datos, como ventas totales, número de clientes, etc.
Usa gráficos de líneas, barras, anillos, tablas y matrices.
Datos analizando las campañas:

Crea una página que se enfoque en el análisis de las campañas de marketing.
Usa gráficos de barras apiladas y tablas para mostrar el rendimiento de cada campaña.
Datos analizando los productos:

Crea una página que se enfoque en el análisis de los productos.
Usa gráficos de anillos y tablas para mostrar las ventas por producto.
Hoja cero oculta para anotaciones:

Agrega una nueva página y déjala en blanco para realizar anotaciones internas.
Paso 2: Configurar interacciones y filtros
Agregar filtros:

En cada visualización, usa el panel de filtros para agregar filtros de página o filtros de visualización.
Configurar interacciones:

Selecciona una visualización, luego en la pestaña "Formato" selecciona "Editar interacciones".
Configura cómo las visualizaciones interactúan entre sí para que las selecciones afecten adecuadamente a todas las visualizaciones relacionadas.
Publicar y compartir el informe
Paso 1: Publicar el informe
En la pestaña "Inicio", selecciona "Publicar".
Inicia sesión en tu cuenta de Power BI Service.
Selecciona el área de trabajo donde deseas publicar el informe y haz clic en "Seleccionar".
Paso 2: Compartir el enlace
Abre Power BI Service en tu navegador.
Navega hasta el informe publicado.
Selecciona "Archivo" > "Obtener enlace" y copia el enlace para compartirlo.
Entrega
Guardar el archivo PBIX.
Exportar el informe como PDF:
En Power BI Desktop, ve a "Archivo" > "Exportar" > "Exportar a PDF".
Crear un archivo con las métricas de DAX:
Utiliza DAX Studio para crear un archivo con las métricas solicitadas.
Comprimir los archivos en un ZIP y nómbralo con tu nombre y apellido. Asegúrate de que no supere los 20 MB.
Archivos a entregar
Archivo PBIX.
PDF exportado.
Archivo de DAX Studio con las métricas.
Siguiendo estos pasos detallados, deberías ser capaz de completar y entregar tu proyecto en Power BI. Si tienes alguna pregunta específica o necesitas más detalles en algún paso, no dudes en decírmelo.

Actividad 1: Carga de Datos
Paso 1: Descargar los datos
Visita el enlace: Kaggle Marketing Campaign Dataset.
Inicia sesión en Kaggle o crea una cuenta si aún no tienes una.
Descarga el archivo CSV haciendo clic en el botón de descarga. Guarda el archivo en una ubicación accesible en tu computadora.
Paso 2: Conectar los datos a Power BI
Abre Power BI Desktop.
En la pestaña "Inicio", selecciona "Obtener datos".
Selecciona "Texto/CSV".
Navega hasta la ubicación donde guardaste el archivo CSV descargado y selecciónalo. Haz clic en "Abrir".
Aparecerá una vista previa de los datos. Haz clic en "Cargar" para importar los datos a Power BI.
Paso 3: Revisar los datos en Power Query
En la pestaña "Inicio", selecciona "Transformar datos". Esto abrirá el Power Query Editor.
Revisa cada columna para entender su contenido y estructura. Verifica los nombres de las columnas y los datos que contienen.
Paso 4: Analizar y modificar los tipos de datos
Selecciona una columna para revisar su tipo de datos.
Para cambiar el tipo de datos, selecciona la columna, haz clic derecho y selecciona "Cambiar tipo". Elige el tipo de datos correcto (por ejemplo, "Fecha", "Número entero", "Texto").
Repite este paso para cada columna que necesite un cambio de tipo de datos.
Actividad 2: Limpieza de Datos
Paso 1: Buscar errores en los datos
Revisar valores atípicos:
Filtra las columnas numéricas para identificar valores que no sean realistas (por ejemplo, edades mayores de 100 años).
Haz clic en el icono de filtro en la cabecera de la columna y selecciona "Número de filtros" para buscar valores extremos.
Revisar datos en blanco:
Filtra las columnas para mostrar solo las filas que contienen valores en blanco. Haz clic en el icono de filtro y selecciona "Filtrar por valor" y luego marca la opción "(Blanks)".
Revisar errores de escritura:
Filtra columnas de texto para buscar inconsistencias en los nombres o categorías.
Usa el "Filtro de texto" en la cabecera de la columna para buscar variaciones en los datos de texto.
Paso 2: Corregir errores
Reemplazar valores erróneos:
Selecciona la columna que contiene el valor erróneo.
Haz clic derecho sobre la celda con el valor incorrecto y selecciona "Reemplazar valores".
Introduce el valor que deseas reemplazar y el nuevo valor. Haz clic en "Aceptar".
Eliminar filas con datos incorrectos:
Selecciona la fila que deseas eliminar haciendo clic en el número de fila.
Haz clic derecho y selecciona "Eliminar" para eliminar la fila completa.
Eliminar valores en blanco:
Filtra las columnas para mostrar solo las filas con valores en blanco (como se explicó antes).
Selecciona las filas y haz clic derecho para elegir "Eliminar filas".
Actividad 3: Transformación de Datos
Paso 1: Renombrar columnas
En el Power Query Editor, haz doble clic en el nombre de la columna para renombrarla.
Escribe el nuevo nombre que sea claro y descriptivo. Repite este paso para todas las columnas que necesiten un nombre más adecuado.
Paso 2: Organizar columnas
Reordena las columnas arrastrando la cabecera de la columna a la posición deseada.
Proporciona la razón de los cambios en las columnas, por ejemplo:
"Renombré la columna 'ID' a 'ClienteID' para clarificar que se refiere a la identificación del cliente."
"Moví la columna 'Fecha' al inicio para facilitar la referencia temporal en los análisis posteriores."
Actividad 4: Modelado de Datos
Paso 1: Crear un modelo de datos
Cambia a la vista de modelo seleccionando el icono de "Modelo" en el panel izquierdo.
Crear relaciones:
Arrastra una columna de una tabla (por ejemplo, "ClienteID") y suéltala sobre la columna correspondiente en otra tabla.
Aparecerá una ventana de configuración de relación. Verifica las columnas y ajusta la cardinalidad si es necesario (por ejemplo, "Uno a muchos").
Haz clic en "Aceptar" para crear la relación.
Estructura de estrella:
Asegúrate de que tu tabla de hechos esté en el centro y que las tablas de dimensiones estén conectadas a ella en una disposición de estrella.
Actividad 5: Visualizaciones
Paso 1: Crear visualizaciones
Visión general de los datos:
Selecciona el tipo de visualización (por ejemplo, gráfico de barras, gráfico de líneas) desde el panel "Visualizaciones".
Arrastra los campos correspondientes desde el panel "Campos" a las áreas de la visualización (Eje, Valores, Leyenda).
Crea gráficos que muestren una visión general de los datos, como ventas totales, número de clientes, etc.
Datos analizando las campañas:
Crea visualizaciones específicas que muestren el rendimiento de cada campaña (por ejemplo, un gráfico de barras que muestre ventas por campaña).
Utiliza filtros para permitir la selección de diferentes campañas.
Datos analizando los productos:
Crea visualizaciones que muestren las ventas por producto (por ejemplo, un gráfico de pastel o barras).
Hoja cero oculta:
Agrega una nueva página y déjala en blanco para anotaciones internas.
Paso 2: Configurar interacciones y filtros
Agregar filtros:
Usa el panel de filtros para agregar filtros de página o filtros de visualización.
Configurar interacciones:
Selecciona una visualización, luego en la pestaña "Formato" selecciona "Editar interacciones".
Configura cómo las visualizaciones interactúan entre sí (por ejemplo, hacer que una selección en un gráfico de barras filtre un gráfico de líneas).
Publicar y compartir el informe
Paso 1: Publicar el informe
En la pestaña "Inicio", selecciona "Publicar".
Inicia sesión en tu cuenta de Power BI Service si aún no lo has hecho.
Selecciona el área de trabajo donde deseas publicar el informe y haz clic en "Seleccionar".
Paso 2: Compartir el enlace
Abre Power BI Service en tu navegador.
Navega hasta el informe publicado.
Selecciona "Archivo" > "Obtener enlace" y copia el enlace para compartirlo.
Métricas de DAX mínimas:
Total de clientes:
En la vista de informe, selecciona "Nueva Medida" en la pestaña "Modelado".
Escribe la siguiente fórmula DAX:
DAX
Copiar código
TotalClientes = COUNTROWS(Tabla)
Ingreso medio de los clientes:
Selecciona "Nueva Medida" en la pestaña "Modelado".
Escribe la siguiente fórmula DAX:
DAX
Copiar código
IngresoMedio = AVERAGE(Tabla[Ingreso])
Totales de compras por producto:
Selecciona "Nueva Medida" en la pestaña "Modelado".
Escribe la siguiente fórmula DAX:
DAX
Copiar código
TotalComprasPorProducto = SUM(Tabla[Compras])
Entrega
Guardar el archivo PBIX.
Exportar el informe como PDF:
En Power BI Desktop, ve a "Archivo" > "Exportar" > "Exportar a PDF".
Crear un archivo con las métricas de DAX:
Utiliza DAX Studio para crear un archivo con las métricas solicitadas.
Comprimir los archivos en un ZIP y nómbralo con tu nombre y apellido. Asegúrate de que no supere los 20 MB.
Archivos a entregar
Archivo PBIX.
PDF exportado.
Archivo de DAX Studio con las métricas.
