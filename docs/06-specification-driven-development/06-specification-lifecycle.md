---
sidebar_position: 6
title: "El ciclo de vida de una Specification"
description: "Comprender cómo una Specification nace, evoluciona, se valida y se mantiene durante el ciclo de vida del software."
---

# El ciclo de vida de una Specification

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Comprender que una Specification es un artefacto evolutivo.
- Conocer las etapas del ciclo de vida de una Specification.
- Entender cómo se relacionan cambios, revisiones y aprobaciones.
- Diseñar procesos de evolución controlada.
- Preparar Specifications para trabajar con agentes IA.

---

# Introducción

Una de las ideas más importantes de SDD es:

> Una Specification no describe solamente el estado actual de un sistema. También registra cómo ese sistema evoluciona.

Un error común es pensar:

```
Crear Specification

↓

Implementar

↓

Fin
```

Pero los sistemas reales nunca permanecen estáticos.

---

# Los sistemas cambian

Durante la vida de un producto aparecen:

- nuevos requerimientos;
- cambios regulatorios;
- nuevas tecnologías;
- problemas encontrados en producción;
- mejoras de arquitectura;
- nuevas necesidades del negocio.

Por lo tanto, las Specifications también deben cambiar.

---

# Modelo del ciclo de vida

Un modelo general sería:

```
Idea

↓

Draft

↓

Review

↓

Approved

↓

Implementation

↓

Validation

↓

Evolution

↓

Deprecated
```

---

Cada etapa tiene un propósito diferente.

---

# 1. Draft (Borrador)

Todo comienza como una hipótesis.

En esta etapa todavía existe incertidumbre.

Ejemplo:

```
Necesitamos mejorar el sistema de beneficios.
```

Todavía no sabemos:

- alcance definitivo;
- impacto;
- restricciones.

---

Características:

- exploración;
- discusión;
- análisis inicial.

---

Una Specification en Draft puede cambiar mucho.

---

# 2. Review (Revisión)

Antes de implementar, otros actores deben analizarla.

Participan:

- producto;
- arquitectura;
- desarrollo;
- seguridad;
- operaciones.

---

La pregunta principal es:

> ¿La Specification representa correctamente el problema?

---

Una revisión no busca aprobar código.

Busca validar conocimiento.

---

# 3. Approved (Aprobada)

Una Specification aprobada significa:

```
Existe acuerdo sobre:

- objetivo;
- alcance;
- reglas;
- restricciones;
- validación.
```

---

Esto no significa que sea perfecta.

Significa que existe un contrato aceptado para avanzar.

---

# 4. Implementation (Implementación)

Aquí comienza la construcción.

La relación es:

```
Specification

↓

Plan

↓

Código

↓

Tests
```

---

Durante esta etapa pueden aparecer nuevos descubrimientos.

Por ejemplo:

- una restricción técnica desconocida;
- una dependencia externa;
- una limitación de infraestructura.

---

Estos descubrimientos no deberían perderse.

Deben regresar a la Specification.

---

# 5. Validation (Validación)

Una Specification madura define cómo validar el resultado.

La validación puede incluir:

- pruebas automáticas;
- revisión humana;
- métricas;
- pruebas de seguridad;
- validaciones de negocio.

---

Ejemplo:

Specification:

```
Un cliente premium recibe 20% de descuento.
```

Evidencia:

```
Test automatizado aprobado.

Captura de interfaz.

Registro de ejecución.
```

---

# 6. Evolution (Evolución)

La mayoría de los sistemas pasan más tiempo evolucionando que siendo creados.

Por eso una Specification debe soportar cambios.

Ejemplo:

Versión inicial:

```
Descuento premium = 20%
```

Nueva versión:

```
Descuento premium depende del nivel del cliente.
```

---

No se elimina la historia.

Se evoluciona mediante versiones.

---

# 7. Deprecated (Deprecada)

No todo conocimiento debe permanecer activo.

Una Specification puede dejar de ser válida.

Ejemplo:

```
Sistema antiguo de pagos.
```

---

Pero incluso una Specification obsoleta puede tener valor histórico.

Puede explicar:

- decisiones antiguas;
- migraciones;
- razones de cambio.

---

# Versionado

Una Specification debería tener identidad.

Ejemplo:

```yaml
id: SPEC-PAYMENTS-001

version: 2.1

status: approved
```

---

Esto permite responder:

```
¿Qué versión utilizó este agente?

¿Qué reglas existían cuando se generó este código?
```

---

# Estados posibles

Un modelo simple:

```text
DRAFT

↓

REVIEW

↓

APPROVED

↓

IMPLEMENTED

↓

VALIDATED

↓

ACTIVE

↓

DEPRECATED
```

---

# Cambios y trazabilidad

Una pregunta fundamental:

> ¿Por qué cambió esta Specification?

La respuesta debe estar registrada.

Ejemplo:

```
Version 2.0

Cambio:

Agregar pagos internacionales.

Motivo:

Nueva expansión comercial.

Aprobado por:

Product + Architecture.
```

---

# Specification y Git

Una práctica natural es almacenar Specifications junto al código.

Ejemplo:

```
repository/

├── src/

├── tests/

├── specs/

│   ├── payments.md

│   └── users.md

└── docs/
```

---

Ventajas:

- historial;
- revisión por Pull Request;
- colaboración;
- auditoría.

---

# Specification y agentes IA

El ciclo de vida es especialmente importante para agentes.

Un agente debe saber:

```
¿Estoy leyendo una Specification activa?

¿Es una versión antigua?

¿Está aprobada?

¿Puede modificarla?
```

---

Sin estados claros, un agente podría utilizar información obsoleta.

---

# 📖 Evolución del pensamiento

Antes:

```
Documento terminado
```

↓

Después:

```
Documento versionado
```

↓

Ahora:

```
Artefacto vivo de conocimiento
```

---

El cambio importante es entender que el conocimiento también tiene ciclo de vida.

---

# Caso de estudio: Your Harness

Una posible plataforma como Your Harness necesitaría gestionar estados de Specifications.

Por ejemplo:

```
Specification Registry

SPEC-001

status:
approved

version:
1.3

history:
[
 v1.0 created,
 v1.1 reviewed,
 v1.3 approved
]
```

Esto permitiría que futuros agentes conozcan no solamente una Specification, sino su evolución.

Estas son decisiones de diseño futuras para un proyecto todavía en desarrollo.

---

# 🧠 AI Engineer Mindset

Un ingeniero tradicional pregunta:

> ¿Cuál es la versión actual del código?

Un AI Engineer agrega:

> ¿Cuál es la versión actual del conocimiento que generó ese código?

---

# Resumen

En este capítulo aprendimos:

- una Specification tiene ciclo de vida;
- las Specifications evolucionan con el sistema;
- los cambios deben quedar trazados;
- el versionado es fundamental;
- los agentes necesitan conocer el estado de una Specification.

---

# Ejercicio

Define el ciclo de vida de una Specification para un equipo de desarrollo.

Incluye:

1. Estados posibles.
2. Quién puede cambiar cada estado.
3. Qué evidencia requiere cada transición.

---

# Proyecto incremental

En el próximo capítulo veremos cómo diferentes Specifications pueden relacionarse entre sí:

```
Product Specification

↓

Functional Specification

↓

Technical Specification

↓

Architecture Specification

↓

Evidence
```

Construiremos el concepto de **trazabilidad entre conocimiento y ejecución**.
