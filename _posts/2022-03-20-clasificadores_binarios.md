# Clasificadores binarios

Llamamos **prevalencia(P)** de una enfermedad al % real de la población afectada por ella.

$E\equiv persona \phantom{i} enferma$

$\overline{E}\equiv persona \phantom{i} sana$

Consideremos ahora un **test de diagnóstico(T)**

$T+\equiv test \phantom{i} positivo$

$T-\equiv test \phantom{i} negativo$

¿Cómo de bueno es nuestro test de diagnóstico?
Disponemos de algunos indicadores intrínsecos del test de diagnóstico, que son valores teóricos. 
Como estos indicadores no varían entre poblaciones, en sí mismos no tienen mucha utilidad práctica.
Más adelante veremos cómo encontrársela. La idea clave es ver cómo afecta a la bondad del test de
diagnóstico la variación de la prevalencia de la enfermedad en la población.

Estudiemos la *matriz de confusión* para este test de diagnóstico

||Personas Enfermas|Personas Sanas|
|-|-|-|
|**Test Positivo**|$VP\equiv verdadero \phantom{i} positivo$\\$E\cap{T+}$|$FP\equiv falso \phantom{i} positivo$\\$\overline{E}\cap{T+}$|
|**Test Negativo**|$FN\equiv falso \phantom{i} negativo$\\$E\cap{T-}$|$VN\equiv verdadero \phantom{i} negativo$\\$\overline{E}\cap{T-}$|

Se llama **sensibilidad del test(SE)** a la probabilidad de que el test de diagnóstico sea positivo en el grupo de personas enfermas

$$SE=P(T+/E)$$

Se llama **especificidad del test(SP)** a la probabilidad de que el test de diagnóstico sea negativo en el grupo de personas sanas

$$SP=P(T-/\overline{E})$$

De la teoría de detección de señales proceden las curvas ROC (Receiver Operating Characteristic) que representan la relación
entre los verdaderos positivos VP (*beneficios* del test) y los falsos positivos FP (*costes* del test) según se varía el umbral
de discriminación (valor a partir del cual decidimos que un caso es positivo).

$VPR\equiv proporcion/razon \phantom{i} de \phantom{i} Verdaderos \phantom{i} Positivos$ (entre las personas enfermas)

$FPR\equiv proporcion/razon \phantom{i} de \phantom{i} Falsos \phantom{i} Positivos$ (entre las personas sanas)

Llamamos curva ROC a la representación gŕafica de la funcion ROC

VPR=ROC(FPR)

SE=ROC(1-SP)

Cuando la detección es al azar SE=ROC(1-SP)=1-SP, entonces SE+SP=1

Cuando la detección es perfecta SE=ROC(1-SP)=1, entonces SE+SP=1+SP>=1

Un test de diagnóstico es más apropiado cuanto mayor es el **área bajo la curva** ROC

$AUC\equiv Area \phantom{i} Under \phantom{i} Curve \phantom{i} ROC$

El análisis ROC está directamente relacionado con el análisis coste/beneficio.

Pero en la práctica son mucho más útiles los llamados **VALORES PREDICTIVOS**.

Se llama **valor predictivo positivo del test(VP+)** a la probabilidad de que la persona esté enferma si el resultado del test ha dado positivo.

$$(VP+)=P(E/{T+})=VP/(VP+FP)$$

Se llama **valor predictivo negativo del test(VP-)** a la probabilidad de que la persona esté sana si el resultado del test ha sido negativo.

$$(VP-)=P(\overline{E}/{T-})=VN/(VN+FN)$$

Es muy interesante poder expresar estos valores predicitivos en función de la *prevalencia* de la enfermedad y de la 
*sensibilidad* y la *especificidad* del test de diagnóstico. Es decir, obtener las probabilidades a posteriori a partir de las probabilidades a priori.

Para obtener estas expresiones recordemos que dados dos sucesos independientes A y B sabemos que

$P(A\cap{B})={P(A)}\cdot{P(B)}$

sin embargo, en general, si los sucesos son dependientes

$P(A\cap{B})={P(A)}\cdot{P(B/A)}={P(B)}\cdot{P(A/B)}$

$P(A)=P(A\cap{(B\cup{\overline{B}})})=P((A\cap{B})\cup{(A\cap{\overline{B}})})=P(A\cap{B})+P(A\cap{\overline{B}})$

Entonces, aplicando estos razonamientos a los sucesos E y T+

$P(E\cap{T+})={P({T+})}\cdot{P(E/{T+})}={[P(E\cap{T+})+P({\overline{E}}\cap{T+})]}\cdot{P(E/{T+})}$

y así obtenemos que

$P(E/{T+})=\frac{P(E\cap{T+})}{P(E\cap{T+})+P({\overline{E}}\cap{T+})}=\frac{P(E)\cdot{P({T+}/E)}}{P(E)\cdot{P({T+}/E)}+{P({\overline{E}})\cdot{P({T+}/{\overline{E}})}}}$

O lo que es exactamente lo mismo

$(PV+)=P(E/{T+})=\frac{P\cdot{SE}}{P\cdot{SE}+(1-P)\cdot(1-SP)}$

Y análogamente

$(PV-)=P(\overline{E}/{T-})=\frac{(1-P)\cdot{SP}}{(1-P)\cdot{SP}+P\cdot(1-SE)}$
