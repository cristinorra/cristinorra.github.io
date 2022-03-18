# Primeras ideas interesantes

En un sistema basado en un red neuronal el comportamiento del sistema emerge del intento del modelo de ajustarse a los datos de entrenamiento.

Nos encontramos con el problema de los *datos fuera del dominio* de entrenamiento cuando nuestro modelo se enfrenta en producción a datos muy diferentes de los de entrenamiento. No hay una solución perfecta para abordar este problema.

El problema del *desplazamiento del dominio* se produce cuando el tipo de datos a los que se enfrenta nuestro modelo va cambiando a medida que pasa el tiempo.

Se trata de dos ejemplos de un problema más general, debido al inmenso número de parámetros de una red neuronal no podemos comprender completamente su comportamiento. Y ésta es la desventaja natural de la principal característica de las redes neuronales, su flexibilidad. Que les permite resolver problemas complejos allí donde nosotros no somos capaces diseñar una solución bien definida.

¿Cómo mitigar estos riesgos? Controlando el proceso de puesta en producción
1. PROCESO MANUAL
- Ejecutar el modelo en paralelo
- Comprobar todas las predicciones por un experto humano
2. LIMITAR EL AMBITO DE DESPLIEGUE
- Cuidadosa supervisión humana
- Despliegue limitado en el tiempo o en el espacio
3. EXPANSION GRADUAL
- Previamente se necesitan buenos sistemas de reporte
- Reflexionar sobre qué podría ir mal

