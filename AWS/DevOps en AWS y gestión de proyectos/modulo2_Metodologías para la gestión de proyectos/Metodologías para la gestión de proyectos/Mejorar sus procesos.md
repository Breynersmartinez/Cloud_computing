Una vez finalizado este curso, su jefe le pide ayuda para identificar los cuellos de botella en el proceso de desarrollo de software que se está llevando a cabo actualmente en su empresa. Durante los últimos años, la empresa ha estado desarrollando software utilizando la metodología de cascada, y quieren introducir algunas mejoras. El proceso de desarrollo actual tiene el siguiente aspecto:

El director del proyecto recaba opiniones sobre su software de los clientes y de las partes interesadas internas. Para hacerse una idea de lo que hay que mejorar, el jefe de proyecto pasa una semana revisando todos los tickets y correcciones de errores que se han presentado. En el caso de quejas menores, este proceso podría conducir al desarrollo de una actualización del software. Sin embargo, si los tickets contienen muchas quejas sobre un proceso específico, este proceso podría dar lugar al desarrollo de una pieza de software completamente nueva. Después de que el gestor del proyecto recopile las quejas, presentará esta información a los responsables de los distintos departamentos de TI. A partir de ahí, el director del proyecto y los responsables de TI llegan a un consenso sobre lo que hay que hacer y quién lo hará. (Tiempo: 1 semana)

Una vez establecido el objetivo del trabajo, los responsables vuelven a sus equipos y distribuyen el trabajo entre los desarrolladores, los arquitectos de soluciones, los administradores de sistemas y otro personal clave. A lo largo de la semana siguiente, cada miembro del equipo simula sus partes individuales del trabajo y luego crea una solución que resuelve la tarea que se le asignó. El martes después de que cada persona cree maquetas y soluciones, los departamentos vuelven a reunirse para comparar las soluciones. El objetivo de la comparación es asegurarse de que las piezas individuales que se están construyendo funcionarán juntas. (Tiempo: 1,5 semanas)

En la siguiente fase, los profesionales de TI empiezan a trabajar en sus piezas individuales. Dedican las 3 semanas siguientes a crear sus partes del proyecto. (Tiempo: 3 semanas)

Una vez completadas estas piezas individuales, el equipo de control de calidad (QA) prueba todas las partes para asegurarse de que funcionan juntas correctamente. (Tiempo: 1 semana)

Si el equipo de control de calidad encuentra algún problema de compatibilidad, devuelve las piezas individuales a los desarrolladores para que las resuelvan. Después de que los desarrolladores hagan las correcciones necesarias, el equipo de control de calidad vuelve a probar las piezas individuales para confirmar que se han resuelto los problemas. (Tiempo: 1 semana)

En la parte final del proceso, el nuevo código se despliega en un entorno de ensayo. Desde allí, el código se ejecuta durante 3 días para garantizar que no se producen otros problemas. Una vez finalizados los 3 días, se da 1 día para ejecutar el código en un entorno beta. Si todo va bien, el equipo despliega finalmente la nueva aplicación en los servidores de producción el viernes. (Tiempo: 1 semana)




---

## ¿Qué cambiaría del proceso?

No mantendría el proceso exactamente igual, pero tampoco haría una transición radical inmediata. Propondría una **transformación progresiva hacia un enfoque ágil**, manteniendo algunos elementos estructurados del modelo actual mientras se introducen mejoras clave.

---

## ¿Lo rediseñaría completamente usando una metodología ágil?

Sí, a mediano plazo lo rediseñaría hacia una metodología ágil (como Scrum o Kanban), porque el principal problema del proceso actual no es solo la duración de los pasos, sino:

* Validación tardía
* Integración al final
* QA como fase aislada
* Entregas grandes y poco frecuentes

Un enfoque ágil permitiría:

* Entregas incrementales más rápidas
* Feedback continuo del cliente
* Detección temprana de errores
* Mayor adaptabilidad a cambios

Sin embargo, haría la transición de forma gradual para evitar resistencia interna y problemas organizacionales.

---

## ¿O mantendría el proceso actual pero optimizando los pasos?

Como mejora inmediata, antes de una transformación total, aplicaría estos cambios:

1. Integrar QA desde el inicio (no solo al final).
2. Implementar integración continua (CI).
3. Reducir el tamaño de las entregas.
4. Trabajar en ciclos más cortos (mini-iteraciones).
5. Automatizar despliegues (CI/CD).

---

## Conclusión

No mantendría el proceso igual.
Lo evolucionaría hacia un modelo ágil de forma progresiva, combinando mejoras inmediatas con una transformación estructural a mediano plazo.

El problema principal no es que los pasos sean lentos, sino que el modelo completo está diseñado para detectar errores demasiado tarde.

