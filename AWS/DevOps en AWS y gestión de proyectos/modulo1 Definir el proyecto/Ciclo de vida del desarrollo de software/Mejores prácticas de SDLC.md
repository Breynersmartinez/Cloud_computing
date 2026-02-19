# Buenas prácticas en cada fase del SDLC

## 1. Planificación y análisis

**Objetivo:** definir correctamente la funcionalidad del producto.

Buenas prácticas:

- Involucrar a:
  - Propietarios del producto
  - Usuarios finales
  - Personas con poder de decisión
- Hablar en el lenguaje del negocio (no técnico).
- Validar que la funcionalidad realmente resuelve el problema.
- Crear maquetas o prototipos simples para visualizar el resultado.

Clave: asegurar que lo que se construya sea lo que realmente se necesita.

---

## 2. Diseño

**Objetivo:** tomar decisiones técnicas y arquitectónicas.

Buenas prácticas:

- Evaluar compatibilidad y sostenibilidad tecnológica (especialmente en proyectos de largo plazo).
- Elegir tecnologías acordes a las habilidades del equipo.
- Realizar un “spike” técnico (pequeña prueba de concepto) si la tecnología es nueva.
- Validar decisiones antes de iniciar la implementación formal.

---

## 3. Implementación

**Objetivo:** desarrollar el software de forma organizada.

Buenas prácticas:

- Usar control de código fuente (repositorio central).
- Definir estándares de codificación.
- Facilitar la colaboración y mantenibilidad.
- Integrar código con frecuencia (Integración Continua).
- Automatizar el proceso de construcción cuando sea posible.

---

## 4. Documentación

**Principio:** la cantidad correcta de documentación.

- Suficiente para que un nuevo miembro entienda el sistema.
- Útil para soporte y resolución de incidentes.
- Evitar documentación excesiva que no aporte valor.

---

## 5. Pruebas

Las pruebas pueden realizarse durante la implementación.

### Seguimiento de errores

- Utilizar una base de datos de seguimiento de bugs.
- Registrar:
  - Pasos para reproducir el error
  - Estado (creado, en proceso, corregido, desplegado)

### Tipos de pruebas

**Pruebas funcionales**
- Verifican que el sistema hace lo que debe hacer.
- Ejemplo: un usuario puede crear un cliente.

**Pruebas no funcionales**
- Evalúan:
  - Rendimiento
  - Usabilidad
  - Seguridad

---

## 6. Despliegue

El despliegue implica riesgo.

Buenas prácticas:

- Automatizar los despliegues para reducir errores humanos.
- Probar primero en entornos de prueba y preproducción.
- Realizar despliegues frecuentes con cambios pequeños.
- Reducir ciclos largos de retroalimentación.

Principio: cambios pequeños y frecuentes son más seguros que grandes cambios esporádicos.

---

## 7. Mantenimiento

El mantenimiento ocupa más tiempo que la implementación.

Buenas prácticas:

- Priorizar la corrección de errores.
- Usar el sistema de seguimiento de bugs.
- Escribir código:
  - Legible
  - Fácil de depurar
  - Fácil de mantener
- Involucrar a miembros nuevos en corrección de errores para acelerar su aprendizaje.

---

## Conclusión

- Cada proyecto es diferente.
- No existe una única fórmula perfecta.
- Es fundamental realizar retrospectivas y adaptar las prácticas al equipo.
- La mejora continua fortalece el éxito futuro.
