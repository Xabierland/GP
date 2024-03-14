<!-- markdownlint-disable MD004 -->
# Tema 5 - Estimación de esfuerzo en desarrollo de software

- [Tema 5 - Estimación de esfuerzo en desarrollo de software](#tema-5---estimación-de-esfuerzo-en-desarrollo-de-software)
  - [Introducción](#introducción)
  - [Metodos para la estimación](#metodos-para-la-estimación)
  - [Puntos de Función](#puntos-de-función)
  - [COCOMO II](#cocomo-ii)

## Introducción

* Conocer el coste de desarrollo de un sistema
  * Esfuerzo
  * Dinero
  * ...
* Queremos saberlo cuanto antes para asignar tareas y personas

## Metodos para la estimación

* Experiencia
  * Juicio de experto
    * Puro
      * Un experto, en base a sus conocimientos, hace una estimación.
    * Delphi
      * Un grupo de expertos, debate, cada uno hace una estimación y se llega a un consenso mediante un coordinador. Si no se llega a un consenso, se repite el proceso.
    * Wideband Delphi
      * Igual que el Delphi pero los miembros deben dar explicaciones de sus estimaciones.
  * Estimación multipunto
    * Forma de estimar basada la opción optimista, pesimista y la media.
    * ![Image](./img/1.png)
  * Analogia
    * Comparar el proyecto con otros similares teniendo en cuenta las diferencias.
      * Tamaño
      * Complejidad
      * Usuarios
      * ...
  * Distribución de la utilización de recursos en el ciclo de vida
    * Se coge la estimación de un proyecto similar y se divide en las mismas fases.
* Recursos
  * Parkinson
    * La estimación depende del numero de personas y del tiempo que se tienen.
    * > "El trabajo se expande hasta consumir todos los recursos disponibles" -> Ley de Parkinson
* Mercado
  * Precio para vender
    * Se prioriza obtener el contrato ajustando el precio al pago. Peligroso como única estimación.
* Componentes del producto
  * Bottom-up
    * Descomponer el proyecto en unidades lo mas pequeñas posible y estimar cada unidad.
  * Top-down
    * Se estima el proyecto completo y se descompone en tareas teniendo en cuenta la estimacion.
* Algoritmos
  * Puntos de Función
  * COCOMO II

## Puntos de Función

* Identificación de elementos y clasificación
  * Relacionados con los datos
    * Ficheros Logicos Internos (FLI)
      * Grupo de datos mantenidos por el sistema
        * Tablas de una base de datos
        * Ficheros
    * Ficheros de Interfaz Externos (FIE)
      * Grupo de datos mantenidos por otro sistema
      * Fichero Logico Interno de otro sistema
  * Relacionados con las transacciones
    * Entradas Externas (EE)
      * Proceso que hace llegar datos desde el exterior al sistema
      * Actualiza los FLI
        * Pantallas de entrada de datos
        * Codigos de barras
    * Salidas Externas (SE)
      * Proceso que hace llegar datos desde el sistema al exterior
      * Procesa datos, no solo los muestra
        * Informes
        * Listados
        * Graficos
    * Consultas Externas (CE)
      * Combinación de EE y SE
      * Ni modifica ni añade datos
        * Obtener datos para solo mostrarlos
* Cálculo de los puntos de funcion no ajustados (PFNA)
  * Se estudia cada elemento de funcion y se identifica sus componentes
  * Se calcula los PFNA de cada elemento de funcion
* Cálculo del factor de ajuste (FA)
  * Se calcula basado en catorce caracterisicas
    1. Comunicación de datos
    2. Procesamiento distribuido
    3. Prestaciones
    4. Facilidad de Configuración
    5. Tasa de transacciones
    6. Entrada de datos en linea
    7. Diseño Eficiencia requerida del usuario final
    8. Actualización en linea
    9. Procesamiento complejo
    10. Reusabilidad
    11. Facilidad de instalación
    12. Facilidad operacional
    13. Adaptabilidad a multiples sitios
    14. Facilidad de cambio
* Cálculo de los puntos de función ajustados (PFA)

## COCOMO II

* COnstructive COst MOdel
* Modelo de estimación de costes mas utilizado
* Objetivos
  * Estimacion de tiempo y coste de acuerdo a los ciclos de vida
  * Construir una base de datos de proyectos para calibrar el modelo e incrementar la precisión
* Tres modelos
  * ACM - Composición de aplicaciones
    * Se decide en la etapa de planificación
    * Ya se debe tener una idea de la arquitectura
    * Principalmente para constuir interfaces graficas
    * Utiliza Puntos de Objeto
      * Estima la cantidad de pantallas, informes y componentes.
      * Clasifica segun la complejidad
      * Se suman todos los puntos
      * Se estima el porcentaje de codigo a reusar.
      * Calcula el ratio de la productividad
      * Se calcula el esfuerzo
  * EDM - Diseño Temprano
    * Primeras etapas
    * Cuando se tiene poca informacion sobre el proyecto
    * Basado en puntos de funcion no ajustados
    * Se convierte los PFNA en lineas de codigo
    * Se usan 7 drivers para ajustarlo.
      * Calcular los PFNA
      * Convertir los PFNA a miles de lineas de codigo
      * Calcular el esfuerzo
      * Se ajusta el esfuerzo
  * PAM - Post-Arquitectura
    * El mas detallado
    * Ya se conoce la arquitectura completa
    * Tiene 17 factores de ajuste
      * Calcular los PFNA
      * Convertir los PFNA a miles de lineas de codigo
      * Calcular el esfuerzo
      * Se ajusta el esfuerzo
