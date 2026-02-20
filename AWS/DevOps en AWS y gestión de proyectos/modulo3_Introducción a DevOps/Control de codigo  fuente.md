# Control de Código Fuente (Source Control)

## Introducción

El **control de código fuente** es una herramienta esencial en el desarrollo de software. La herramienta más popular en 2023 es **Git**.

---

## ¿Qué es el Control de Código Fuente?

Es una ubicación centralizada donde:
- **Empujar** el código conforme realizamos cambios
- **Descargar** la última versión del código
- **Colaborar** con otros desarrolladores

---

## Razones para Usar Control de Código Fuente

### 1. **Colaboración en Equipo**

- **Absolutamente necesario** para equipos de más de un desarrollador
- Permite que múltiples personas trabajen en diferentes partes de la aplicación
- Proporciona un lugar común para **combinar regularmente** el código

---

### 2. **Historial Completo de Cambios**

El control de código fuente conserva:
- Todo cambio realizado en el código
- **Quién** hizo el cambio
- **Cuándo** se realizó el cambio

**Utilidad:** Entender la evolución del proyecto y rastrear decisiones.

---

### 3. **Gestión de Múltiples Versiones**

**Escenario común:**
- **Desarrollo:** Nuevas características en desarrollo
- **Testing:** Código más antiguo siendo probado
- **Producción:** Código de semanas atrás en ejecución

Sin control de versiones, mantener estas versiones diferentes sería **manual y difícil**. Con control de versiones, se gestiona automáticamente.

---

### 4. **Revertir Cambios**

**Problema:** He estado escribiendo código para una nueva característica y decidí reescribirlo de otra forma.

**Solución:** Usando el historial completo de cambios, puedo volver a un punto anterior en el tiempo.

**Analogía:** Es como una "partida guardada" en un videojuego. Puedo descartar cambios sin perder el trabajo previo.

---

### 5. **Trabajo en Paralelo (Branching)**

**Escenario:** 
- Hay un error en producción que necesita corrección urgente
- Hay desarrollo activo de nuevas características
- No quiero desplegar código no probado

**Solución:** Los desarrolladores pueden trabajar en **versiones paralelas** del código.

**Proceso de "viaje en el tiempo":**
1. Viajar atrás a la versión de producción
2. Hacer cambios de corrección de errores
3. Desplegar **solo este código** a producción
4. Traer los mismos cambios de corrección a las otras versiones (dev, staging)

El control de versiones **automatiza** este proceso de sincronización entre versiones.

---

### 6. **Depuración Eficiente**

**Problema:** Hay un error en la aplicación que no existía la semana pasada.

**Proceso de depuración:**

1. Ver todos los cambios añadidos a la aplicación
2. Crear una compilación con el código de hace una semana
3. ¿Ocurre el error ahora?
4. Crear una compilación con el código de hace 2 días
5. Usar este proceso para **acotar exactamente** dónde se introdujo el fallo

**Ventaja:** Identificar rápidamente qué cambio causó el problema.

---

### 7. **Copia de Seguridad Efectiva**

**Problema:** 
- Estoy trabajando en una nueva característica en mi laptop
- El código solo existe localmente
- ¿Qué si mi laptop se daña o la pierdo?

**Solución:** Al empujar el código al control de código fuente, creo **otra copia** del código.

**Resultado:** El código está protegido contra pérdidas físicas del dispositivo.

---

## Resumen de Beneficios

| Beneficio | Descripción |
|-----------|-------------|
| **Colaboración** | Múltiples desarrolladores pueden trabajar juntos |
| **Historial** | Registro completo de todos los cambios |
| **Versionado** | Gestión de múltiples versiones simultáneamente |
| **Reversión** | Volver a versiones anteriores del código |
| **Ramas** | Trabajo en paralelo sin conflictos |
| **Depuración** | Identificar rápidamente cuándo se introdujeron errores |
| **Seguridad** | Copia de seguridad distribuida del código |

---

## Próximos Pasos

Explorar herramientas populares de control de código fuente y cómo utilizarlas en el flujo de desarrollo.