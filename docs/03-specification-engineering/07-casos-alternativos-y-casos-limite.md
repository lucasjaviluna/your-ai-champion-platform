---
sidebar_position: 7
title: "Casos alternativos y casos límite"
description: "Aprende a identificar escenarios alternativos y situaciones excepcionales dentro de una especificación."
---

# Casos alternativos y casos límite

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Diferenciar flujo principal, escenario alternativo y caso límite.
- Identificar situaciones que suelen quedar fuera de una especificación.
- Mejorar la calidad de los requerimientos anticipando excepciones.
- Crear escenarios más completos para humanos y sistemas IA.
- Preparar especificaciones más robustas para SDD.

---

## ⏱ Tiempo estimado

60 minutos.

---

# Introducción

En capítulos anteriores construimos el camino principal de una funcionalidad.

Por ejemplo:

```
Usuario autenticado

↓

Selecciona favorito

↓

Sistema registra favorito

↓

Curso aparece guardado
```

Este flujo representa la situación esperada.

Pero los sistemas reales rara vez funcionan únicamente en condiciones ideales.

¿Qué ocurre si:

- el usuario pierde conexión?
- el curso fue eliminado?
- dos dispositivos modifican información al mismo tiempo?
- el usuario intenta una acción repetida?

Estas situaciones forman parte del comportamiento del sistema.

---

# Flujo principal

El flujo principal describe:

> La interacción esperada cuando todo funciona correctamente.

Ejemplo:

```text
1. Usuario abre un curso.

2. Selecciona agregar favorito.

3. Sistema registra la acción.

4. Sistema muestra confirmación.
```

Este es el escenario más importante.

Pero no es suficiente.

---

# Escenarios alternativos

Un escenario alternativo representa un camino diferente que sigue siendo válido.

No necesariamente es un error.

---

## Ejemplo

Usuario intenta agregar un curso que ya es favorito.

No es una falla.

Es una situación posible.

Podemos definir:

```text
1. Usuario selecciona agregar favorito.

2. Sistema detecta que ya existe.

3. Sistema mantiene el estado actual.

4. Informa al usuario.
```

---

# Casos límite

Los casos límite aparecen cuando nos acercamos a los extremos del comportamiento.

Son situaciones menos frecuentes, pero importantes.

Ejemplos:

- cero elementos,
- máximo permitido,
- información incompleta,
- estados inesperados.

---

# Ejemplo

Supongamos:

```
Un estudiante puede tener hasta 100 favoritos.
```

Aparece un caso límite:

```text
¿Qué ocurre cuando intenta agregar el favorito número 101?
```

La especificación debe responder.

---

# Caso de estudio — AI Academy

Continuamos con favoritos.

Nuestro flujo principal:

```text
UC-001

Agregar curso favorito.
```

Ahora agregaremos escenarios adicionales.

---

# Escenario alternativo 1

## Curso ya favorito

```text
Dado:

Un estudiante autenticado.

Y un curso que ya está marcado como favorito.

Cuando:

El estudiante intenta agregarlo nuevamente.

Entonces:

El sistema mantiene un único registro.

Y evita duplicados.
```

---

# Escenario alternativo 2

## Usuario cancela acción

```text
Dado:

Un estudiante visualizando un curso.

Cuando:

Decide cancelar antes de confirmar.

Entonces:

No se modifica la lista de favoritos.
```

---

# Caso límite 1

## Límite máximo alcanzado

```text
Dado:

Un estudiante con el máximo permitido de favoritos.

Cuando:

Intenta agregar otro curso.

Entonces:

El sistema rechaza la operación.

Y muestra una explicación.
```

---

# Caso límite 2

## Curso eliminado

```text
Dado:

Un curso previamente marcado como favorito.

Cuando:

El administrador elimina el curso.

Entonces:

El curso deja de estar disponible.
```

---

# ¿Por qué esto importa con IA?

Una IA normalmente genera soluciones basándose en patrones.

Si solamente recibe:

```
Agregar favorito.
```

buscará una implementación típica.

Pero no sabrá:

- qué ocurre con duplicados,
- qué ocurre con errores,
- qué ocurre con límites.

Cuanto mejor especificamos escenarios, más precisa será la solución generada.

---

# Pensamiento de ingeniería

Un desarrollador junior suele pensar:

```
¿Qué pasa cuando funciona?
```

Un ingeniero piensa:

```
¿Qué pasa cuando no funciona?
```

La segunda pregunta evita muchos problemas.

---

# Técnica: análisis de excepciones

Una técnica útil es preguntar:

## ¿Qué puede faltar?

Ejemplo:

- usuario,
- curso,
- conexión,
- permisos.

---

## ¿Qué puede repetirse?

Ejemplo:

- doble clic,
- solicitudes duplicadas.

---

## ¿Qué puede cambiar?

Ejemplo:

- estado del curso,
- permisos del usuario.

---

## ¿Qué puede ocurrir al límite?

Ejemplo:

- máximo permitido,
- mínimo permitido.

---

# Relación con pruebas

Cada escenario puede convertirse en una prueba.

Ejemplo:

Caso límite:

```
Usuario alcanza máximo de favoritos.
```

Prueba:

```
Given:
Usuario con 100 favoritos.

When:
Agrega uno más.

Then:
Sistema rechaza la operación.
```

---

# Relación con agentes IA

Cuando lleguemos a agentes, estos escenarios funcionarán como restricciones.

Un agente que implementa una funcionalidad podrá revisar:

- camino feliz,
- caminos alternativos,
- excepciones.

La especificación se convierte en una guía de comportamiento.

---

# 💡 Consejo AI Champion

Una especificación incompleta normalmente no falla por falta de información del flujo principal.

Falla porque nadie preguntó:

> "¿Qué pasa si algo sale diferente?"

---

# 🏆 Buenas prácticas

- Documentar escenarios negativos.
- Pensar desde la perspectiva del usuario.
- Incluir situaciones poco frecuentes.
- Relacionar escenarios con criterios de aceptación.
- No esperar a que QA descubra todos los casos.

---

# ⚠️ Errores comunes

## Solo documentar el camino feliz

Es el error más frecuente.

---

## Crear excepciones imposibles de entender

Ejemplo:

```
Error 502.
```

Mejor:

```
El sistema no puede completar la operación temporalmente.
```

---

## Agregar casos técnicos antes que funcionales

Primero comprender el comportamiento.

Después decidir implementación.

---

# Conceptos clave

- Flujo principal: camino esperado.
- Escenario alternativo: comportamiento válido diferente.
- Caso límite: situación extrema o poco frecuente.
- Las excepciones forman parte de la especificación.
- Más escenarios significan menos interpretación.

---

# Resumen

Una especificación madura no describe solamente lo que ocurre cuando todo funciona.

También describe qué debe hacer el sistema cuando:

- falta información,
- existe conflicto,
- aparece un límite,
- ocurre una situación inesperada.

Esta capacidad será especialmente importante cuando utilicemos IA para generar código, porque la IA necesita conocer no solamente el objetivo, sino también los límites del comportamiento esperado.

---

# 📝 Ejercicios

1. Identifica cinco casos límite de una aplicación bancaria.
2. Escribe escenarios alternativos para un login.
3. Analiza una funcionalidad real y encuentra caminos no documentados.
4. Convierte escenarios alternativos en criterios de aceptación.
5. Explica por qué los casos límite son importantes para agentes IA.

---

# 🎯 Desafío

Elige una funcionalidad real.

Construye:

- flujo principal,
- tres escenarios alternativos,
- tres casos límite.

Luego solicita a una IA:

"Analiza esta especificación y encuentra escenarios que todavía no contemplé."

Compara los resultados.

---

# Evolución del caso de estudio

## Estado actual

✅ Especificación inicial.

✅ Caso de uso UC-001.

✅ Reglas de negocio.

✅ Criterios de aceptación.

✅ Escenarios alternativos.

✅ Casos límite.

## Nuevos escenarios

- Curso duplicado.
- Usuario no autenticado.
- Límite máximo alcanzado.
- Curso eliminado.

## Próximo capítulo

Aprenderemos a documentar **restricciones funcionales y no funcionales**, completando la visión de una especificación profesional.
