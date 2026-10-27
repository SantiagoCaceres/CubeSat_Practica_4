# Avance OBC del 26 de octubre de 2026

Esta revisión conserva el trabajo guardado de Computador_Abordo.SchDoc e incorpora seis carpetas de librerías locales con sus archivos SchLib, PcbLib, IntLib y LibPkg. El proyecto referencia las librerías mediante rutas relativas. TOP y Comunicaciones se mantienen como en main b1b306a.

## Alcance del avance

- Interfaz I2C con EPS y adaptación mediante PCA9306.
- Interfaz USB 3 de cámara externa, conector, interruptor TPS2553 y protección ESD TPD6E05U06.
- Adaptación de RESET y tres señales de estado del radio mediante un segundo TXU0304.
- Actualización de las conexiones y componentes auxiliares del OBC. La revisión incluye también los bloques anteriores de microSD, SPI y UART.
- Requisito de alimentación acordado: 5,10 V ±1 % en la entrada de la placa, capacidad continua mínima de 4,5 A para SoM y rama USB. Este requisito no representa una medición de consumo.

## Comprobaciones realizadas para publicar

- Se descargó main y se incorporó a d-obc sin conflictos de integración.
- Se comprobó la existencia de las 28 rutas DocumentPath del proyecto.
- Se conservaron TOP, Comunicaciones y las librerías previamente versionadas de main.
- Se respaldaron los archivos locales antes de integrar. El guardado local de Comunicaciones presentaba cambios de identificadores y referencias cruzadas en los registros de texto; se conserva la versión de main para evitar ruido en la revisión.

Estas comprobaciones son de archivos e integración Git. **No se ejecutó la validación ERC en Altium ni se certificó la compatibilidad eléctrica, la resolución de todos los modelos o los footprints. No es una liberación para fabricación.**

## Pendientes de revisión

- Ejecutar ERC y revisión manual; corregir conflictos de nombres, designadores, puertos, alimentación y conectividad.
- Sustituir/validar el conector provisional de entrada de 5 V, incluidos su footprint, terminales y cable. La guía exige una huella válida para cada componente físico.
- Comprobar arranque del SoM, tratamiento de VCC_BACKUP, señales de control y acceso de programación, recuperación y depuración.
- Verificar continuidad de los puertos a través del TOP y la configuración del radio: GPIO0, GPIO2 y GPIO3 se han destinado a salidas del radio hacia entradas del OBC. Verificar RESET y SPI_CS durante el arranque.
- Comprobar secuencias de alimentación, posibles corrientes de retorno, márgenes lógicos, presupuesto de corriente y caídas de tensión, incluida la interfaz I2C y el cable USB.
- Verificar las referencias comerciales y la correspondencia entre símbolos y huellas; comprobar los componentes copiados y sus valores reales.
- Actualizar informe, cálculos, restricciones, BOM y costos a esta revisión; exportar esquemáticos PDF y guardar evidencia de validación.

El informe y las hojas de cálculo del repositorio de Daniel no se actualizaron como parte de esta publicación del proyecto de Santiago.
