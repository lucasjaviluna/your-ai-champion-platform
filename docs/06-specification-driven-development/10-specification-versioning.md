---
sidebar_position: 10
title: "Versionado de Specifications"
description: "Comprender cómo versionar Specifications para preservar evolución, contexto y trazabilidad del conocimiento."
---

# Versionado de Specifications

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Comprender por qué las Specifications necesitan versionado.
- Diferenciar cambios menores y cambios conceptuales.
- Relacionar versiones de conocimiento con versiones de código.
- Diseñar estrategias de evolución histórica.
- Entender la importancia del versionado para agentes IA.

---

# Introducción

En software estamos acostumbrados a versionar:

- código;
- librerías;
- APIs;
- bases de datos.

Pero existe otro elemento que también evoluciona:

```
El conocimiento del sistema.
```

---

Una Specification representa conocimiento.

Por lo tanto:

```
Conocimiento

=

Algo que cambia

↓

Algo que debe versionarse
```

---

# El problema de modificar sin historia

Imaginemos una Specification:

```
Cliente premium recibe 20% de descuento.
```

Un año después alguien cambia:

```
Cliente premium recibe 30%.
```

Si simplemente reemplazamos el texto:

```
30%
```

perdemos información.

No sabemos:

- cuándo cambió;
- por qué cambió;
- quién decidió;
- qué código dependía de la regla anterior.

---

# Una Specification necesita memoria

Una Specification madura debe responder:

```
¿Cuál es la versión actual?

¿Qué cambió?

¿Por qué cambió?

¿Qué impacto tuvo?
```

---

# Identidad de una Specification

Cada Specification debería tener una identidad estable.

Ejemplo:

```yaml
id: CUSTOMER-DISCOUNT-001

title: Premium Customer Discount

version: 2.0

status: active
```

---

El ID representa la entidad.

La versión representa su evolución.

---

# Versionado semántico

Podemos aplicar una idea similar a Semantic Versioning:

```
MAJOR.MINOR.PATCH
```

---

## PATCH

Cambios pequeños.

No modifican comportamiento.

Ejemplo:

```
1.0.0

↓

1.0.1
```

Cambio:

```
Corregir descripción.
```

---

## MINOR

Nueva capacidad compatible.

Ejemplo:

```
1.0.0

↓

1.1.0
```

Cambio:

```
Agregar nuevo tipo de cliente.
```

---

## MAJOR

Cambio conceptual.

Ejemplo:

```
1.0.0

↓

2.0.0
```

Cambio:

```
La regla de descuentos cambia completamente.
```

---

# Ejemplo completo

Versión inicial:

```yaml
id: PAYMENT-001

version: 1.0

rule:

Payment supports credit cards.
```

---

Nueva necesidad:

```
Agregar pagos internacionales.
```

Nueva versión:

```yaml
id: PAYMENT-001

version: 1.1

changes:

- Added international payments
```

---

Cambio posterior:

```
Eliminar integración anterior.
```

Nueva versión:

```yaml
id: PAYMENT-001

version: 2.0

changes:

- Replaced payment provider model
```

---

# Versionado y Git

Git ya proporciona una capa de historial.

Ejemplo:

```
specs/payment.md

commit A

↓

version 1.0

commit B

↓

version 1.1

commit C

↓

version 2.0
```

---

La Specification tiene:

```
Versión conceptual

+

Historial técnico
```

---

# Relación entre Specification y código

Un problema frecuente:

```
Código actual

+

Specification antigua
```

---

Esto genera inconsistencias.

---

Por eso debemos poder responder:

```
¿Qué versión de Specification implementa este código?
```

---

Ejemplo:

```
Release v3.0

uses:

PAYMENT-001 version 2.1
```

---

# Matriz de compatibilidad

En sistemas grandes puede ser útil mantener relaciones:

| Código | Specification |
|-|-|
| Payment Service v1 | Payment Spec 1.x |
| Payment Service v2 | Payment Spec 2.x |

---

Esto es especialmente importante durante migraciones.

---

# Versionado y agentes IA

Este punto es fundamental.

Un agente puede recibir:

```
Payment Specification
```

pero necesita saber:

```
¿Cuál?
```

---

Porque:

```
Payment Spec v1
```

puede decir:

```
Solo tarjetas nacionales.
```

Mientras:

```
Payment Spec v2
```

dice:

```
Tarjetas nacionales e internacionales.
```

---

Sin versionado, un agente puede tomar decisiones incorrectas.

---

# Knowledge Time Travel

Una capacidad interesante del versionado es poder viajar en la historia.

Pregunta:

```
¿Por qué existe este código?
```

Respuesta:

```
Porque en 2025 la Specification v1.3 definía esta regla.
```

---

El sistema puede reconstruir decisiones pasadas.

---

# 📖 Evolución del pensamiento

La evolución del conocimiento:

```
Documento reemplazado

↓

Documento histórico

↓

Documento versionado

↓

Specification versionada

↓

Conocimiento navegable en el tiempo
```

---

El objetivo final:

No solamente saber qué sabemos hoy.

También saber qué sabíamos cuando tomamos una decisión.

---

# Caso de estudio: Your Harness

Una posible evolución futura de Your Harness podría incluir un Specification Registry:

```
spec-registry/

├── SPEC-001/

│   ├── v1.0.md

│   ├── v1.1.md

│   └── v2.0.md

└── metadata.yaml
```

---

Esto permitiría:

- comparar versiones;
- entender cambios;
- alimentar agentes con contexto histórico.

---

Es importante recordar:

Your Harness continúa siendo un proyecto en desarrollo. Estas ideas representan posibles capacidades futuras y decisiones de diseño, no funcionalidades existentes.

---

# 🧠 AI Engineer Mindset

Un desarrollador piensa:

> Tengo la versión actual del código.

Un AI Engineer piensa:

> Tengo la versión actual del conocimiento y puedo reconstruir su evolución.

---

# Resumen

En este capítulo aprendimos:

- las Specifications necesitan versionado;
- el conocimiento también evoluciona;
- Git aporta historial técnico;
- la versión de Specification debe relacionarse con la versión del código;
- los agentes necesitan saber qué versión de conocimiento están utilizando.

---

# Ejercicio

Elige una funcionalidad que haya cambiado en un proyecto real.

Define:

```
Specification v1

↓

Cambio requerido

↓

Specification v2

```

Describe:

1. Qué cambió.
2. Por qué cambió.
3. Qué impacto tuvo.

---

# Proyecto incremental

En el próximo capítulo veremos cómo llevar estas ideas al siguiente nivel:

```
Specifications

+

Agentes IA

+

Workflows
```

Analizaremos cómo una Specification puede convertirse en el contrato que guía agentes durante tareas reales de ingeniería.
