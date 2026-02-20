# Tuberías CI/CD: Integración Continua y Entrega Continua

## Introducción

El pipeline de CI/CD es como una **cinta transportadora de DevOps**. Representa todas las etapas por las que pasa el software antes de llegar a los clientes.

![alt text](<../../../img/Canalización CI_CD.png>)
---

## Etapas del Pipeline CI/CD

### 1. **Integración Continua (Build)**

**Objetivo:** Preparar y compilar el código

- Escribir el código fuente
- Compilar el código en un paquete desplegable
- Establecer dependencias necesarias
- Realizar pruebas básicas

**Concepto clave:** El código recién escrito no está listo para funcionar; necesita compilarse y empaquetarse.

---

### 2. **Pruebas (Testing)**

**Objetivo:** Validar que todo funciona correctamente

- ¿La aplicación hace lo que se supone que debe hacer?
- ¿Los bloques de código individuales cumplen sus funciones?
- ¿Interactúa correctamente con otros microservicios?

Este paso es crítico antes de presentar la aplicación a los clientes.

---

### 3. **Revisión (Review) - Punto de Decisión**

**Objetivo:** Aprobar la aplicación antes de producción

Se implementa en el **entorno de ensayo** para validar antes de pasar a producción.

Aquí hay dos enfoques:

#### **Entrega Continua (CD)**
- Incluye una **revisión manual**
- Una persona humana verifica que la aplicación esté lista
- El proceso automatizado se **detiene temporalmente**
- Once aprobado, el revisor autoriza el paso a la siguiente fase
- **Mantiene intervención humana** en el lanzamiento

#### **Implementación Continua**
- **Automatiza completamente** la revisión final
- Elimina cualquier intervención humana
- Se recomienda implementar solo después de confirmar que el proceso funciona correctamente

---

### 4. **Despliegue (Deployment)**

**Objetivo:** Poner la aplicación en producción

- Implementar el código en la **arquitectura de producción**
- Realizar una **ronda final de pruebas** en servidores de producción
- Validar que todo funciona correctamente

Una vez aprobadas todas las pruebas finales, el proceso ha **terminado exitosamente**.

---

## Características Importantes

### Velocidad
- Al automatizar los pasos, se crea un entorno que permite a los desarrolladores escribir y publicar código **rápidamente** durante el día

### Flexibilidad
- Las etapas del pipeline **se pueden ajustar** según las necesidades específicas
- Ejemplos: múltiples entornos de ensayo, varios pasos de revisión manual
- **Cada equipo crea su propia canalización** según sus requisitos

---

## Resumen de Conceptos Clave

| Concepto | Descripción |
|----------|-------------|
| **CI (Integración Continua)** | Escribir, compilar y probar código automáticamente |
| **CD (Entrega Continua)** | Desplegar con revisión manual antes de producción |
| **Deployment Continuo** | Despliegue completamente automatizado sin intervención humana |
| **Pipeline** | Secuencia de etapas automáticas y manuales que controla el flujo del software |

---

## Próximos Pasos

Explorar las **herramientas específicas** que se pueden usar para implementar cada etapa del pipeline CI/CD.