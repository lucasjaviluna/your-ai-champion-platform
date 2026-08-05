---
sidebar_position: 8
title: "Restricciones funcionales y no funcionales"
description: "Aprende a documentar las condiciones que limitan y complementan una especificación."
---

# Restricciones funcionales y no funcionales

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Diferenciar requisitos funcionales y no funcionales.
- Identificar restricciones que afectan una especificación.
- Evitar mezclar diseño técnico con necesidades del negocio.
- Documentar condiciones de calidad del sistema.
- Comprender su importancia en sistemas desarrollados con IA.

---

## ⏱ Tiempo estimado

60 minutos.

---

# Introducción

Hasta este momento nos concentramos en una pregunta:

> ¿Qué debe hacer el sistema?

Pero los sistemas profesionales tienen otra dimensión:

> ¿Cómo debe comportarse mientras lo hace?

Ejemplo:

Un usuario puede guardar favoritos.

Eso responde:

```
¿Qué?
```

Pero todavía faltan preguntas:

```
¿Cuánto tarda?

¿Quién puede acceder?

¿Cuántos elementos soporta?

¿Qué disponibilidad debe tener?

¿Qué restricciones existen?
```

---

# Requisitos funcionales

Un requisito funcional describe una capacidad del sistema.

Responde:

> ¿Qué debe hacer?

Ejemplos:

```
El estudiante puede agregar cursos favoritos.

El administrador puede publicar cursos.

El usuario puede descargar certificados.
```

---

# Requisitos no funcionales

Un requisito no funcional describe características de calidad o restricciones.

Responde:

> ¿Cómo debe comportarse?

Ejemplos:

```
La respuesta debe producirse en menos de 2 segundos.

El sistema debe estar disponible el 99.9% del tiempo.

La información debe estar protegida.
```

---

# Una analogía sencilla

Un requisito funcional es:

> Un automóvil debe poder desplazarse.

Un requisito no funcional es:

> Debe hacerlo consumiendo poca energía, siendo seguro y soportando ciertas condiciones.

Ambos son necesarios.

---

# Tipos de restricciones no funcionales

Existen muchas categorías.

---

# Rendimiento

Define tiempos de respuesta o capacidad.

Ejemplo:

```
La consulta de favoritos debe responder
en menos de 2 segundos.
```

---

# Seguridad

Define protección de información.

Ejemplo:

```
Un estudiante no puede consultar
favoritos de otro usuario.
```

---

# Disponibilidad

Define continuidad del servicio.

Ejemplo:

```
La plataforma debe estar disponible
durante el horario académico.
```

---

# Escalabilidad

Define crecimiento esperado.

Ejemplo:

```
La solución debe soportar
un aumento progresivo de estudiantes.
```

---

# Usabilidad

Define experiencia esperada.

Ejemplo:

```
El usuario debe recibir confirmación
después de completar una acción.
```

---

# Mantenibilidad

Define facilidad de evolución.

Ejemplo:

```
Las reglas de negocio deben estar
documentadas y ser modificables.
```

---

# Caso de estudio — AI Academy

Volvemos a nuestra funcionalidad:

> Favoritos.

Ya sabemos:

- qué hace,
- quién lo usa,
- qué reglas tiene.

Ahora agregamos restricciones.

---

# Restricciones funcionales

## RF-001

```
El estudiante puede agregar un curso favorito.
```

---

## RF-002

```
El estudiante puede eliminar un curso favorito.
```

---

## RF-003

```
El estudiante puede consultar su lista personal.
```

---

# Restricciones no funcionales

## RNF-001 - Rendimiento

```
La consulta de favoritos debe responder
en un tiempo aceptable para el usuario.
```

---

## RNF-002 - Seguridad

```
Un estudiante únicamente puede acceder
a sus propios favoritos.
```

---

## RNF-003 - Persistencia

```
Los favoritos deben mantenerse
entre sesiones.
```

---

# Importante: no convertir restricciones en soluciones

Veamos un error común.

Incorrecto:

```
Los favoritos se almacenarán en MongoDB.
```

¿Por qué?

Porque ya decidimos la solución.

---

Correcto:

```
Los favoritos deben persistir
entre sesiones del usuario.
```

Ahora arquitectura puede decidir cómo.

---

# Restricciones y decisiones técnicas

Una especificación debería estar separada de:

- framework,
- lenguaje,
- base de datos,
- infraestructura.

Ejemplo:

## Especificación

```
El sistema debe autenticar usuarios.
```

## Diseño

```
Se utilizará JWT.
```

---

# Restricciones y agentes IA

Este punto será fundamental más adelante.

Un agente IA necesita conocer:

No solamente:

```
Implementar favoritos.
```

Sino:

```
Implementar favoritos considerando:

- seguridad,
- límites,
- rendimiento,
- reglas de negocio.
```

La calidad de la implementación depende del contexto entregado.

---

# 💡 Consejo AI Champion

Muchas malas decisiones técnicas aparecen porque una restricción importante nunca fue escrita.

Si algo importa para el sistema, debe existir como conocimiento explícito.

---

# 🏆 Buenas prácticas

- Separar funcional y no funcional.
- Priorizar restricciones realmente importantes.
- Evitar especificar tecnologías.
- Asociar restricciones con impacto.
- Revisarlas durante la evolución del proyecto.

---

# ⚠️ Errores comunes

## Confundir restricción con solución

Incorrecto:

```
Usar Redis.
```

Correcto:

```
La consulta debe tener baja latencia.
```

---

## Escribir requisitos imposibles de medir

Incorrecto:

```
Debe ser muy rápido.
```

Mejor:

```
Debe responder en menos de X segundos.
```

---

## Ignorar requisitos no funcionales

Muchos problemas graves aparecen por esta omisión.

---

# Relación con SDD

En Specification-Driven Development las restricciones ayudan a los agentes y herramientas a tomar mejores decisiones.

Una especificación completa necesita:

```
Comportamiento esperado

+

Reglas

+

Restricciones

=

Contexto suficiente
```

---

# Conceptos clave

- Funcional responde qué hace.
- No funcional responde cómo debe hacerlo.
- Las restricciones limitan el espacio de soluciones.
- No deben confundirse con decisiones técnicas.
- Son fundamentales para IA.

---

# Resumen

Una especificación profesional no solamente describe funcionalidades.

También define las condiciones que hacen que esa funcionalidad sea aceptable.

Las restricciones permiten que diferentes equipos y sistemas inteligentes entiendan los límites dentro de los cuales deben trabajar.

---

# 📝 Ejercicios

1. Clasifica diez requisitos como funcionales o no funcionales.
2. Encuentra restricciones ocultas en una aplicación bancaria.
3. Reescribe decisiones técnicas como restricciones.
4. Define requisitos no funcionales para una tienda online.
5. Explica por qué una IA necesita conocer restricciones.

---

# 🎯 Desafío

Selecciona una funcionalidad real.

Define:

- 5 requisitos funcionales.
- 5 requisitos no funcionales.
- 3 restricciones que no mencionen tecnologías.

Después analiza si otra persona podría diseñar una solución sin hacer preguntas adicionales.

---

# Evolución del caso de estudio

## Estado actual

✅ Especificación inicial.

✅ Caso de uso UC-001.

✅ Reglas de negocio.

✅ Criterios de aceptación.

✅ Escenarios alternativos.

✅ Casos límite.

✅ Restricciones funcionales y no funcionales.

## Próximo capítulo

Aprenderemos a **revisar y validar una especificación**, utilizando técnicas para detectar ambigüedades, inconsistencias y falta de información antes de comenzar el desarrollo.
