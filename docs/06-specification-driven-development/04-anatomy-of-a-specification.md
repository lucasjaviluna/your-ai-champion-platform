---
sidebar_position: 4
title: "Anatomía de una Specification"
description: "Comprender los componentes que forman una Specification moderna y cómo estructurar contratos de conocimiento."
---

# Anatomía de una Specification

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Comprender los componentes principales de una Specification.
- Diferenciar información esencial de información accidental.
- Diseñar Specifications claras y mantenibles.
- Entender cómo una Specification puede ser consumida por humanos y agentes IA.
- Preparar la base para formatos estructurados.

---

# Introducción

En capítulos anteriores definimos una idea fundamental:

> Una Specification es la fuente de verdad del conocimiento necesario para construir una solución.

Ahora aparece una nueva pregunta:

> ¿Cómo se estructura ese conocimiento?

Una Specification demasiado simple no aporta suficiente contexto.

Una Specification demasiado extensa se vuelve difícil de mantener.

El objetivo es encontrar un equilibrio.

---

# Una Specification no es un documento tradicional

Antes de definir una estructura debemos aclarar algo.

Una Specification NO es:

```
Un documento escrito para cumplir un proceso.
```

Tampoco es:

```
Un resumen de una reunión.
```

Una Specification es:

```
Un contrato que define qué debe existir,
por qué debe existir,
y cómo verificamos que existe correctamente.
```

---

# Modelo conceptual

Podemos pensar una Specification como cinco grandes bloques:

```
Specification

├── Contexto
│
├── Intención
│
├── Contrato funcional
│
├── Restricciones
│
└── Validación
```

---

# 1. Contexto

El primer elemento responde:

> ¿Por qué estamos haciendo esto?

Incluye información como:

- problema actual;
- situación del negocio;
- usuarios afectados;
- sistemas relacionados;
- motivación.

---

Ejemplo:

```
Contexto:

Los usuarios premium actualmente reciben
beneficios únicamente durante campañas manuales.

Se requiere automatizar la aplicación
de beneficios según su nivel.
```

---

El contexto evita que una implementación pierda el propósito original.

---

# 2. Intención

La intención responde:

> ¿Qué queremos lograr?

Normalmente se expresa como un objetivo.

Ejemplo:

```
Objetivo:

Permitir que clientes premium reciban
beneficios automáticamente al realizar
una compra.
```

---

Una buena intención debe explicar el resultado esperado.

No debe describir una solución técnica prematura.

---

Incorrecto:

```
Crear una tabla llamada PremiumDiscount.
```

Correcto:

```
Permitir gestionar descuentos para clientes premium.
```

---

# 3. Contrato funcional

Esta es probablemente la parte más conocida.

Define:

- comportamientos esperados;
- reglas de negocio;
- escenarios;
- casos límite.

---

Ejemplo:

```
Reglas:

- Un cliente premium obtiene descuento.
- El descuento máximo permitido es 30%.
- Los descuentos no se acumulan.
```

---

Aquí aparece una diferencia importante.

La Specification define:

```
Qué debe ocurrir.
```

No necesariamente:

```
Cómo implementarlo.
```

---

# 4. Restricciones

Todo sistema tiene límites.

Una Specification debe capturarlos.

Ejemplos:

```
Restricciones:

- Mantener compatibilidad con API existente.
- No modificar contratos públicos.
- Cumplir requisitos regulatorios.
- Mantener tiempos de respuesta actuales.
```

---

Las restricciones son especialmente importantes para agentes IA.

Sin ellas, un agente puede generar soluciones técnicamente correctas pero incompatibles con el sistema.

---

# 5. Validación

Una Specification incompleta dice:

```
Construir funcionalidad X.
```

Una Specification madura agrega:

```
¿Cómo sabemos que está terminada?
```

---

Ejemplo:

```
Criterios de aceptación:

✓ Usuario premium recibe descuento.

✓ Usuario estándar no recibe descuento.

✓ Descuento máximo respetado.

✓ Evento registrado correctamente.
```

---

Esta sección conecta directamente con testing.

---

# Estructura completa

Una Specification podría verse así:

```yaml
specification:

  metadata:
    id: SPEC-001
    version: 1.0

  context:
    problem: ""
    motivation: ""

  objective:
    description: ""

  requirements:
    functional:
      - ""

  constraints:
    - ""

  acceptance:
    - ""

  evidence:
    - ""
```

---

# Specification como contrato multidimensional

Una característica importante de una Specification moderna es que no solamente sirve al desarrollador.

Puede ser utilizada por:

```
Producto

↓

Arquitectura

↓

Desarrollo

↓

QA

↓

Seguridad

↓

Agentes IA

↓

Operaciones
```

---

Cada uno extrae información diferente.

---

# El problema de las Specifications pobres

Ejemplo:

```
Crear módulo de pagos.
```

Aunque parece una Specification, realmente no lo es.

Faltan:

- contexto;
- alcance;
- reglas;
- restricciones;
- validación.

---

Una Specification pobre solamente cambia un ticket por un documento.

---

# Una Specification madura

Ejemplo:

```
Objetivo:

Permitir pagos con tarjeta para clientes
registrados.

Reglas:

- Validar identidad del usuario.
- Registrar transacciones.
- Manejar rechazos externos.

Restricciones:

- Mantener API actual.
- Cumplir auditoría.

Validación:

- Pago aprobado.
- Pago rechazado.
- Error del proveedor.
```

---

Ahora diferentes equipos pueden trabajar con una interpretación común.

---

# Specifications y agentes IA

Este punto es fundamental.

Los agentes trabajan mejor con estructuras explícitas.

Comparación:

## Prompt ambiguo

```
Agrega pagos.
```

---

## Specification

```
Objetivo:
Agregar pagos con tarjeta.

Contexto:
Actualmente solo existe pago manual.

Restricciones:
Mantener API existente.

Validación:
Debe soportar aprobación y rechazo.
```

---

El segundo escenario reduce la ambigüedad.

---

# 📖 Evolución del pensamiento

La evolución del artefacto de conocimiento:

```
Notas personales

↓

Documentos

↓

Historias de usuario

↓

Requerimientos estructurados

↓

Specifications

↓

Specifications ejecutables
```

---

La tendencia es pasar de información escrita para humanos a conocimiento estructurado para humanos y máquinas.

---

# Caso de estudio: Your Harness

Una posible plataforma como Your Harness necesitaría definir claramente qué representa una Specification.

Algunas preguntas de diseño serían:

- ¿Será Markdown?
- ¿Será YAML/JSON?
- ¿Será un formato híbrido?
- ¿Tendrá validación automática?
- ¿Podrá generar workflows?

Estas son decisiones de diseño que deberán evaluarse durante la evolución del proyecto.

No existe todavía una implementación definitiva.

---

# 🧠 AI Engineer Mindset

Un ingeniero tradicional pregunta:

> ¿Qué archivos debo modificar?

Un AI Engineer primero pregunta:

> ¿Cuál es el contrato de conocimiento que define este cambio?

---

# Resumen

En este capítulo aprendimos:

- una Specification tiene contexto, intención, reglas, restricciones y validación;
- una Specification no define implementación;
- las restricciones son fundamentales para agentes IA;
- los criterios de aceptación conectan especificación y evidencia;
- una Specification debe servir a múltiples actores.

---

# Ejercicio

Diseña una Specification para una funcionalidad pequeña.

Puede ser:

- login;
- carrito de compras;
- notificaciones;
- búsqueda.

Incluye:

1. Contexto.
2. Objetivo.
3. Reglas.
4. Restricciones.
5. Criterios de aceptación.

---

# Proyecto incremental

En el próximo capítulo analizaremos los diferentes tipos de Specifications:

- funcionales;
- técnicas;
- arquitectónicas;
- operativas;
- de seguridad.

Comprender esta clasificación será clave para diseñar sistemas complejos con agentes IA.
