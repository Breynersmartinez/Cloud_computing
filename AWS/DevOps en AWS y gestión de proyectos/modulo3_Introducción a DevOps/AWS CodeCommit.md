# AWS CodeCommit

## Introducción

**AWS CodeCommit** es el servicio de Git gestionado por Amazon, parte de la suite de herramientas DevOps de AWS.

![alt text](<../../../img/AWS CodeCommit1.png>)

**Diferencia clave con GitHub:** CodeCommit está construido por AWS, lo que permite una **integración directa** con el resto de los servicios de DevOps de AWS.

---

## Ventajas de CodeCommit

### Integración Nativa con AWS

- Integración perfecta con otros servicios AWS DevOps
- Facilita el flujo de código a través del pipeline
- Simplifica la automatización del proceso CI/CD

### Repositorios en AWS

- Almacenamiento seguro en la infraestructura de AWS
- Los repositorios se gestionan directamente desde la consola de AWS
- Acceso integrado con credenciales de IAM


![alt text](<../../../img/AWS CodeCommit2.png>)

![alt text](<../../../img/AWS CodeCommit3.png>)



---

## Flujo Básico de Git en CodeCommit

El proceso es **idéntico** al de GitHub:



1. **Clonar repositorio** desde CodeCommit
2. **Crear rama** local
3. **Hacer cambios** al código
4. **Confirmar cambios** (commit)
5. **Subir cambios** (push) a CodeCommit
6. **Crear Pull Request**
![alt text](<../../../img/AWS CodeCommit4.png>)

![alt text](<../../../img/AWS CodeCommit5.png>)



7. **Revisar y fusionar**

**Diferencia:** El código se almacena en CodeCommit en lugar de GitHub.

---

## Características Avanzadas de CodeCommit

### 1. **Reglas de Aprobación (Approval Rules)**

**Problema:** Es difícil hacer cumplir políticas de revisión si solo son sugerencias.

**Solución:** Crear reglas automáticas que refuercen los procesos

**Configuración:**

![alt text](<../../../img/AWS CodeCommit7.png>)

- **Número de aprobaciones requeridas:** Especificar cuántas revisiones se necesitan antes de fusionar
  - Ejemplo: 1, 2, 5, o incluso más revisiones


![alt text](<../../../img/AWS CodeCommit8.png>)

- **Usuarios o roles autorizados:** Definir quién puede aprobar
  - Usuarios específicos de IAM
  - Roles de IAM
  - Equipos específicos

![alt text](<../../../img/AWS CodeCommit9.png>)

- **Aplicación selectiva por rama:** Elegir qué ramas requieren aprobación
  - Aplicar a rama `main` (producción)
  - No aplicar a ramas `dev` (desarrollo)

- **Aplicación selectiva por repositorio:** Configurar reglas por repositorio

**Beneficio:** **Garantiza** que nadie fusione código sin revisión adecuada

---

### 2. **Disparadores (Triggers)**

**¿Qué es un disparador?**

Un mecanismo que **desencadena acciones automáticas** cuando ocurren eventos en CodeCommit.

**Casos de uso:**

#### **Notificación vía SNS (Simple Notification Service)**
- Cuando se hace push de código, enviar una notificación
- Alertar al equipo de nuevos cambios
- Iniciar procesos de revisión

#### **Ejecutar Pruebas Automáticas**
- Usar AWS Lambda para ejecutar pruebas automáticas
- La función Lambda puede:
  - Descargar la rama
  - Ejecutar suite de pruebas
  - Proporcionar aprobación automática ✓ o rechazo ✗
  - Bloquear la revisión manual si las pruebas fallan

#### **Vinculación de Herramientas**
- Conectar CodeCommit con otros servicios AWS
- Disparar procesos en CodeBuild
- Iniciar pipelines de CodePipeline
- Activar funciones Lambda personalizadas

**Poder:** Los disparadores permiten **automatizar completamente** partes del pipeline de DevOps

**Ejemplo de flujo automatizado:**
```
1. Developer hace push a CodeCommit
2. Disparador ejecuta función Lambda
3. Lambda descarga código y ejecuta pruebas
4. Si pruebas pasan → Aprobación automática
5. Si pruebas fallan → Requiere revisión manual
6. Después de aprobación → Inicia etapa de build
```

---

## Integración con Pipeline DevOps

### Integración Simplificada

CodeCommit se integra perfectamente con el pipeline de AWS DevOps:

- **CodeCommit** (Source) → Tu código
- **CodeBuild** (Build) → Compilar código
- **CodeDeploy** (Deploy) → Desplegar a servidores
- **CodePipeline** (Orchestration) → Orquestar todo

**Facilidad:** CodeCommit puede ser el **origen de tu etapa de compilación** con una sola acción.

---

## Flujo Completo de CodeCommit en DevOps

```
┌─────────────────────────────────────────────────────────┐
│ 1. DEVELOPER HACE CAMBIOS                               │
│    - Clona repositorio de CodeCommit                    │
│    - Crea rama                                          │
│    - Hace cambios locales                               │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│ 2. PUSH A CODECOMMIT                                    │
│    - Sube cambios a CodeCommit                          │
│    - Dispara automáticamente disparadores               │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│ 3. DISPARADORES EJECUTAN ACCIONES                       │
│    - Ejecutan pruebas automáticas (Lambda)              │
│    - Envían notificaciones (SNS)                        │
│    - Validan código                                     │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│ 4. PULL REQUEST Y REVISIÓN                              │
│    - Crear solicitud de cambios                         │
│    - Reglas de aprobación requieren revisiones          │
│    - Compañeros revisan cambios                         │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│ 5. MERGE A RAMA MAIN                                    │
│    - Fusionar cambios aprobados                         │
│    - Disparar siguiente etapa del pipeline              │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│ 6. PIPELINE AUTOMÁTICO                                  │
│    - CodePipeline inicia automáticamente                │
│    - CodeBuild compila código                           │
│    - CodeDeploy despliega a producción                  │
└─────────────────────────────────────────────────────────┘
```

---

## Comparativa: CodeCommit vs GitHub

| Aspecto | CodeCommit | GitHub |
|--------|-----------|--------|
| **Proveedor** | AWS | Microsoft |
| **Integración AWS** | Nativa, integrada | Requiere configuración |
| **Reglas de Aprobación** | ✓ Incluido | ✓ Con GitHub Pro/Enterprise |
| **Disparadores** | ✓ Potentes | ✓ Webhooks |
| **Costo** | Incluido en AWS | Freemium + planes pagos |
| **Curva de aprendizaje** | Media | Baja (más popular) |

---

## Resumen de Características Clave

### Reglas de Aprobación
- Aplicar políticas de revisión de código
- Especificar cantidad de aprobadores
- Seleccionar usuarios y roles
- Aplicar a ramas específicas

### Disparadores
- Ejecutar acciones automáticas
- Enviar notificaciones (SNS)
- Ejecutar pruebas (Lambda)
- Vincular con otros servicios AWS

### Integración Pipeline
- Conectar directamente con CodeBuild
- Iniciar CodePipeline automáticamente
- Orquestar todo el flujo DevOps

---

## Conclusión

AWS CodeCommit es una solución completa de control de código fuente que:

- ✅ Ofrece todas las características de Git
- ✅ Se integra perfectamente con AWS DevOps
- ✅ Automatiza procesos con disparadores
- ✅ Refuerza políticas con reglas de aprobación
- ✅ Simplifica la gestión del pipeline CI/CD

La verdadera potencia de CodeCommit se demuestra cuando se combina con otros servicios AWS como CodeBuild, CodeDeploy y CodePipeline.