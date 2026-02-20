# Conceptos Básicos de Git

## Introducción

**Git** es la forma más popular de control de código fuente en la actualidad. Es tan predominante que es probable encontrarlo en prácticamente cualquier proyecto de software moderno.

**GitHub** es uno de los servicios de Git más populares de Internet, utilizado por numerosas empresas.

---

## Conceptos Fundamentales

### Repositorio (Repo)

Un **repositorio** es un lugar donde se almacena un proyecto o colección de proyectos.

- Generalmente contiene **una aplicación** que se está desarrollando
- Incluye todos los archivos y el historial de cambios del proyecto
- Se aloja en un servicio como GitHub

---

## Flujo de Trabajo Básico de Git

### 1. **Clonar el Repositorio**

**Objetivo:** Obtener una copia local del código

**Pasos:**
1. Acceder al repositorio en GitHub
2. Hacer clic en el botón "Code"
3. Copiar la URL SSH
4. Ejecutar en terminal local: `git clone <URL>`

**Autenticación:**
- Usa la clave SSH de tu máquina local
- GitHub verifica tus permisos
- Recibes una copia completa del repositorio

---

### 2. **Crear una Rama (Branch)**

**¿Qué es una rama?**
- Una **copia separada** del código
- Te permite trabajar de forma **aislada** sin afectar otras ramas
- Otros desarrolladores pueden trabajar simultáneamente en sus propias ramas

**Ramas importantes:**

| Rama | Propósito |
|------|-----------|
| **main** | Rama principal - código listo para producción |
| **demo/feature** | Rama de desarrollo para nuevas características |

**Comando:**
```
git checkout -b <nombre-rama>
```

**Nota:** La rama `main` es el estándar en Git y representa el código que terminará en producción.

---

### 3. **Trabajar en tu Rama**

**Proceso:**
1. Cambiar a tu rama: `git checkout demo`
2. Realizar cambios en los archivos
3. Guardar y editar el código como normalmente lo harías

**Ejemplo:** Eliminar líneas innecesarias en un Dockerfile

---

### 4. **Revisar Cambios**

**Comando:** `git status`

**Función:**
- Muestra qué archivos han sido modificados
- Identifica cambios no confirmados
- Te da una visión clara del estado actual

---

### 5. **Confirmar Cambios (Commit)**

**Comando:** `git commit -a -m "mensaje del cambio"`

**Parámetros:**
- `-a`: Incluir todos los cambios realizados
- `-m`: Mensaje descriptivo del cambio

**Importancia:** El mensaje aparecerá en GitHub y debe describir claramente qué cambió y por qué.

**Ejemplo:**
```
git commit -a -m "Eliminar comandos innecesarios en Dockerfile"
```

---

### 6. **Subir Cambios a GitHub**

**Comando:** `git push origin <nombre-rama>`

**Función:**
- Sube tu rama **local** al repositorio **remoto** (GitHub)
- `origin` hace referencia al repositorio de GitHub
- Ahora otros pueden ver tu rama

---

### 7. **Crear una Solicitud de Cambios (Pull Request)**

**¿Qué es?**
- Una **solicitud de permiso** para hacer cambios
- Permite la **revisión y colaboración**
- Inicia el proceso de Code Review

**Pasos:**
1. GitHub detecta tu nueva rama
2. Mostrar los cambios realizados comparados con la versión anterior
3. Hacer clic en "Create Pull Request"
4. Proporcionar descripción de los cambios

**Flujo de revisión:**
- Enviar la PR a compañeros de trabajo
- Ellos revisan el código
- Dejan comentarios o sugerencias
- Si todo está bien, **fusionan** la PR a la rama main

---

### 8. **Fusionar Cambios (Merge)**

**Proceso:**
1. Un compañero de trabajo revisa tu PR
2. Aprueba los cambios
3. Hace clic en "Merge"
4. Tu código ahora está en la rama **main**
5. **Inicia el pipeline de DevOps** para desplegar el código

**Importancia de la colaboración:**
⚠️ **NUNCA** fusiones tu propio código sin revisión de otros desarrolladores. Esta es una de las partes más importantes de usar Git: la **colaboración y revisión mutua**.

---

## Características Avanzadas de Git

### Reversión de Cambios

**Escenario:** Realizaste un cambio que resultó ser incorrecto

**Solución:** Git permite revertir cambios fácilmente
- Deshacer cambios locales
- Revertir commits fusionados
- Volver a versiones anteriores

---

### Pruebas Antes del Despliegue

**Opción:** Puedes probar tu código antes de iniciar el pipeline de DevOps
- Crear una rama de prueba
- Validar que todo funciona correctamente
- Luego crear la PR

---

## Resumen del Flujo de Trabajo

```
1. git clone <URL>           → Clonar repositorio
2. git checkout -b demo      → Crear rama
3. [Editar archivos]         → Hacer cambios
4. git status                → Revisar cambios
5. git commit -a -m "msg"    → Confirmar cambios
6. git push origin demo      → Subir a GitHub
7. Crear Pull Request        → Solicitar revisión
8. Code Review               → Compañeros revisan
9. Merge                     → Fusionar a main
10. DevOps Pipeline          → Desplegar a producción
```

---

## Buenas Prácticas

| Práctica | Descripción |
|----------|-------------|
| **Ramas descriptivas** | Usar nombres que describan el trabajo (feature/login, bugfix/error) |
| **Commits claros** | Mensajes específicos y detallados |
| **Pull Requests** | Siempre pedir revisión antes de fusionar |
| **Code Review** | Revisar código de compañeros |
| **Nunca fusionar solo** | Mantener la colaboración y calidad |

---

## Conclusión

Git es una herramienta increíblemente poderosa con muchas más características:
- Historial completo de cambios
- Reversión de cambios
- Branching y merging
- Colaboración en equipo

**Recomendación:** Practicar con Git en tus propios proyectos para dominar esta herramienta esencial del desarrollo moderno.