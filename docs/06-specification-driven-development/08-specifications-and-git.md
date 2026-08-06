---
sidebar_position: 8
title: "Specifications + Git"
description: "Comprender cómo integrar Specifications dentro del flujo de control de versiones y colaboración."
---

# Specifications + Git

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Comprender la relación entre Specifications y control de versiones.
- Diseñar una estructura de repositorio orientada a conocimiento.
- Entender cómo revisar cambios de Specifications mediante Pull Requests.
- Aplicar prácticas de versionado y colaboración.
- Preparar repositorios para trabajar con agentes IA.

---

# Introducción

En capítulos anteriores definimos una idea:

> Una Specification es un artefacto vivo.

Pero un artefacto vivo necesita:

- historial;
- versiones;
- autores;
- revisiones;
- cambios trazables.

Exactamente las capacidades que Git proporciona.

---

# El error tradicional

Muchas organizaciones mantienen esta separación:

```
Repositorio de código

↓

Git
```

y:

```
Documentación

↓

Wiki / Word / Confluence
```

---

El problema:

El código evoluciona.

La documentación evoluciona por separado.

Con el tiempo aparecen inconsistencias.

---

# La propuesta SDD

En SDD, las Specifications forman parte del ciclo normal del desarrollo.

Una estructura posible:

```
repository/

├── src/

├── tests/

├── specs/

│   ├── product/

│   ├── functional/

│   ├── technical/

│   └── architecture/

├── docs/

└── README.md
```

---

Ahora el repositorio contiene:

```
Código

+

Pruebas

+

Conocimiento
```

---

# ¿Por qué junto al código?

Porque ambos evolucionan juntos.

Ejemplo:

Un desarrollador modifica una regla de negocio.

Antes:

```
Cambiar código

↓

Actualizar documentación manualmente
```

---

Con SDD:

```
Modificar Specification

↓

Modificar código

↓

Actualizar tests

↓

Revisar cambio completo
```

---

# Git como memoria histórica

Git no solamente guarda archivos.

Guarda evolución.

Puede responder:

```
¿Cuándo apareció esta regla?

¿Quién la modificó?

¿Por qué cambió?

¿Qué versión del código la implementaba?
```

---

Cuando las Specifications están dentro de Git, estas preguntas también aplican al conocimiento.

---

# Pull Requests como revisión de conocimiento

Tradicionalmente un Pull Request revisa:

```
¿El código funciona?
```

En SDD agregamos:

```
¿La intención está correctamente definida?
```

---

Un cambio completo puede verse así:

```
Specification Change

        +

Implementation Change

        +

Tests

        +

Evidence
```

---

# Ejemplo de Pull Request

Título:

```
Add international payments support
```

Cambios:

```
specs/payments/international.md

src/payment-service/

tests/payment/
```

---

El reviewer puede analizar:

1. ¿El objetivo está claro?
2. ¿Las reglas están definidas?
3. ¿El código implementa la Specification?
4. ¿Los tests cubren los criterios?

---

# Branching y Specifications

Las Specifications pueden seguir el mismo modelo de ramas.

Ejemplo:

```
main

 |

 +-- feature/international-payments

        |
        |
        +-- specification update

        |
        +-- implementation

        |
        +-- tests
```

---

La rama contiene la evolución completa del cambio.

---

# Commits orientados a conocimiento

Un commit tradicional:

```
Fix payment bug
```

Aporta poca información.

---

Un commit orientado a SDD:

```
Update payment specification:
support rejected provider responses
```

Luego:

```
Implement payment rejection handling
```

---

La historia es más comprensible.

---

# Versionado de Specifications

Una Specification puede tener:

```yaml
id: PAYMENT-001

version: 2.0

status: approved
```

---

Pero Git agrega otra dimensión:

```
Specification Version

+

Repository Commit
```

---

Esto permite saber:

```
Specification 2.0

fue implementada en:

commit abc123
```

---

# Tags y releases

Las releases pueden incluir el estado del conocimiento.

Ejemplo:

```
v3.0.0

includes:

- Product Specifications
- Architecture Decisions
- Implementation
- Tests
```

---

El producto liberado incluye también la explicación de por qué existe.

---

# Git como base para agentes IA

Aquí aparece un punto importante.

Un agente IA trabajando sobre un repositorio necesita acceder a:

```
Código actual

+

Historial

+

Specifications

+

Decisiones
```

---

Sin Git:

El agente ve solamente archivos actuales.

---

Con Git:

Puede comprender evolución.

Ejemplo:

Pregunta:

```
¿Por qué este código es diferente?
```

Puede analizar:

```
Specification anterior

↓

Cambio aprobado

↓

Implementación actual
```

---

# 📖 Evolución del pensamiento

La evolución del repositorio:

```
Código en Git

↓

Código + documentación

↓

Código + documentación versionada

↓

Código + Specifications

↓

Repositorio como memoria completa del sistema
```

---

La idea cambia:

Git deja de ser solamente un sistema de versiones.

Se convierte en una memoria histórica del proyecto.

---

# Caso de estudio: Your Harness

Una posible estructura para Your Harness podría ser:

```
your-harness/

├── packages/

├── specs/

│   ├── vision/

│   ├── architecture/

│   ├── features/

│   └── experiments/

├── adr/

├── examples/

└── docs/
```

---

Esta estructura permitiría registrar:

- decisiones;
- experimentos;
- cambios;
- evolución del diseño.

---

Nuevamente:

Esto representa una posible organización futura del proyecto. Your Harness continúa siendo una iniciativa en desarrollo, no un producto terminado.

---

# 🧠 AI Engineer Mindset

Un desarrollador piensa:

> Git guarda mi código.

Un AI Engineer piensa:

> Git guarda la evolución del conocimiento que produjo mi código.

---

# Resumen

En este capítulo aprendimos:

- las Specifications deben vivir cerca del código;
- Git permite versionar conocimiento;
- los Pull Requests pueden revisar intención además de implementación;
- la historia del repositorio es parte del conocimiento del sistema;
- los agentes IA pueden beneficiarse del historial completo.

---

# Ejercicio

Toma un repositorio existente y responde:

1. ¿Dónde vive actualmente el conocimiento del proyecto?
2. ¿Qué información está fuera de Git?
3. ¿Qué cambiarías para convertirlo en un repositorio orientado a SDD?

---

# Proyecto incremental

En el próximo capítulo veremos una consecuencia natural:

```
Specifications

↓

Cambios

↓

Evidencia

↓

Trazabilidad completa
```

Estudiaremos cómo demostrar que una Specification fue correctamente implementada.
