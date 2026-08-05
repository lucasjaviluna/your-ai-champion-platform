---
sidebar_position: 10
title: "La especificación como contrato de ingeniería"
description: "Cómo transformar una especificación en un artefacto listo para desarrollo, testing y colaboración."
---

# La especificación como contrato de ingeniería

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Comprender una especificación como contrato entre equipos.
- Identificar cuándo una especificación está lista para desarrollo.
- Conectar especificaciones con desarrollo, QA y arquitectura.
- Preparar una especificación para sistemas asistidos por IA.
- Entender la transición hacia SDD.

---

## ⏱ Tiempo estimado

60 minutos.

---

# Introducción

Durante este módulo aprendimos a responder diferentes preguntas:

| Pregunta | Artefacto |
|---|---|
| ¿Por qué existe? | Objetivo |
| ¿Quién participa? | Actores |
| ¿Qué debe ocurrir? | Casos de uso |
| ¿Qué reglas existen? | Reglas de negocio |
| ¿Cómo verificamos? | Criterios de aceptación |
| ¿Qué pasa en casos especiales? | Escenarios |
| ¿Qué límites existen? | Restricciones |

Ahora debemos unir todo.

---

# La especificación como contrato

Una especificación funciona como un contrato entre diferentes participantes.

No es un contrato legal.

Es un acuerdo de conocimiento.

---

## Negocio

Necesita responder:

```
¿El sistema resuelve la necesidad?
```

---

## Desarrollo

Necesita responder:

```
¿Qué comportamiento debo implementar?
```

---

## QA

Necesita responder:

```
¿Cómo verifico que funciona?
```

---

## Arquitectura

Necesita responder:

```
¿Qué restricciones debo respetar?
```

---

## IA

Necesita responder:

```
¿Qué contexto necesito para ayudar correctamente?
```

---

# De documento a contrato

Una especificación inicial puede verse así:

```
Crear favoritos.
```

Tiene poco valor.

Después de evolucionar:

```
Objetivo definido

+

Actores

+

Casos de uso

+

Reglas

+

Criterios

+

Escenarios

+

Restricciones
```

Ahora representa conocimiento estructurado.

---

# Cuándo está lista una especificación

Una especificación nunca está completamente perfecta.

Pero podemos definir un nivel de preparación.

---

# Specification Ready

Una especificación está lista cuando:

## Objetivo claro

Sabemos qué problema resolver.

---

## Alcance definido

Sabemos qué incluye y qué no.

---

## Actores identificados

Sabemos quién participa.

---

## Comportamiento definido

Existen casos de uso.

---

## Reglas conocidas

Las decisiones importantes están explícitas.

---

## Validación posible

Existen criterios de aceptación.

---

## Riesgos visibles

Las dudas están documentadas.

---

# Caso de estudio — AI Academy

Nuestra especificación inicial comenzó como:

```
Agregar favoritos.
```

Ahora evolucionó a:

```
SPEC-001

Favoritos de cursos

Objetivo:
Permitir estudiantes guardar cursos.

Actor:
Estudiante autenticado.

Casos de uso:
UC-001 Agregar favorito.

Reglas:
BR-001 Usuario autenticado.

Criterios:
AC-001 Operación exitosa.

Restricciones:
Persistencia y seguridad.
```

---

# El valor de estructurar información

Una especificación estructurada permite diferentes usos.

---

## Para humanos

Permite:

- entender,
- discutir,
- revisar.

---

## Para herramientas

Permite:

- generar tareas,
- crear documentación,
- validar cambios.

---

## Para IA

Permite:

- generar código,
- proponer pruebas,
- detectar inconsistencias.

---

# La especificación como contexto IA

Una IA no conoce nuestro dominio.

Necesita contexto.

Comparemos.

---

## Sin especificación

```
Crea una funcionalidad de favoritos.
```

---

## Con especificación

```
Implementa UC-001.

Contexto:

Actor:
Estudiante autenticado.

Reglas:
BR-001.

Criterios:
AC-001.

Restricciones:
RNF-001.
```

---

La segunda opción reduce interpretación.

---

# Preparando el camino hacia SDD

Hasta ahora hicimos:

```
Problema

↓

Especificación

↓

Validación
```

SDD agregará:

```
Especificación

↓

Planificación

↓

Implementación

↓

Validación automática
```

La diferencia es que la especificación pasa de ser documentación a ser una fuente activa del desarrollo.

---

# Especificación viva

Un error común es crear documentación que queda olvidada.

Una especificación profesional debe evolucionar junto al sistema.

Ejemplo:

```
v1

Favoritos básicos


v2

Agregar categorías


v3

Compartir favoritos
```

Cada cambio debe actualizar conocimiento.

---

# 💡 Consejo AI Champion

El código cambia rápido.

El conocimiento del sistema debe cambiar con él.

La especificación es el lugar donde ese conocimiento debe permanecer.

---

# Buenas prácticas

- Mantener versiones.
- Registrar decisiones.
- Relacionar artefactos.
- Evitar documentación duplicada.
- Mantener trazabilidad.

---

# Errores comunes

## Crear documentos enormes

Una especificación debe ser útil, no burocrática.

---

## Escribir después del desarrollo

Pierde gran parte de su valor.

---

## Mezclar problema y solución

Primero entender.

Después diseñar.

---

# Conceptos clave

- Una especificación es un contrato de conocimiento.
- Une negocio, desarrollo, QA e IA.
- Debe ser verificable.
- Debe evolucionar.
- Es la base de SDD.

---

# Resumen del módulo

Durante este módulo construimos:

```
Necesidad

↓

Especificación

↓

Casos de uso

↓

Reglas

↓

Criterios

↓

Escenarios

↓

Restricciones

↓

Validación
```

Este proceso permite transformar una idea ambigua en conocimiento estructurado.

---

# Ejercicio final del módulo

Crear una especificación completa para una funcionalidad real.

Debe incluir:

- Objetivo.
- Actores.
- Alcance.
- Caso de uso.
- Reglas de negocio.
- Criterios de aceptación.
- Escenarios alternativos.
- Restricciones.
- Revisión final.

---

# Desafío AI Champion

Entrega la especificación a una IA y solicita:

```
Actúa como un equipo completo:

Product Owner.
Arquitecto.
QA.
Developer.

Analiza la especificación.

Indica:

- preguntas pendientes,
- riesgos,
- escenarios faltantes,
- posibles mejoras.
```

---

# Próximo módulo

## Specification-Driven Development (SDD)

En el siguiente módulo veremos cómo llevar esta disciplina al siguiente nivel:

```
Especificación

↓

Plan de implementación

↓

Tareas

↓

Código

↓

Pruebas

↓

Validación
```

Y comenzaremos a estudiar herramientas como:

- OpenSpec.
- SpecKit.
- flujos asistidos por IA.
- agentes orientados a especificaciones.
