+++
title = "PRINCIPIOS DE LA INGENIERIA DEL CAOS"
date = 2020-01-28T16:25:57+02:00
draft = false
+++

# PRINCIPIOS DE LA INGENIERIA DEL CAOS
Última actualización: Enero de 2021

_La Ingeniería del Caos es la disciplina de experimentar en un Sistema, con la finalidad de generar confianza en la capacidad del Sistema para soportar condiciones turbulentas en producción._

Los avances en sistemas de software distribuidos a gran escala están cambiando el juego para la ingeniería de software.  Como industria, somos rápidos en adoptar prácticas que aumentan la flexibilidad de desarrollo y la velocidad de despliegue.  Una pregunta urgente sigue de cerca a estos beneficios: ¿cuánta confianza podemos tener en los sistemas complejos que ponemos en producción?

Incluso cuando todos los servicios individuales de un sistema distribuido funcionan correctamente, las interacciones entre ellos pueden causar resultados impredecibles.  Estos resultados impredecibles, agravados por los raros pero disruptivos eventos del mundo real que afectan a los entornos de producción, hacen que estos sistemas distribuidos sean inherentemente caóticos.

Necesitamos identificar las debilidades antes de que se manifiesten en comportamientos aberrantes en todo el sistema.  Las debilidades sistémicas podrían tomar la forma de: fallbacks incorrectos cuando un servicio no está disponible; tormentas de reintentos debido a timeouts mal configurados; interrupciones cuando una dependencia downstream recibe demasiado tráfico; fallas en cascada cuando hay un crash en un punto único de fallo; Etc.  Debemos abordar las debilidades más significativas de manera proactiva, antes de que afecten a nuestros clientes en producción.  Necesitamos una manera de gestionar el caos inherente a estos sistemas, aprovechar la flexibilidad y la velocidad crecientes, y tener confianza en nuestros despliegues a  producción a pesar de la complejidad que representan.

Un enfoque empírico basado en sistemas aborda el Caos en los sistemas distribuidos a escala y aumenta la confianza en la capacidad de esos sistemas para resistir condiciones realistas.  Aprendemos sobre el comportamiento de un sistema distribuido observándolo durante un experimento controlado.  Llamamos a esto Ingeniería del Caos.

## EL CAOS EN LA PRÁCTICA

Para abordar específicamente la incertidumbre de los sistemas distribuidos a escala, se puede pensar en la Ingeniería del Caos como la facilitación de experimentos para descubrir debilidades sistémicas. Estos experimentos siguen cuatro pasos: 

1. Comenzar definiendo un estado estacionario como una salida medible de un sistema que indica el comportamiento normal.
2. Hipotetizar que este estado estacionario continuará tanto en el grupo de control como en el grupo experimental.
3. Introducir variables que reflejan eventos del mundo real como servidores que dejan de funcionar, discos rígidos que funcionan mal, conexiones de red que están cortadas, etc.
4. Tratar de refutar la hipótesis buscando una diferencia en el estado estacionario entre el grupo de control y el grupo experimental.
Cuanto más difícil es interrumpir el estado estacionario, más confianza tenemos en el comportamiento del sistema. Si se descubre una debilidad, tenemos ahora un objetivo de mejora antes de que ese comportamiento se manifieste en el Sistema en general.

## PRINCIPIOS AVANZADOS

Los siguientes principios describen una aplicación ideal de la Ingeniería del Caos, aplicada a los procesos de experimentación descritos anteriormente. El grado en que se persiguen estos principios se correlaciona fuertemente con la confianza que podemos tener en un sistema distribuido a escala.

### Construir una hipótesis alrededor del comportamiento del estado estacionario

Céntrese en la salida medible de un sistema, en lugar de los atributos internos del mismo. Las mediciones de esa salida durante un período corto de tiempo constituyen una representación para el estado estacionario del sistema. El rendimiento del sistema general, las tasas de error, los percentiles de latencia, etc., podrían ser métricas de interés que representen un comportamiento de estado estacionario. Al centrarse en los patrones de comportamiento sistémico durante los experimentos, el caos comprueba que el sistema funciona, en lugar de intentar validar cómo funciona.

### Varíe los eventos del mundo real

Las variables del Caos reflejan eventos del mundo real. Priorizar los eventos ya sea por impacto potencial o frecuencia estimada. Considere los eventos que corresponden a fallas de hardware como servidores que mueren, fallas de software como respuestas malformadas y eventos de no-falla como un aumento en el tráfico o un evento de escalado. Cualquier evento capaz de interrumpir el estado estacionario es una variable potencial en un experimento de Caos.

### Ejecute los experimentos en producción

Los sistemas se comportan de manera diferente dependiendo del entorno y patrones de tráfico. Dado que el comportamiento de la utilización puede cambiar en cualquier momento, el muestreo de tráfico real es la única manera de capturar de forma fiable la ruta de las peticiones. Para garantizar la autenticidad de la forma en que se experimenta con el sistema y su relevancia para el sistema implementado actualmente, el Caos prefiere experimentar con el tráfico de producción.

### Automatice los experimentos para que se ejecuten continuamente

Ejecutar los experimentos manualmente es muy trabajoso y en última instancia insostenible. Automatice sus experimentos y ejecútelos continuamente. La Ingeniería del Caos construye automatización en el sistema para impulsar tanto la orquestación como el análisis.

### Minimice el radio de explosión

Experimentar en producción tiene el potencial de causar dolor innecesario para el cliente. Si bien debe contarse con un margen para algún impacto negativo a corto plazo, es responsabilidad y obligación del Ingeniero del Caos asegurar que las consecuencias de los experimentos sean minimizadas y contenidas.

La Ingeniería del Caos es una práctica poderosa que ya está cambiando el diseño y la ingeniería de software en algunas de las operaciones de mayor escala en el mundo. Mientras otras prácticas tratan la velocidad y la flexibilidad, el Caos aborda específicamente la incertidumbre sistémica en estos sistemas distribuidos. Los Principios del Caos proporcionan confianza para innovar rápidamente a escalas masivas y dar a los clientes las experiencias de alta calidad que merecen. Únase a la discusión continua de los Principios del Caos y su aplicación en el Grupo de Google [Chaos Community](https://groups.google.com/forum/#!forum/chaos-community).


_Traducción al español de [Principles of Chaos Engineering](https://principlesofchaos.org/) por Rodrigo Julián Martín_