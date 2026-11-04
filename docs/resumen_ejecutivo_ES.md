# Tienda en línea de Google · Análisis de marketing digital: canales, embudo de compra y dispositivos (septiembre 2026)

**Autora:** Dámaris Cubos Rosas · **Herramientas:** Google Analytics 4 (GA4) · Looker Studio
**Datos:** cuenta de demostración de GA4 de la Google Merchandise Store · 1 al 30 de septiembre de 2026 · 137.067 sesiones · 1.921 compras · ingresos de USD 340.182 (cifras en dólares; la cuenta demo redondea algunos valores)

---

## 🎯 Mensaje principal

> **El 94% de las compras proviene de Estados Unidos, a pesar de que hay países con muchas sesiones y casi ninguna compra. Conviene verificar a qué países envía la tienda antes de decidir las acciones de marketing. Además, solo 24% de los usuarios que inician el pago en mobile finaliza la compra, frente a 53% en desktop; se recomienda probar el pago en mobile y compararlo con desktop para identificar la causa.**

---

## 1. Contexto

La tienda en línea de Google vende productos con su marca. Se planteó un **caso de negocio simulado**: la directora de marketing debe decidir en qué canales, dispositivos y países enfocar el esfuerzo del próximo trimestre. Las preguntas se definieron al inicio, antes de ver los datos:

1. ¿Qué canales generan más compras e ingresos, y cuáles traen muchas sesiones con pocas compras?
2. ¿En qué paso del recorrido de compra (ver producto → agregar al carrito → iniciar el pago → comprar) abandonan más las personas?
3. ¿Qué dispositivos y qué países generan más compras, tanto en total como en proporción a sus sesiones?

**Palabras clave:** una **sesión** es una visita al sitio (un mismo usuario puede tener varias). Un **canal** es el camino por el que la persona llegó (buscador, anuncios, enlaces de otros sitios, etc.). El **embudo de compra** son los pasos que sigue una persona hasta comprar; en cada paso se pierde gente.

---

## 2. Hallazgos principales

### 📣 Canales (Pregunta 1)
- **Dos canales traen casi todo:** Direct (la persona llega sin que GA4 pueda identificar el origen) y Organic Search (clic en un resultado no pagado de un buscador) suman **87% de las sesiones y 87% de los ingresos**. El negocio depende de dos canales.
- **Paid Search (anuncios en buscadores) y Unassigned (GA4 no pudo asignar un canal) traen 11% de las sesiones, pero solo 3% de las compras.** Su promedio es 0,37% y 0,49% de compras por sesión, contra 1,4% del sitio completo.
- Los canales pequeños (redes sociales, video, email, shopping, cross-network) muestran tasas altas o raras, pero con muy pocas sesiones (menos de 1.000 cada uno): **no se concluye nada de ellos**. Referral (enlaces desde otros sitios) tiene la mayor tasa de compras por sesión (3,56%) entre los canales con 1.000 sesiones o más (2.415 sesiones), pero merece una revisión propia.

### 🛒 Embudo de compra (Pregunta 2)
- **De quienes ven un producto, 70% no lo agrega al carrito.** Es la mayor pérdida, pero puede ser comportamiento normal de quien solo está mirando.
- **De quienes inician el pago, 52% no compra.** Esta pérdida es más costosa, porque esa persona ya mostró intención de compra.
- **La brecha por dispositivo es grande:** de quienes inician el pago, compra **24% en mobile y 53% en desktop**. Se mantiene dentro de un mismo canal (en Organic Search: 16,4% en mobile y 41,9% en desktop), así que no se explica solo por qué canal trae a la gente.
- Mi hipótesis inicial era que la mayor pérdida estaba en el pago. **Se cumplió a medias:** el paso con más abandono es ver el producto → carrito, aunque el abandono en el pago es el más costoso.

### 📱 Dispositivos y países (Pregunta 3)
- **Mobile trae 65% de los usuarios, pero desktop concentra 92% de las compras.**
- Sin contar las sesiones sin país identificado, **desktop convierte 2,8% de sus sesiones en compra y mobile 0,5%**. La diferencia se reduce al quitar ese tráfico dudoso, pero persiste.
- **Estados Unidos concentra 94% de las compras** con 39% de las sesiones. Ningún otro país con 1.000 sesiones o más llega al promedio de 1,4% de compras por sesión.
- Tablet y smart tv tienen menos de 1.000 sesiones: son muestras pequeñas y no se interpretan.

### ⚠️ Hallazgo inesperado: tráfico sin ubicación
- **32% de las sesiones (43.403) no tiene país identificado ("not set") y no generó ninguna compra.** Casi todas son de Direct y de mobile, y casi no ven productos.
- Infla las **sesiones**, no las **compras ni los ingresos**: sin ese grupo, las compras por sesión del sitio suben de 1,4% a ≈ 2,05%. Esto explica por qué Direct y mobile parecen "malos" en porcentajes. Por eso el dashboard excluye ese grupo al comparar dispositivos y países, y lo avisa con una nota.

---

## 3. Recomendaciones

| # | Recomendación | Por qué (dato) | Qué no sabemos / dato que falta |
|---|---|---|---|
| 1a | **💰 Paid Search: comparar el costo de los anuncios con los ingresos que generó el canal** y, si el costo es parecido o mayor, evaluar reducir o rediseñar la inversión. | Paid Search: 11% de las sesiones combinadas con Unassigned, solo 3% de las compras; ingresos del canal USD 7.618 en el mes. | No se conoce el costo de los anuncios; falta ese dato antes de decidir. Ingresos no es ganancia: la cifra es una señal, no una prueba. |
| 1b | **🏷️ Unassigned: pedir al equipo de marketing que revise el etiquetado de los enlaces** (las marcas que permiten a GA4 saber de qué canal viene cada sesión). | GA4 no pudo identificar el canal de 7.296 sesiones. | No se sabe por qué aparece sin canal; el etiquetado es una hipótesis por confirmar. |
| 2 | **🛒 Probar el proceso de pago desde un celular**, revisar si los medios de pago funcionan igual en mobile y en desktop, y verificar en GA4 si hay un registro que permita ver **en qué parte exacta del pago** se pierde la compra. | De quienes inician el pago: compra 24% en mobile y 53% en desktop. | No se conoce la razón del abandono; las hipótesis son un proceso poco claro o pocos medios de pago. El 70% perdido entre ver el producto y el carrito queda pendiente de investigar (puede ser comportamiento normal). |
| 3 | **🌎 Verificar a qué países envía la tienda** antes de decidir si el marketing se enfoca en fortalecer Estados Unidos o en otros países con muchas sesiones. **📱 Probar la usabilidad en mobile y compararla con desktop** (misma revisión que la recomendación 2). | Estados Unidos: 94% de las compras. Desktop convierte 2,8% de sus sesiones y mobile 0,5%. | No se sabe a qué países envía la tienda, ni si las sesiones de países con casi ninguna compra son de baja calidad. Tampoco se sabe si la brecha de mobile se debe a mala experiencia o a personas que miran en el celular y compran después en desktop. |
| 4 | **🔎 Revisar el origen de las sesiones sin país** (equipo de marketing/analítica) y, mientras tanto, **reportarlas por separado y excluirlas del cálculo de conversión**, explicando por qué. | 32% de las sesiones no tiene país identificado y no generó ninguna compra. | No se sabe si es tráfico automático, sesiones sin ubicación por privacidad o mal etiquetado; la revisión debe confirmarlo antes de decidir. |

*Estas recomendaciones no incluyen metas numéricas ni estimaciones de impacto porque la cuenta demo no tiene costos de publicidad ni de productos. Las cifras base (24% vs. 53% de compra tras iniciar el pago, 3% vs. 11%, 2,8% vs. 0,5%) sirven como punto de partida para medir cualquier mejora.*

---

## 4. Supuestos y limitaciones

- **Cuenta demo:** datos de la Google Merchandise Store, de solo lectura y con algunas cifras redondeadas. Los totales de canales y de dispositivos suman un poco más que el total de sesiones (140.051 y 137.980 frente a 137.067); la causa no se pudo confirmar.
- **Sin datos de costos:** no hay costo de anuncios ni de productos, así que **ingresos no es ganancia** y no se evalúa rentabilidad.
- **Direct** significa origen desconocido, no necesariamente alguien que escribió la dirección. Parte del tráfico podría ser interno de Google (hay sesiones desde Mountain View, Sunnyvale y San José).
- **Muestras pequeñas:** canales, países y dispositivos con menos de 1.000 sesiones no se usan para recomendar. Es un criterio propio, de juicio, no una regla exacta.
- **Usuarios no sumables:** un mismo usuario puede entrar desde más de un dispositivo, por lo que la suma por dispositivo supera el total de usuarios.
- **Embudo abierto:** el dashboard cuenta usuarios por cada evento; el embudo cerrado de GA4 da cifras parecidas, no idénticas. El orden de las pérdidas coincide.
- **Un solo mes:** no se puede confirmar estacionalidad ni tendencias. Hay un pico de usuarios hacia el 28–29 de septiembre que no se investigó.
- **Correlación no es causalidad:** GA4 muestra **dónde** ocurre una diferencia, no **por qué**. Las causas mencionadas son hipótesis.

---

## 5. Próximos pasos sugeridos

1. Conseguir el **costo de los anuncios** para evaluar la rentabilidad de Paid Search.
2. Confirmar **a qué países envía la tienda** y revisar si hay sesiones de baja calidad en India y Japón.
3. Revisar en GA4 los **pasos dentro del pago** (datos de envío y de pago) para ubicar dónde se abandona.
4. Analizar **varios meses** para ver tendencias y estacionalidad, e investigar el pico del 28–29 de septiembre.
5. Revisar **qué sitios generan el tráfico de Referral**, el canal con mayor tasa de compras por sesión entre los de muestra aceptable.
6. Repetir el análisis con los datos de GA4 en **BigQuery (SQL)**, para tener un control total sobre las definiciones.
