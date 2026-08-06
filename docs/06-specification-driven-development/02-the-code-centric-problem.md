---
sidebar_position: 2
title: "El problema del desarrollo centrado en el código"
description: "Comprender las limitaciones del desarrollo code-centric y por qué surge Specification-Driven Development."
---

# El problema del desarrollo centrado en el código

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Comprender cómo evolucionó el desarrollo de software.
- Identificar las limitaciones del enfoque centrado en el código.
- Entender por qué el conocimiento termina fragmentado.
- Descubrir por qué SDD propone un cambio de paradigma.
- Relacionar estos problemas con el uso de IA.

---

# Introducción

Durante muchos años, el software se desarrolló con una idea implícita:

> El código es el producto.

Y, en gran medida, esa afirmación sigue siendo cierta.

El problema aparece cuando confundimos **el producto** con **la fuente de conocimiento**.

---

# La evolución del desarrollo de software

Podemos simplificar la evolución histórica de esta manera:

```text
Programador individual
        ↓
Equipos pequeños
        ↓
Arquitecturas multicapa
        ↓
Sistemas distribuidos
        ↓
Microservicios
        ↓
Cloud
        ↓
AI Engineering
```

A medida que los sistemas crecieron, también creció la complejidad.

Sin embargo, muchos equipos siguieron utilizando prácticamente el mismo mecanismo para transmitir conocimiento:

```text
Leer el código.
```

---

# Cuando el código se convierte en documentación

Imagina que un nuevo desarrollador se incorpora al equipo.

Quiere responder una pregunta sencilla:

> ¿Cómo se calcula el descuento para clientes premium?

Frecuentemente la respuesta es:

```text
Buscá el método.

↓

Seguí las llamadas.

↓

Leé varios servicios.

↓

Revisá las consultas.

↓

Probá el sistema.
```

Es decir, para entender una regla de negocio primero debe reconstruir la implementación.

---

# El conocimiento termina distribuido

En un proyecto típico, la información puede quedar repartida entre múltiples lugares:

```text
Product Owner

↓

Jira

↓

Slack

↓

Correo

↓

Documentación

↓

Pull Requests

↓

Código

↓

Memoria del equipo
```

Cada fuente contiene una parte de la historia.

Ninguna contiene la historia completa.

---

# El problema de la interpretación

Supongamos que un requerimiento dice:

> Aplicar descuentos especiales a clientes premium.

Cada persona puede interpretar algo distinto.

El Product Owner piensa en una regla comercial.

El desarrollador piensa en una condición `if`.

El QA piensa en casos de prueba.

El arquitecto piensa en el impacto sobre otros servicios.

Todos trabajan sobre la misma frase, pero con modelos mentales diferentes.

---

# El costo del conocimiento implícito

Cuando una decisión no queda documentada, aparece el conocimiento implícito.

Por ejemplo:

```text
¿Por qué usamos Redis aquí?

↓

Porque siempre fue así.
```

O:

```text
¿Por qué este endpoint devuelve 202?

↓

No estamos seguros.
```

Con el paso del tiempo, estas decisiones dejan de tener una justificación visible.

---

# Cuando llega la IA

Los modelos de IA tienen una limitación importante:

No conocen el proyecto.

Solo conocen el contexto que reciben.

Si el conocimiento está distribuido entre conversaciones, tickets y memoria del equipo, el agente tampoco podrá reconstruirlo de manera confiable.

El problema no es la IA.

El problema es la falta de una fuente de verdad.

---

# El código responde al "cómo"

El código es excelente para explicar:

```text
¿Cómo funciona esta implementación?
```

Pero rara vez responde preguntas como:

- ¿Por qué se tomó esta decisión?
- ¿Qué alternativas se descartaron?
- ¿Cuál era el objetivo original?
- ¿Qué restricciones debía cumplir?
- ¿Qué criterios determinan que el trabajo está terminado?

---

# El costo del cambio

Modificar un sistema no consiste únicamente en cambiar código.

También implica comprender:

- reglas de negocio,
- restricciones,
- impacto,
- dependencias,
- decisiones previas.

Cuando esa información no está disponible, el costo del cambio aumenta.

---

# El cambio de perspectiva

En lugar de pensar:

```text
El código describe el sistema.
```

SDD propone pensar:

```text
La Specification describe el sistema.

↓

El código implementa la Specification.
```

Es un cambio sutil, pero profundo.

---

# Un ejemplo

Supongamos que una empresa quiere agregar un nuevo método de pago.

En un enfoque tradicional, el equipo podría comenzar modificando el código.

En un enfoque basado en SDD, primero respondería preguntas como:

- ¿Cuál es el objetivo de negocio?
- ¿Qué reglas debe cumplir?
- ¿Qué restricciones existen?
- ¿Cómo sabremos que la funcionalidad está completa?
- ¿Qué impacto tendrá sobre el resto del sistema?

Recién después comenzaría la implementación.

---

# ¿Significa que el código pierde importancia?

No.

El código sigue siendo el producto ejecutable.

Lo que cambia es su rol.

En lugar de ser la fuente principal de conocimiento, pasa a ser una implementación de una especificación previamente acordada.

---

# Caso de estudio: Your Harness

Imaginemos que estamos diseñando un runtime para agentes.

Sin una especificación, distintos desarrolladores podrían asumir responsabilidades diferentes para el runtime, el orquestador o el sistema de memoria.

Una posible aplicación de SDD sería definir primero los contratos de cada componente y, solo después, implementar el código correspondiente.

Esto no implica que esa sea la arquitectura definitiva de Your Harness, sino un ejemplo de cómo aplicar el paradigma en un proyecto en evolución.

---

# 🧠 AI Engineer Mindset

Cuando un sistema crece, el mayor problema deja de ser escribir código.

El verdadero desafío pasa a ser **preservar el conocimiento**.

Un AI Engineer entiende que el código es una consecuencia del conocimiento compartido, no su reemplazo.

---

# Resumen

En este capítulo aprendimos que:

- el conocimiento suele quedar fragmentado;
- el código explica la implementación, pero no siempre la intención;
- los equipos interpretan un mismo requerimiento de maneras diferentes;
- la IA necesita contexto explícito para producir buenos resultados;
- SDD busca convertir la especificación en la principal fuente de conocimiento.

---

# Ejercicio

Piensa en un proyecto en el que hayas participado y responde:

1. ¿Qué información solo conocían determinadas personas?
2. ¿Qué decisiones importantes nunca quedaron documentadas?
3. Si un agente IA tuviera que modificar ese proyecto hoy, ¿qué información le faltaría para hacerlo con confianza?

---

# Proyecto incremental

En el próximo capítulo comenzaremos a construir el concepto central del módulo:

> **La Specification como fuente de verdad.**

A partir de ese momento, todas las piezas del proceso —desarrollo, pruebas, documentación y agentes IA— girarán alrededor de ese único artefacto.
