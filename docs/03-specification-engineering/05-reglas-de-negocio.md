---
sidebar_position: 5
title: "Reglas de negocio como parte de la especificación"
description: "Aprende a identificar, documentar y validar reglas de negocio dentro de una especificación."
---

# Reglas de negocio como parte de la especificación

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Comprender qué es una regla de negocio.
- Diferenciar reglas de negocio de validaciones técnicas.
- Identificar reglas ocultas dentro de requerimientos simples.
- Documentar reglas de forma clara y verificable.
- Comprender la importancia de las reglas para SDD y sistemas inteligentes.

---

## ⏱ Tiempo estimado

60 minutos.

---

# Introducción

En los capítulos anteriores construimos:

- un objetivo,
- actores,
- hechos,
- casos de uso.

Pero todavía falta algo fundamental.

Los sistemas reales no solamente ejecutan acciones.

También deben respetar reglas.

Por ejemplo:

Un sistema educativo no solamente permite inscribirse en cursos.

También debe responder preguntas como:

- ¿Quién puede inscribirse?
- ¿Cuándo puede hacerlo?
- ¿Existe un límite?
- ¿Qué ocurre si el curso está completo?

Estas respuestas son reglas de negocio.

---

# ¿Qué es una regla de negocio?

Una regla de negocio es una condición, política o restricción que define cómo debe comportarse un sistema dentro de un determinado dominio.

Una regla expresa una decisión del negocio.

Ejemplo:

```
Un estudiante solo puede obtener un certificado
si completó todas las lecciones obligatorias.
```

Esta regla no pertenece al código.

Existe independientemente de la tecnología utilizada.

---

# Regla de negocio vs implementación

Consideremos este ejemplo.

## Incorrecto

```
Crear una validación en Angular
que bloquee usuarios sin permisos.
```

Esto es una decisión técnica.

---

## Correcto

```
Un usuario sin permisos administrativos
no puede modificar información de otros usuarios.
```

Esto es una regla de negocio.

---

# Características de una buena regla

Una regla debería ser:

## Clara

Debe poder entenderse sin conocimientos técnicos.

---

## Verificable

Debe poder comprobarse si se cumple o no.

---

## Independiente

No debe depender de una tecnología específica.

---

## Estable

Debe representar una decisión del dominio.

---

# Tipos de reglas de negocio

Existen diferentes tipos.

---

# 1. Reglas de autorización

Definen quién puede realizar una acción.

Ejemplo:

```
Un estudiante únicamente puede modificar
sus propios cursos favoritos.
```

---

# 2. Reglas de estado

Definen transiciones permitidas.

Ejemplo:

```
Un curso publicado no puede volver
al estado borrador sin aprobación.
```

---

# 3. Reglas temporales

Dependen del tiempo.

Ejemplo:

```
Una inscripción puede cancelarse
hasta 24 horas antes del inicio.
```

---

# 4. Reglas de cantidad

Definen límites.

Ejemplo:

```
Un estudiante puede tener
hasta 100 cursos favoritos.
```

---

# 5. Reglas de cálculo

Definen cómo obtener valores.

Ejemplo:

```
El progreso del estudiante corresponde
al porcentaje de lecciones completadas.
```

---

# Caso de estudio — AI Academy

Continuamos con nuestra funcionalidad:

> Los estudiantes pueden guardar cursos favoritos.

Ahora debemos descubrir las reglas.

---

## Regla inicial

```
Un estudiante puede agregar cursos favoritos.
```

Parece simple.

Pero aparecen preguntas.

---

# Descubriendo reglas ocultas

## Pregunta

¿Puede cualquier persona agregar favoritos?

Posible regla:

```
Solo usuarios autenticados pueden gestionar favoritos.
```

---

## Pregunta

¿Puede un estudiante modificar favoritos de otro?

Regla:

```
Cada estudiante solamente puede modificar
sus propios favoritos.
```

---

## Pregunta

¿Qué ocurre si un curso desaparece?

Regla:

```
Un curso inexistente no puede formar parte
de la lista de favoritos.
```

---

# Nuestra especificación evoluciona

Ahora tenemos:

```text
BR-001

Solo usuarios autenticados
pueden gestionar favoritos.


BR-002

Un estudiante solo puede modificar
sus propios favoritos.


BR-003

Un curso eliminado no puede permanecer
como favorito.
```

Estas reglas ahora forman parte del conocimiento del sistema.

---

# Reglas y pruebas

Una ventaja importante de documentar reglas es que permiten derivar pruebas.

Ejemplo:

Regla:

```
Solo usuarios autenticados pueden agregar favoritos.
```

Genera escenarios:

```text
✓ Usuario autenticado agrega favorito.

✓ Usuario no autenticado intenta agregar favorito.

✓ Sesión expirada intenta agregar favorito.
```

La regla se transforma en comportamiento verificable.

---

# Reglas y sistemas inteligentes

Este concepto será fundamental cuando trabajemos con agentes IA.

Un agente necesita conocer:

- qué puede hacer,
- qué no puede hacer,
- qué condiciones debe respetar.

Las reglas de negocio funcionan como límites de comportamiento.

---

# 💡 Consejo AI Champion

Cuando una decisión afecta al negocio, no debería estar escondida dentro del código.

Debe existir como conocimiento explícito.

Una regla perdida dentro de una implementación es una regla difícil de mantener.

---

# 🏆 Buenas prácticas

- Asignar identificadores únicos a las reglas.
- Escribirlas en lenguaje claro.
- Evitar términos técnicos.
- Mantenerlas independientes de la implementación.
- Relacionarlas con casos de uso y pruebas.

---

# ⚠️ Errores comunes

## Escribir reglas demasiado técnicas

Incorrecto:

```
Validar JWT antes del endpoint.
```

Correcto:

```
Solo usuarios autenticados pueden realizar la acción.
```

---

## Mezclar varias reglas

Incorrecto:

```
El usuario debe estar autenticado, tener rol admin,
usar Chrome y acceder desde Argentina.
```

Son varias reglas diferentes.

---

## No actualizar reglas

El negocio cambia.

La especificación debe evolucionar.

---

# Relación con SDD

En Specification-Driven Development las reglas de negocio tienen un rol central.

Permiten que:

- personas,
- herramientas,
- agentes,

entiendan los límites del sistema.

Una implementación generada sin conocer las reglas puede ser técnicamente correcta pero funcionalmente incorrecta.

---

# Conceptos clave

- Las reglas expresan decisiones del negocio.
- No son detalles técnicos.
- Deben ser claras y verificables.
- Son una fuente directa para pruebas.
- Serán fundamentales para sistemas asistidos por IA.

---

# Resumen

Las reglas de negocio convierten una funcionalidad simple en un comportamiento definido.

Sin reglas, una especificación queda incompleta.

Con reglas claras, el sistema tiene límites conocidos y puede evolucionar de manera segura.

---

# 📝 Ejercicios

1. Explica la diferencia entre regla de negocio y validación técnica.
2. Identifica cinco reglas ocultas en una aplicación bancaria.
3. Extrae reglas de negocio de una funcionalidad de e-commerce.
4. Convierte tres reglas en escenarios de prueba.
5. Analiza una funcionalidad real e identifica reglas que actualmente están escondidas en código.

---

# 🎯 Desafío

Selecciona una funcionalidad real de tu trabajo.

Crea una lista de reglas de negocio utilizando:

```
BR-001
BR-002
BR-003
```

Para cada regla define:

- descripción,
- motivo,
- casos donde aplica,
- casos donde no aplica.

Luego revisa si esas reglas podrían ser entendidas por una IA sin acceso al código.

---

# Evolución del caso de estudio

## Estado actual

✅ Especificación inicial.

✅ Caso de uso UC-001.

✅ Reglas de negocio iniciales.

## Nuevos artefactos

- BR-001 Usuario autenticado.
- BR-002 Propiedad de favoritos.
- BR-003 Cursos válidos.

## Próximo capítulo

Transformaremos el comportamiento esperado en **criterios de aceptación**, conectando especificaciones, QA y pruebas automatizadas.
