---
sidebar_position: 3
title: "Construyendo la primera especificación"
description: "Aprende a transformar un requerimiento ambiguo en una especificación estructurada utilizando un proceso sistemático."
---

# Construyendo la primera especificación

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Construir una especificación a partir de un requerimiento.
- Separar hechos, reglas y decisiones.
- Identificar información faltante.
- Organizar una especificación de forma profesional.
- Comprender que una especificación evoluciona con el proyecto.

---

## ⏱ Tiempo estimado

75 minutos.

---

# Introducción

En el capítulo anterior aprendimos a identificar ambigüedades.

Ahora responderemos una nueva pregunta:

> ¿Cómo organizamos toda esa información?

Muchos equipos escriben especificaciones como documentos largos.

Cada integrante busca información en distintas secciones.

Las preguntas aparecen mezcladas con decisiones técnicas.

Las reglas de negocio conviven con notas internas.

Después de algunos meses, nadie sabe cuál es la versión correcta.

Specification Engineering propone otro enfoque.

La especificación debe ser un modelo estructurado del problema.

---

# Del requerimiento al conocimiento

Nuestro requerimiento sigue siendo el mismo.

> Los usuarios podrán marcar cursos como favoritos.

No escribiremos código.

No hablaremos de Angular.

No hablaremos de bases de datos.

Solo construiremos conocimiento.

---

# Primer principio

## Una especificación no intenta responder todo al mismo tiempo.

Debe crecer de manera incremental.

Podemos imaginarla como un árbol.

```text
Especificación

├── Objetivo
├── Actores
├── Reglas
├── Casos de uso
├── Restricciones
├── Casos límite
├── Preguntas abiertas
└── Criterios de aceptación
```

Cada rama responde un tipo diferente de pregunta.

---

# Paso 1 - Definir el objetivo

Toda especificación debería comenzar explicando por qué existe.

Ejemplo:

```text
Objetivo

Permitir que los estudiantes puedan identificar rápidamente
los cursos que desean consultar posteriormente,
manteniendo esa información sincronizada
entre todos sus dispositivos.
```

Observa que todavía no hablamos de implementación.

---

# Paso 2 - Identificar actores

Ahora debemos responder:

¿Quién interactúa con esta funcionalidad?

En AI Academy encontramos inicialmente:

| Actor | Participa |
|--------|-----------|
| Estudiante | Sí |
| Instructor | Pendiente de definir |
| Administrador | No directamente |
| Sistema | Sí |

En este punto no estamos tomando decisiones.

Estamos identificando participantes.

---

# Paso 3 - Extraer hechos

Un hecho representa algo que sabemos.

Ejemplo:

```text
✓ Un curso existe.

✓ Un estudiante existe.

✓ Un estudiante puede acceder a cursos.

✓ Los cursos poseen un identificador único.
```

Los hechos no dependen de decisiones técnicas.

---

# Paso 4 - Detectar reglas de negocio

Ahora aparecen las primeras reglas.

Por ejemplo:

```text
Un estudiante solamente podrá modificar
sus propios favoritos.
```

Otra:

```text
Un curso eliminado
no podrá permanecer
en la lista de favoritos.
```

Las reglas describen comportamiento.

No implementación.

---

# Paso 5 - Registrar preguntas abiertas

Una buena especificación también documenta
lo que todavía no sabemos.

Por ejemplo:

```text
¿Existe un límite máximo de favoritos?

¿Los instructores pueden utilizar favoritos?

¿Se sincronizan inmediatamente?

¿Funcionan sin conexión?

¿Puede un administrador consultar favoritos?
```

Una pregunta abierta no representa un problema.

Representa una conversación pendiente.

---

# Paso 6 - Separar supuestos

Muchas veces comenzamos a asumir información.

Ejemplo:

```
Los favoritos se guardarán en una tabla.
```

Eso no pertenece a la especificación.

Es una decisión de diseño.

Otro ejemplo:

```
Se utilizará Redis.
```

También pertenece al diseño.

Una buena especificación evita introducir soluciones prematuramente.

---

# Organizando el conocimiento

Una primera versión podría verse así.

```text
Favoritos

Objetivo

Permitir guardar cursos de interés.

------------------------

Actores

- Estudiante
- Sistema

------------------------

Hechos

- Existen cursos.
- Existen estudiantes.

------------------------

Reglas

- Cada estudiante administra únicamente sus favoritos.
- Los favoritos deben persistirse.

------------------------

Preguntas abiertas

- ¿Existe límite?
- ¿Hay sincronización offline?

------------------------

Pendiente

- Casos límite.
- Restricciones.
- Validación.
```

Todavía está incompleta.

Pero ahora sabemos exactamente qué falta.

---

# Caso de estudio — AI Academy

Veamos cómo evoluciona nuestro documento.

## Versión 0

```text
Agregar favoritos.
```

Muy ambigua.

---

## Versión 1

```text
Los estudiantes autenticados
podrán guardar cursos favoritos.

Cada estudiante administrará
únicamente sus propios favoritos.

Los favoritos permanecerán disponibles
después de cerrar sesión.

Los cursos eliminados
dejarán de aparecer como favoritos.
```

Todavía quedan preguntas.

Pero la calidad ya mejoró considerablemente.

---

# Especificar no significa decidir

Supongamos que aparece la siguiente conversación.

Arquitecto:

> Utilicemos MongoDB.

¿Forma parte de la especificación?

No.

Otro ejemplo.

Arquitecto:

> Usaremos Angular.

¿Forma parte?

Tampoco.

Las tecnologías cambian.

La especificación debería sobrevivir a esos cambios.

---

# 💡 Consejo AI Champion

Cuando dudes si una frase pertenece a la especificación, pregúntate:

> Si mañana cambiamos completamente la tecnología,
> ¿esta frase seguiría siendo verdadera?

Si la respuesta es sí, probablemente pertenece a la especificación.

---

# 🏆 Buenas prácticas

- Una sección responde un único tipo de pregunta.
- Mantén separadas las decisiones técnicas.
- Documenta las incertidumbres.
- Actualiza la especificación cuando cambie el negocio.
- Evita repetir información en distintas secciones.

---

# ⚠️ Errores comunes

## Mezclar reglas con implementación

Incorrecto:

```
Guardar favoritos usando Redis.
```

Correcto:

```
Los favoritos deberán persistirse.
```

---

## Ocultar preguntas abiertas

Las dudas deben permanecer visibles.

---

## Intentar completar toda la especificación en una sola reunión

Las especificaciones evolucionan.

---

## Pensar que la primera versión será definitiva

Una especificación madura mediante conversaciones y validaciones.

---

# 📌 Recuerda

Una especificación es un documento vivo.

Su objetivo no es estar terminada rápidamente.

Su objetivo es representar correctamente el problema.

---

# 🔗 Conexión con el próximo capítulo

Ya sabemos cómo organizar una especificación.

Ahora aprenderemos a escribir **casos de uso**, uno de los mecanismos más efectivos para describir el comportamiento esperado de un sistema.

---

# Conceptos clave

- Una especificación crece de manera incremental.
- Los hechos describen la realidad.
- Las reglas describen comportamiento.
- Las preguntas abiertas también forman parte de la especificación.
- El diseño aparece después de la especificación.

---

# Resumen

Una buena especificación no consiste en escribir mucho.

Consiste en organizar correctamente el conocimiento.

Cuando separamos objetivos, actores, hechos, reglas y preguntas abiertas, el proyecto se vuelve mucho más fácil de comprender y evolucionar.

Esta estructura será la base sobre la que construiremos el resto del caso de estudio AI Academy.

---

# 📝 Ejercicios

1. Separa los siguientes elementos en: hecho, regla de negocio, decisión técnica o pregunta abierta.
2. Reescribe un requerimiento real utilizando la estructura presentada en este capítulo.
3. Identifica tres decisiones técnicas que normalmente aparecen demasiado pronto en tus proyectos.
4. Analiza una historia de usuario de tu empresa y conviértela en una primera especificación estructurada.
5. Explica por qué una especificación debería poder sobrevivir a un cambio tecnológico.

---

# 🎯 Desafío

Toma una funcionalidad de un proyecto real.

Construye una especificación inicial con las siguientes secciones:

- Objetivo.
- Actores.
- Hechos.
- Reglas.
- Preguntas abiertas.

No escribas ni una sola decisión técnica.

Al finalizar, pide a otra persona que revise la especificación e identifique si comprende el comportamiento esperado sin conocer la tecnología utilizada.

---

# Evolución del caso de estudio

## Estado actual

✅ Objetivo definido.

✅ Actores identificados.

✅ Hechos documentados.

✅ Primeras reglas de negocio.

✅ Preguntas abiertas registradas.

## Artefacto construido

Primera versión estructurada de la especificación de **Favoritos** para AI Academy.

## Próximo capítulo

Transformaremos esta especificación en **casos de uso**, describiendo paso a paso cómo interactúan los distintos actores con el sistema y preparando el terreno para los criterios de aceptación y, más adelante, para Specification-Driven Development.
