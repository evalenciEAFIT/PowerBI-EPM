# PowerBI-EPM


# Generador de Datos de Consumo de Energía y Agua para Visualización

Este programa en Python genera un conjunto de datos simulado sobre el consumo de energía y agua en hogares ubicados en tres ciudades colombianas: Medellín, Manizales y Pereira. Los datos se pueden utilizar en herramientas de visualización de datos como Power BI para analizar el impacto de las condiciones climáticas y diferentes escenarios de cambio climático en el consumo y generación de recursos.

## Propósito

El programa tiene como objetivo proporcionar datos de prueba para ejercicios de visualización y análisis. El modelo de datos incluye información sobre el consumo de energía convencional, la generación de energía solar y eólica, el consumo de agua convencional, y el agua autogenerada (purificación de aguas residuales y recolección de aguas lluvias). Además, proyecta el consumo bajo diferentes escenarios climáticos.

## Características

1. **Datos de Consumo**:
   - Consumo de energía (convencional y autogenerada) basado en condiciones climáticas.
   - Generación de agua autogenerada, diferenciando entre agua purificada de residuos y agua recolectada de lluvias.

2. **Condiciones Climáticas**:
   - Información mensual de temperatura, precipitación, horas de sol, y velocidad del viento, ajustada por ciudad.

3. **Proyecciones de Consumo**:
   - Escenarios de cambio climático para el año 2024, simulando condiciones como aumento de calor, sequía prolongada y eventos de viento extremo.

## Requisitos de Instalación

Antes de ejecutar el programa, asegúrate de tener instaladas las siguientes librerías:

```bash
pip install pandas numpy openpyxl
```

Estas librerías permiten la manipulación de datos y la exportación de archivos en formato Excel (`.xlsx`).

## Algoritmos y Pseudocódigo

### Generación de Datos para los Hogares

**Algoritmo**: `generar_datos_hogares`  
**Descripción**: Genera datos para hogares y condiciones climáticas. Calcula el consumo de energía y agua en función de factores climáticos y produce un archivo Excel con varias hojas de datos.

**Pseudocódigo**:

```
1. Para cada hogar, generar:
    - Ubicación, coordenadas geográficas, tipo de zona y tipo de autogeneración de energía.
2. Para cada combinación de hogar, mes y año, generar condiciones climáticas:
    - Temperatura, precipitación, horas de sol y velocidad del viento.
3. Calcular consumo de energía y agua basado en condiciones climáticas.
4. Ajustar agua recolectada según el nivel de lluvia.
5. Generar proyecciones para escenarios climáticos futuros.
6. Guardar todos los datos en un archivo Excel con varias hojas.
```

### Cálculo de Agua Autogenerada

**Algoritmo**: `calcular_agua_autogenerada`  
**Descripción**: Calcula el volumen de agua autogenerada en función de los sistemas de purificación de aguas residuales y recolección de lluvias.

**Pseudocódigo**:

```
1. Inicializar agua purificada con un valor aleatorio (1-5 m³).
2. Para cada nivel de lluvia:
    - Si la lluvia es ligera, añadir 1 m³ a agua recolectada.
    - Si la lluvia es moderada, añadir 3 m³.
    - Si la lluvia es fuerte, añadir 6 m³.
3. Retornar la suma de agua purificada y agua recolectada.
```

### Cálculo de Proyecciones Climáticas

**Algoritmo**: `calcular_proyecciones_climaticas`  
**Descripción**: Proyecta el consumo de energía y agua bajo distintos escenarios climáticos.

**Pseudocódigo**:

```
1. Seleccionar un escenario climático: Aumento de Calor, Sequía Prolongada, o Viento Extremo.
2. Basado en el escenario, ajustar los valores proyectados de:
    - Energía convencional, energía autogenerada, agua convencional y agua autogenerada.
3. Guardar las proyecciones en la hoja de proyecciones del archivo Excel.
```

## Uso del Programa

1. **Ejecuta el Programa**: Ejecuta el archivo de Python en tu terminal con el siguiente comando:
   ```bash
   python generador_datos.py
   ```

2. **Ingresa los Parámetros Solicitados**:
   - `Número de hogares a generar`: Cantidad de registros de hogares que deseas incluir en el conjunto de datos.
   - `Nombre del archivo de salida`: Nombre del archivo `.xlsx` que se generará (sin la extensión).

3. **Salida**: El programa generará un archivo `.xlsx` con el nombre especificado. Este archivo contendrá varias hojas de datos, cada una con información específica sobre consumo, clima y proyecciones.

## Estructura del Archivo de Salida

El archivo de salida en formato Excel (`.xlsx`) incluye las siguientes hojas:

- **Hogares**: Contiene información básica de cada hogar, como ubicación geográfica, tipo de zona (urbana o suburbana), y tipo de autogeneración de energía.
  
- **Consumo_Mensual**: Datos mensuales de consumo de energía y agua, ajustados en función de las condiciones climáticas.
  
- **Clima**: Condiciones climáticas como temperatura, precipitación, horas de sol, y velocidad del viento.
  
- **Necesidades_Consumo**: Estimación de la demanda de energía y agua por hogar, considerando factores climáticos y tamaño del hogar.
  
- **Proyeccion_Escenarios**: Proyecciones de consumo en diferentes escenarios climáticos para el año 2024.

## Ejemplo de Ejecución

```bash
python generador_datos.py
```

**Ejemplo de Parámetros:**
```
Ingrese el número de hogares a generar: 100
Ingrese el nombre del archivo de salida (sin extensión): datosDemo
```

Esto generará un archivo `datosDemo.xlsx` con 100 registros de hogares y datos climáticos simulados para análisis.

## Notas

1. **Personalización**: Puedes modificar los parámetros del modelo de datos en el código para personalizar los valores de consumo y generación.
2. **Manejo de Errores**: El programa verifica que `openpyxl` esté instalado para la creación de archivos Excel. Si no está instalado, se mostrará un mensaje explicativo.
   
## Autor

Este programa fue diseñado para proporcionar datos de ejemplo de consumo de energía y agua para proyectos de visualización y análisis de datos.

---

Este archivo `README.md` describe detalladamente el propósito, la estructura del archivo de salida, y las instrucciones de uso del programa, así como los algoritmos y pseudocódigo de los métodos principales.
