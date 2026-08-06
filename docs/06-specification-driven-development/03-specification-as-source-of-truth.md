---
sidebar_position: 3
title: "La Specification como fuente de verdad"
description: "Comprender cómo las especificaciones se convierten en el núcleo de conocimiento de un sistema de ingeniería moderno."
---

# La Specification como fuente de verdad

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Comprender qué significa "fuente de verdad" en ingeniería de software.
- Diferenciar documentación tradicional de especificaciones vivas.
- Entender la relación entre Specification, código y evidencia.
- Identificar qué información debe vivir en una Specification.
- Comprender por qué este concepto es fundamental para AI Engineering.

---

# Introducción

En ingeniería de software existe un concepto recurrente:

```
Single Source of Truth
```

o:

```
Fuente única de verdad
```

La idea es simple:

> Para una determinada información crítica debe existir un lugar principal donde esa información sea mantenida y consultada.

---

# El problema de múltiples verdades

Un sistema puede tener diferentes representaciones:

```
Requerimiento

↓

Ticket

↓

Documento

↓

Código

↓

Tests

↓

Manual de usuario
```

El problema aparece cuando esas representaciones empiezan a divergir.

---

Ejemplo:

El ticket dice:

```
Máximo 5 intentos de login.
```

El código implementa:

```
Máximo 3 intentos.
```

La documentación dice:

```
Máximo 10 intentos.
```

¿Cuál es la verdad?

---

# El costo de la inconsistencia

Cuando existen múltiples fuentes:

- aumenta la incertidumbre;
- aparecen errores;
- las decisiones son difíciles de justificar;
- los nuevos integrantes tardan más en comprender el sistema.

---

# El papel tradicional de la documentación

Históricamente la documentación tuvo diferentes roles:

## Documentación antes del desarrollo

En algunos procesos tradicionales:

```
Documento

↓

Código
```

---

Problema:

La documentación podía quedar desactualizada rápidamente.

---

## Documentación después del desarrollo

En muchos equipos modernos:

```
Código

↓

Documentación (si existe)
```

---

Problema:

La documentación explica qué existe, pero no siempre explica por qué existe.

---

# La propuesta de SDD

Specification-Driven Development propone una posición diferente:

```
Specification

↓

Implementación

↓

Validación

↓

Evidencia
```

La Specification no describe únicamente el resultado.

Define la intención.

---

# Intención vs implementación

Esta diferencia es fundamental.

El código responde:

```
¿Cómo funciona?
```

La Specification responde:

```
¿Qué problema resolvemos?

¿Por qué existe?

¿Qué condiciones debe cumplir?
```

---

Ejemplo:

Código:

```typescript
if(user.level === "PREMIUM"){
   discount = 20;
}
```

Puede decirnos cómo funciona.

Pero no explica:

- por qué PREMIUM tiene descuento;
- si 20% es una regla permanente;
- quién aprobó esa decisión;
- qué ocurre en casos especiales.

---

La Specification contiene ese contexto.

---

# Specification como contrato

Una forma útil de pensar una Specification es:

```
Contrato entre:

Negocio

↓

Arquitectura

↓

Desarrollo

↓

QA

↓

Operaciones
```

---

Todos interpretan el mismo contrato.

---

# Anatomía conceptual de una Specification

Aunque veremos la estructura detallada más adelante, normalmente contiene:

```text
Specification

├── Objetivo

├── Contexto

├── Alcance

├── Reglas

├── Restricciones

├── Criterios de aceptación

├── Dependencias

└── Evidencia esperada
```

---

# Specification y código

Es importante aclarar:

La Specification no reemplaza al código.

La relación correcta es:

```
Specification

        ↓

Código

        ↓

Comportamiento ejecutable
```

---

El código es una implementación posible de la Specification.

---

# Specification y tests

Los tests también derivan de la Specification.

Ejemplo:

Specification:

```
Un usuario bloquea su cuenta después de 5 intentos fallidos.
```

Tests:

```
Caso 1:
4 intentos fallidos.
Cuenta activa.

Caso 2:
5 intentos fallidos.
Cuenta bloqueada.
```

---

La Specification define qué debe validarse.

---

# Specification y agentes IA

Aquí aparece uno de los motivos principales por los cuales SDD es especialmente relevante hoy.

Un agente IA necesita contexto.

Si recibe:

```
Crear módulo de pagos.
```

Tiene demasiadas interpretaciones posibles.

---

Pero si recibe:

```
Specification:

Objetivo:
Agregar pagos con tarjeta.

Restricciones:
- Mantener compatibilidad existente.
- Usar proveedor X.
- Registrar auditoría.

Criterios:
- Pago aprobado.
- Pago rechazado.
- Error externo.
```

El agente tiene un contrato mucho más preciso.

---

# Specification como Knowledge Object

En AI Engineering, una Specification puede verse como un objeto de conocimiento.

No es solamente texto.

Contiene:

```
Contexto

↓

Intención

↓

Restricciones

↓

Decisiones

↓

Validaciones
```

---

Esto permite que diferentes sistemas puedan utilizarla:

```
Humano

↓

Agente IA

↓

Pipeline

↓

Herramientas

↓

Evaluadores
```

---

# 📖 Evolución del pensamiento

La evolución del desarrollo puede verse así:

```
Código como fuente de verdad

↓

Documentación complementaria

↓

Documentación viva

↓

Configuración como código

↓

Infraestructura como código

↓

Especificación como conocimiento estructurado
```

---

El cambio fundamental es:

Antes:

```
El sistema explica la intención.
```

Ahora:

```
La intención guía la construcción del sistema.
```

---

# Caso de estudio: Your Harness

Una posible arquitectura para una plataforma como Your Harness podría considerar las Specifications como artefactos centrales.

Por ejemplo:

```
Specification

↓

Workflow

↓

Agentes

↓

Cambios

↓

Evidencia
```

Esto permitiría que un futuro sistema pueda responder preguntas como:

```
¿Por qué se creó este cambio?

¿Qué reglas debía cumplir?

¿Qué agentes participaron?

¿Qué validaciones fueron realizadas?
```

No significa que esta arquitectura ya exista en Your Harness. Es una posible dirección de diseño para un proyecto en evolución.

---

# 🧠 AI Engineer Mindset

Un ingeniero tradicional piensa:

> El código es donde vive el sistema.

Un AI Engineer piensa:

> El conocimiento estructurado es lo que permite construir, modificar y evolucionar el sistema.

---

# Resumen

En este capítulo aprendimos que:

- una fuente de verdad evita inconsistencias;
- una Specification define intención, reglas y restricciones;
- el código implementa una Specification;
- los tests validan una Specification;
- los agentes IA necesitan Specifications para trabajar con mayor precisión.

---

# Ejercicio

Selecciona una funcionalidad real de un sistema que conozcas.

Define:

1. ¿Cuál sería su Specification?
2. ¿Qué información debería contener?
3. ¿Qué decisiones hoy están solamente implícitas en el código?

---

# Proyecto incremental

En el próximo capítulo construiremos la estructura interna de una Specification:

```
¿Qué elementos debe contener?

¿Cómo se organiza?

¿Cómo evoluciona?
```

Comenzaremos a diseñar el primer contrato formal de conocimiento.
