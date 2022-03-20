# Clasificadores binarios

Llamamos **prevalencia(P)** de una enfermedad al % real de la población afectada por ella.

<img src="https://latex.codecogs.com/svg.image?E\equiv{individuoEnfermo}" />
<img src="https://latex.codecogs.com/svg.image?\bar{E}\equiv{individuoSano}" />

Consideremos ahora un **test de diagnóstico(T)**

<img src="https://latex.codecogs.com/svg.image?{T+}\equiv{testPositivo}" />
<img src="https://latex.codecogs.com/svg.image?{T-}\equiv{testNegativo}" />

Disponemos de algunos valores intrínsecos del test de diagnóstico, que son valores teóricos. 
Como estos valores no varían entre poblaciones, en sí mismos no tienen mucha utilidad práctica.

Estudiemos la *matriz de confusión* para este test de diagnóstico
||Personas Enfermas|Personas Sanas|
|-|-|-|
|**Test Positivo**|<img src="https://latex.codecogs.com/svg.image?{VP}\equiv{verdaderoPositivo}" />|<img src="https://latex.codecogs.com/svg.image?{FP}\equiv{falsoPositivo}" />|
|**Test Negativo**|<img src="https://latex.codecogs.com/svg.image?{FN}\equiv{falsoNegativo}" />|<img src="https://latex.codecogs.com/svg.image?{VN}\equiv{verdaderoNegativo}" />|

Se llama **sensibilidad(SE)** a la probabilidad de que el test de diagnóstico sea positivo en el grupo de personas enfermas

<img src="https://latex.codecogs.com/svg.image?{SE}=P(T+/E)" />

Se llama **especificidad(SP)** a la probabilidad de que el test de diagnóstico sea negativo en el grupo de personas sanas

<img src="https://latex.codecogs.com/svg.image?{SP}=P(T-/\bar{E})" />

De la teoría de detección de señales proceden las curvas ROC (Receiver Operating Characteristic) que representan la relación
entre los verdaderos positivos VP (*beneficios* del test) y los falsos positivos FP (*costes* del test) según se varía el umbral
de discriminación (valor a partir del cual decidimos que un caso es positivo).

<img src="https://latex.codecogs.com/svg.image?{VPR}\equiv{proporcionRazonVerdaderosPositivos}" /> (entre las personas enfermas)

<img src="https://latex.codecogs.com/svg.image?{FPR}\equiv{proporcionRazonFalsosPositivos}" /> (entre las personas sanas)

Llamamos curva ROC a la representación gŕafica de la funcion ROC

VPR=ROC(FPR)

SE=ROC(1-SP)

Cuando la detección es al azar SE=ROC(1-SP)=1-SP, entonces SE+SP=1

Cuando la detección es perfecta SE=ROC(1-SP)=1, entonces SE+SP=1+SP>=1

Un test de diagnóstico es más apropiado cuanto mayor es el **área bajo la curva** ROC,
<img src="https://latex.codecogs.com/svg.image?{AUC}\equiv{AreaUnderCurveROC}" />

El análisis ROC está directamente relacionado con el análisis coste/beneficio.

Pero en la práctica son mucho más útiles los llamados **VALORES PREDICTIVOS**.

Se llama **valor predictivo positivo del test(VP+)** a la probabilidad de que la persona esté enferma si el resultado del test ha dado positivo.

<img src="https://latex.codecogs.com/svg.image?{(VP+)}=P(E/{T+})=VP/(VP+FP)" />

Se llama **valor predictivo negativo del test(VP-)** a la probabilidad de que la persona esté sana si el resultado del test ha sido negativo.

<img src="https://latex.codecogs.com/svg.image?{(VP-)}=P(\bar{E}/{T-})=VN/(VN+FN)" />

Es muy interesante poder expresar estos valores predicitivos en función de la *prevalencia* de la enfermedad y de la 
*sensibilidad* y la *especificidad* del test diagnóstico. Es decir, obtener las probabilidades a posteriori a partir de las probabilidades a priori.

Para obtener estas expresiones recordemos que dados dos sucesos independientes A y B sabemos que

<img src="https://latex.codecogs.com/svg.image?P(A\cap{B})={P(A)}\cdot{P(B)}" />

sin embargo, en general, si los sucesos son dependientes

<img src="https://latex.codecogs.com/svg.image?P(A\cap{B})={P(A)}\cdot{P(B/A)}={P(B)}\cdot{P(A/B)}" />
<img src="https://latex.codecogs.com/svg.image?P(A)=P(A\cap{(B\cup{\bar{B}})})=P((A\cap{B})\cup{(A\cap{\bar{B}})})=P(A\cap{B})+P(A\cap{\bar{B}})" />

Entonces, aplicando estos razonamientos a los sucesos E y T+

<img src="https://latex.codecogs.com/svg.image?P(E\cap{T+})={P(T+)}\cdot{P(E/T+)}={[P(E\cap{T+})+P({\bar{E}}\cap{T+})]}\cdot{P(E/T+)}" />

y así obtenemos que

<img src="https://latex.codecogs.com/svg.image?P(E/T+)=\frac{P(E\cap{T+})}{P(E\cap{T+})+P({\bar{E}}\cap{T+})}=\frac{P(E)\cdot{P({T+/E})}}{{P(E)\cdot{P({T+/E})}}+{P({E})\cdot{P({{T+}/{E}})}}}" />

