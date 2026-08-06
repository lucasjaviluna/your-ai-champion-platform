---
sidebar_position: 1
title: "¿Por qué Specification-Driven Development?"
description: "Comprender por qué las especificaciones deben convertirse en el punto de partida del desarrollo moderno."
---

# ¿Por qué Specification-Driven Development?

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Comprender las limitaciones del desarrollo centrado en el código.
- Entender el papel de las especificaciones dentro de un proyecto.
- Identificar los beneficios de Specification-Driven Development (SDD).
- Diferenciar SDD de otras metodologías como TDD o BDD.
- Comprender por qué SDD resulta especialmente relevante en la era de la IA.

---

# Introducción

Durante décadas, el desarrollo de software ha girado alrededor del código.

Cuando un equipo necesitaba implementar una nueva funcionalidad, el proceso habitual era:

```text
Idea

↓

Reunión

↓

Documento (opcional)

↓

Código

↓

Testing

↓

Deploy
```

En muchos proyectos, el código terminó convirtiéndose en la única fuente de verdad.

---

# El problema

Cuando alguien pregunta:

> ¿Cómo funciona este sistema?

Las respuestas suelen ser:

- "Está en el código."
- "Preguntale al desarrollador que lo hizo."
- "Creo que hay un documento viejo..."
- "La documentación está desactualizada."

El conocimiento termina disperso entre:

- personas,
- tickets,
- correos electrónicos,
- documentación,
- código,
- decisiones informales.

---

# ¿Por qué ocurre esto?

Porque el proceso tradicional considera a la documentación como un artefacto secundario.

Normalmente ocurre algo como esto:

```text
Idea

↓

Código

↓

Documentación (si hay tiempo)
```

La documentación se convierte en una consecuencia del desarrollo.

No en su punto de partida.

---

# El cambio de paradigma

Specification-Driven Development propone invertir ese orden.

En lugar de comenzar escribiendo código, comenzamos definiendo claramente qué queremos construir.

El flujo pasa a ser:

```text
Idea

↓

Specification

↓

Planificación

↓

Implementación

↓

Validación

↓

Evidencia
```

La especificación deja de ser un documento opcional y se convierte en el contrato principal del proyecto.

---

# ¿Qué entendemos por Specification?

En este curso utilizaremos el término **Specification** para referirnos a un artefacto que describe de manera precisa una necesidad, un comportamiento o una restricción del sistema.

Una Specification puede incluir, entre otros elementos:

- objetivos,
- alcance,
- reglas de negocio,
- restricciones,
- criterios de aceptación,
- dependencias,
- evidencia esperada.

Más adelante estudiaremos su estructura en detalle.

---

# La Specification como fuente de verdad

En SDD, la pregunta:

> ¿Qué debe hacer el sistema?

no se responde mirando el código.

Se responde consultando la Specification correspondiente.

El código pasa a ser una implementación de esa especificación.

---

# Comparación

## Desarrollo tradicional

```text
Código

↓

Interpretación
```

---

## Specification-Driven Development

```text
Specification

↓

Código

↓

Validación

↓

Evidencia
```

---

# ¿Por qué esto es especialmente importante con IA?

Los modelos de IA generan resultados a partir del contexto que reciben.

Si el contexto es ambiguo, incompleto o contradictorio, el resultado también lo será.

Una Specification bien definida proporciona un contrato claro para:

- desarrolladores,
- agentes IA,
- herramientas,
- revisores,
- equipos de QA.

Todos trabajan sobre la misma definición del problema.

---

# SDD no reemplaza otras prácticas

Es importante aclarar que SDD no pretende reemplazar metodologías existentes.

Por ejemplo:

- **TDD** responde a la pregunta: ¿cómo verificamos que el código funciona?
- **BDD** responde a: ¿cómo describimos el comportamiento esperado?
- **SDD** responde a: ¿qué debemos construir y bajo qué restricciones?

Estas prácticas pueden complementarse.

---

# Beneficios de SDD

Cuando una organización adopta SDD suele obtener ventajas como:

- mayor claridad de objetivos;
- mejor comunicación entre equipos;
- reducción de ambigüedades;
- mejor trazabilidad;
- documentación viva;
- mejor colaboración entre humanos y agentes IA.

---

# Un ejemplo sencillo

Supongamos que el equipo recibe esta solicitud:

> "Agregar descuentos para clientes premium."

Sin una Specification, diferentes personas podrían interpretar requisitos distintos.

Una Specification permite definir aspectos como:

- quién es un cliente premium;
- qué tipos de descuentos existen;
- cuándo aplican;
- qué excepciones deben contemplarse;
- cómo validar que la funcionalidad es correcta.

Antes de escribir una sola línea de código, todos comparten el mismo entendimiento.

---

# Lo que SDD no es

SDD no significa:

- escribir documentos extensos sin utilidad;
- reemplazar el diseño técnico;
- eliminar la colaboración;
- evitar cambios durante el proyecto.

El objetivo no es producir más documentación.

El objetivo es reducir la incertidumbre.

---

# Caso de estudio: Your Harness

A lo largo del curso utilizaremos **Your Harness** como un caso de estudio.

Actualmente es un proyecto en evolución, no un producto terminado.

Cuando aparezca en los ejemplos, lo haremos para explorar posibles decisiones de diseño y analizar cómo podrían aplicarse los principios de SDD en una plataforma real.

Las soluciones presentadas deben entenderse como alternativas de arquitectura, no como implementaciones definitivas.

---

# 🧠 AI Engineer Mindset

Un desarrollador suele preguntarse:

> ¿Cómo implemento esta funcionalidad?

Un AI Engineer comienza antes:

> ¿Cómo defino correctamente el problema para que humanos y agentes puedan resolverlo de forma consistente?

La calidad de la implementación rara vez supera la calidad de la especificación que la guía.

---

# Resumen

En este capítulo vimos que:

- el desarrollo tradicional suele colocar el código en el centro;
- SDD propone colocar la Specification como fuente de verdad;
- las especificaciones reducen ambigüedades;
- SDD complementa otras prácticas como TDD y BDD;
- este paradigma resulta especialmente valioso cuando participan agentes IA.

---

# Ejercicio

Piensa en un proyecto en el que hayas trabajado recientemente.

Responde:

1. ¿Dónde estaba realmente el conocimiento del sistema?
2. ¿Qué problemas generó esa situación?
3. ¿Qué información habría sido útil tener especificada antes de comenzar el desarrollo?

---

# Proyecto incremental

Durante este módulo construiremos progresivamente las Specifications de un sistema de ejemplo y veremos cómo evolucionan a lo largo del ciclo de vida del desarrollo.

En módulos posteriores utilizaremos esas mismas Specifications para integrarlas con herramientas, agentes IA y plataformas de AI Engineering.
