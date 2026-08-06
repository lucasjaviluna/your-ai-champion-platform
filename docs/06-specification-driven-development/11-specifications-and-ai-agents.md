---
sidebar_position: 11
title: "Specifications y agentes IA"
description: "Comprender cómo las Specifications actúan como contratos de conocimiento para agentes inteligentes."
---

# Specifications y agentes IA

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Comprender la relación entre Specifications y agentes IA.
- Identificar por qué los agentes necesitan contexto estructurado.
- Diseñar flujos de trabajo guiados por Specifications.
- Entender el rol de las restricciones y evidencia.
- Preparar sistemas donde humanos y agentes colaboren.

---

# Introducción

La aparición de agentes IA cambia profundamente la ingeniería de software.

Hasta ahora el flujo habitual era:

```
Humano

↓

Código

↓

Sistema
```

Ahora aparece:

```
Humano

↓

Agente IA

↓

Código

↓

Sistema
```

---

Pero aparece un nuevo desafío:

> ¿Cómo aseguramos que el agente entiende correctamente lo que debe hacer?

---

# El problema del contexto

Un modelo de IA no conoce automáticamente:

- la arquitectura;
- las reglas de negocio;
- las decisiones históricas;
- las restricciones;
- los objetivos.

Necesita recibir contexto.

---

Un contexto pobre produce resultados pobres.

---

Ejemplo:

Prompt:

```
Agrega descuentos premium.
```

---

Un agente podría decidir:

```typescript
if(customer.type === "premium"){
    discount = 10;
}
```

Pero:

- ¿10% es correcto?
- ¿Debe aplicarse siempre?
- ¿Existen excepciones?
- ¿Debe registrarse auditoría?

---

El problema no es la capacidad del modelo.

Es la falta de conocimiento estructurado.

---

# Specification como contrato para agentes

Una Specification proporciona:

```
Contexto

+

Objetivo

+

Reglas

+

Restricciones

+

Validación
```

---

El agente no recibe solamente una tarea.

Recibe un contrato.

---

Ejemplo:

```yaml
specification:

goal:
  Add premium discounts

rules:
  - Premium users receive discount
  - Maximum discount is 20%

constraints:
  - Preserve existing API

validation:
  - Premium user receives discount
  - Standard user does not
```

---

Ahora el agente tiene un marco de trabajo.

---

# De Prompt Engineering a Specification Engineering

Durante los primeros años de IA generativa apareció una idea:

```
Prompt Engineering
```

La pregunta era:

> ¿Cómo escribimos mejores instrucciones?

---

Pero en sistemas complejos aparece una nueva pregunta:

> ¿Cómo estructuramos conocimiento reusable para que múltiples agentes puedan trabajar?

---

Aquí aparece:

```
Specification Engineering
```

---

La diferencia:

Prompt:

```
Haz esta tarea.
```

---

Specification:

```
Este es el contexto.
Este es el objetivo.
Estas son las reglas.
Estas son las restricciones.
Así validamos el resultado.
```

---

# Agentes especializados

Una arquitectura basada en Specifications permite agentes especializados.

Ejemplo:

```
Product Agent

↓

Functional Specification
```

---

```
Developer Agent

↓

Technical Specification
```

---

```
QA Agent

↓

Acceptance Criteria
```

---

```
Security Agent

↓

Security Specification
```

---

Cada agente consume el conocimiento que necesita.

---

# Orquestación basada en Specifications

Un workflow podría ser:

```
Nueva necesidad

↓

Crear Specification

↓

Review humano

↓

Developer Agent

↓

QA Agent

↓

Security Agent

↓

Evidence Agent

↓

Aprobación humana
```

---

La Specification funciona como contrato común.

---

# Restricciones: la pieza olvidada

Una de las partes más importantes para agentes son las restricciones.

Sin restricciones:

```
Agente optimiza solución.
```

---

Con restricciones:

```
Agente optimiza solución
dentro del espacio permitido.
```

---

Ejemplo:

Sin restricción:

```
Mejora performance.
```

---

Con restricción:

```
Mejora performance.

No modificar contrato público.

Mantener compatibilidad Angular 20.

No aumentar bundle inicial.
```

---

Ahora el agente puede razonar mejor.

---

# Evidencia generada por agentes

Un agente no debería terminar diciendo:

```
Listo, terminé.
```

---

Un flujo más confiable:

```
Implementación

↓

Tests

↓

Validaciones

↓

Reporte de evidencia

↓

Revisión humana
```

---

La evidencia es parte del contrato.

---

# Human-in-the-middle

SDD encaja naturalmente con HITM.

El humano no desaparece.

Cambia de rol.

---

Antes:

```
Humano escribe código.
```

---

Ahora:

```
Humano define intención.

Agente ejecuta.

Humano valida.
```

---

El humano se concentra en:

- decisiones;
- prioridades;
- riesgos;
- aprobación.

---

# Agentes y trazabilidad

Un agente debería poder responder:

```
¿Por qué hice este cambio?
```

Respuesta:

```
Porque Specification SPEC-123
versión 2.1 requería este comportamiento.
```

---

También:

```
¿Qué validaciones ejecuté?
```

Respuesta:

```
Tests X,Y,Z aprobados.
```

---

# 📖 Evolución del pensamiento

La evolución del desarrollo asistido:

```
Buscar código manualmente

↓

Copilot como asistente

↓

Chat con contexto

↓

Agentes especializados

↓

Agentes gobernados por Specifications
```

---

La diferencia clave:

Antes:

```
IA que genera código.
```

Ahora:

```
IA que ejecuta conocimiento estructurado.
```

---

# Caso de estudio: Your Harness

Este es uno de los conceptos centrales detrás de una plataforma como Your Harness.

Una posible visión:

```
Specification

↓

Orchestrator

↓

Agents

↓

Tools

↓

Evidence

↓

Human Approval
```

---

El objetivo no sería simplemente generar código.

Sería coordinar ingeniería basada en conocimiento.

---

Pero es importante mantener la perspectiva correcta:

Your Harness continúa siendo una idea y un proyecto en desarrollo. Estas arquitecturas representan hipótesis de diseño y aprendizaje, no una plataforma terminada ni validada en producción.

---

# 🧠 AI Engineer Mindset

Un desarrollador pregunta:

> ¿Qué prompt le doy al modelo?

Un AI Engineer pregunta:

> ¿Qué conocimiento estructurado necesita el agente para tomar una buena decisión?

---

# Resumen

En este capítulo aprendimos:

- los agentes necesitan contexto estructurado;
- una Specification funciona como contrato para IA;
- las restricciones son fundamentales;
- los agentes deben producir evidencia;
- SDD habilita colaboración humano-agente.

---

# Ejercicio

Diseña una Specification para entregársela a un agente IA.

Incluye:

```
Contexto

Objetivo

Restricciones

Criterios de aceptación

Evidencia esperada
```

Luego responde:

¿Qué errores podría cometer el agente sin esa Specification?

---

# Proyecto incremental

En el próximo capítulo construiremos sobre esta idea:

```
Specifications

↓

Workflows

↓

Agentes

↓

Ejecución controlada
```

Veremos cómo transformar una Specification en un proceso completo de ingeniería.
