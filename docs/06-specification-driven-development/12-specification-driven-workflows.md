---
sidebar_position: 12
title: "Workflows guiados por Specifications"
description: "Comprender cómo transformar Specifications en procesos de ingeniería ejecutables por humanos y agentes IA."
---

# Workflows guiados por Specifications

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Comprender la relación entre Specifications y workflows.
- Diseñar procesos de ingeniería basados en conocimiento.
- Entender cómo los agentes participan dentro de un flujo controlado.
- Diferenciar automatización de autonomía.
- Preparar arquitecturas orientadas a agentes.

---

# Introducción

En los capítulos anteriores construimos una idea:

Una Specification contiene:

```
Contexto

Objetivo

Reglas

Restricciones

Validación
```

Pero todavía falta una dimensión:

```
¿Qué pasos seguimos para convertir esto en realidad?
```

---

La respuesta es:

```
Workflow
```

---

# ¿Qué es un workflow?

Un workflow define:

- etapas;
- responsables;
- entradas;
- salidas;
- validaciones.

---

Ejemplo simple:

```
Idea

↓

Specification

↓

Review

↓

Implementación

↓

Testing

↓

Release
```

---

En SDD, el workflow gira alrededor de la Specification.

---

# Desarrollo tradicional vs SDD

## Desarrollo tradicional

```
Ticket

↓

Desarrollador

↓

Código

↓

Review
```

---

El conocimiento está distribuido.

---

## SDD

```
Specification

↓

Workflow

↓

Agentes/Humanos

↓

Implementación

↓

Evidence
```

---

La Specification coordina el proceso.

---

# Specification como punto de inicio

Una nueva funcionalidad podría comenzar así:

```
SPEC-001

Agregar pagos internacionales
```

La Specification define:

```
Objetivo:

Permitir pagos internacionales.

Restricciones:

Mantener API actual.

Validación:

Pago aprobado y rechazado.
```

---

A partir de esto comienza el workflow.

---

# Ejemplo de workflow

```
                    Specification

                         |

                         ↓

                 Analysis Agent

                         |

                         ↓

                Architecture Review

                         |

                         ↓

                Development Agent

                         |

                         ↓

                    QA Agent

                         |

                         ↓

               Human Approval
```

---

Cada etapa consume y produce conocimiento.

---

# Estados del workflow

Un modelo posible:

```text
CREATED

↓

ANALYZING

↓

DESIGNED

↓

IMPLEMENTING

↓

VALIDATING

↓

APPROVED

↓

RELEASED
```

---

Cada estado tiene condiciones.

---

Ejemplo:

No se puede pasar:

```
IMPLEMENTING

↓

RELEASED
```

sin evidencia suficiente.

---

# Workflow como máquina de estados

Una visión más formal:

```
          CREATED

             |

             v

        SPEC REVIEW

             |

             v

        IMPLEMENTATION

             |

             v

         VALIDATION

             |

             v

          RELEASE
```

---

Cada transición puede requerir:

- aprobación;
- evidencia;
- validaciones.

---

# Agentes dentro del workflow

Los agentes no deberían trabajar libremente.

Trabajan dentro de límites.

---

Ejemplo:

## Architecture Agent

Entrada:

```
Functional Specification
```

Salida:

```
Architecture Proposal
```

---

## Developer Agent

Entrada:

```
Technical Specification
```

Salida:

```
Code Changes
```

---

## QA Agent

Entrada:

```
Acceptance Criteria
```

Salida:

```
Validation Evidence
```

---

# Automatización vs autonomía

Este punto es importante.

Automatizar significa:

```
Ejecutar pasos conocidos automáticamente.
```

---

Autonomía significa:

```
Tomar decisiones nuevas sin supervisión.
```

---

SDD permite principalmente:

```
Automatización gobernada.
```

---

El objetivo no es eliminar control.

Es reducir trabajo repetitivo.

---

# Human-in-the-middle dentro del workflow

Un workflow profesional incluye puntos humanos.

Ejemplo:

```
Specification creada

↓

IA analiza

↓

Humano revisa

↓

IA implementa

↓

IA valida

↓

Humano aprueba
```

---

Los humanos mantienen:

- intención;
- responsabilidad;
- decisiones críticas.

---

# Workflow y evidencia

Cada etapa puede generar evidencia.

Ejemplo:

```
Architecture Agent

↓

Architecture Proposal

↓

Review Approval
```

---

```
Development Agent

↓

Pull Request

↓

Tests Passed
```

---

```
QA Agent

↓

Validation Report
```

---

El resultado final es auditable.

---

# 📖 Evolución del pensamiento

La evolución del desarrollo:

```
Personas ejecutando tareas

↓

Procesos documentados

↓

Pipelines automatizados

↓

Workflows inteligentes

↓

Workflows gobernados por conocimiento
```

---

La diferencia:

Antes:

```
El proceso controla la ejecución.
```

Ahora:

```
El conocimiento define el proceso.
```

---

# Caso de estudio: Your Harness

Una visión posible de Your Harness sería:

```
Specification

↓

Workflow Engine

↓

Agent Orchestrator

↓

Tools

↓

Evidence Store
```

---

El objetivo sería que un proyecto no sea solamente:

```
Código + Issues
```

sino:

```
Knowledge + Workflow + Execution
```

---

Nuevamente:

Your Harness continúa siendo un proyecto experimental en evolución. Estos conceptos representan una dirección arquitectónica posible, no una solución final probada.

---

# 🧠 AI Engineer Mindset

Un desarrollador pregunta:

> ¿Qué tarea debo hacer?

Un AI Engineer pregunta:

> ¿Qué conocimiento y workflow permiten ejecutar esta tarea correctamente?

---

# Resumen

En este capítulo aprendimos:

- una Specification puede iniciar un workflow;
- los agentes deben trabajar dentro de procesos controlados;
- los workflows pueden tener estados y transiciones;
- la evidencia debe acompañar cada etapa;
- la autonomía requiere gobernanza.

---

# Ejercicio

Diseña un workflow para una funcionalidad nueva.

Debe incluir:

```
Specification

↓

Análisis

↓

Diseño

↓

Implementación

↓

Validación

↓

Aprobación
```

Para cada etapa define:

- responsable;
- entrada;
- salida;
- evidencia.

---

# Proyecto incremental

En el próximo capítulo veremos:

```
Buenas prácticas

+

Anti-patrones

+

Errores comunes al implementar SDD
```

Porque entender qué evitar es tan importante como saber qué construir.
