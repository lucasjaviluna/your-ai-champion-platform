---
sidebar_position: 4
title: "Descomposición de problemas: la habilidad fundamental para trabajar con IA"
description: "Aprende a dividir problemas complejos en unidades pequeñas, especificables y ejecutables para maximizar el valor de la inteligencia artificial."
---

# Descomposición de problemas: la habilidad fundamental para trabajar con IA

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Comprender por qué la descomposición es una habilidad crítica en la era de la IA.
- Aprender a transformar problemas ambiguos en unidades manejables.
- Diferenciar problemas, funcionalidades, tareas y especificaciones.
- Aplicar técnicas de división de problemas en desarrollo de software.
- Preparar problemas correctamente para trabajar con IA.

---

## ⏱ Tiempo estimado

45 minutos.

---

# Introducción

Una de las mayores diferencias entre un desarrollador junior y uno senior no está solamente en cuánto código puede escribir.

Está en cómo analiza un problema.

Un desarrollador con experiencia rara vez recibe una tarea y comienza inmediatamente a programar.

Primero intenta responder:

- ¿Qué problema estamos resolviendo?
- ¿Qué partes lo componen?
- ¿Qué decisiones debemos tomar?
- ¿Qué riesgos existen?
- ¿Cómo podemos dividirlo?

Esta habilidad siempre fue importante.

Con la llegada de la IA se vuelve fundamental.

---

# El problema de pedir demasiado

Imaginemos esta solicitud:

```
Construye una plataforma de comercio electrónico.
```

Para una persona ya es una tarea enorme.

Para una IA también.

El problema no es la capacidad del modelo.

El problema es la falta de estructura.

---

Una plataforma de comercio electrónico contiene:

```
E-commerce

├── Usuarios

├── Catálogo

├── Productos

├── Carrito

├── Checkout

├── Pagos

├── Envíos

├── Notificaciones

└── Administración
```

Ahora cada parte puede analizarse individualmente.

---

# La regla fundamental

> Un problema complejo debe convertirse en una colección de problemas más pequeños que puedan entenderse, especificarse y validarse.

Este principio aparece en muchas disciplinas:

- Ingeniería de software.
- Arquitectura.
- Gestión de proyectos.
- Diseño de sistemas.
- Inteligencia artificial.

---

# Problema vs solución

Un error común es saltar directamente a la solución.

Ejemplo:

```
Necesitamos una pantalla nueva.
```

Pero la pregunta correcta es:

```
¿Qué problema del usuario estamos resolviendo?
```

La pantalla es una posible solución.

No es el problema.

---

# La pirámide de descomposición

Una forma práctica de pensar:

```
Problema de negocio

↓

Capacidad del sistema

↓

Funcionalidad

↓

Historia de usuario

↓

Caso de uso

↓

Tarea técnica

↓

Implementación
```

---

## Ejemplo

Problema:

```
Los clientes abandonan compras.
```

↓

Capacidad:

```
Proceso de checkout optimizado.
```

↓

Funcionalidad:

```
Permitir pago rápido.
```

↓

Historia:

```
Como cliente quiero guardar mi método de pago para comprar más rápido.
```

↓

Tarea técnica:

```
Crear endpoint para métodos guardados.
```

↓

Implementación:

```
Crear servicio PaymentMethodService.
```

---

# La IA y la descomposición

Un error frecuente es utilizar IA así:

```
Crea todo el sistema.
```

Un mejor enfoque:

```
Analiza este problema.

Ayúdame a identificar capacidades principales.

No propongas código todavía.
```

Luego:

```
Ahora descompón la capacidad de pagos.
```

Luego:

```
Convierte esta parte en especificaciones técnicas.
```

La conversación evoluciona.

---

# Descomposición horizontal y vertical

Existen dos formas comunes de dividir.

---

## Descomposición horizontal

Dividir por funcionalidades.

Ejemplo:

```
Sistema bancario

├── Clientes

├── Cuentas

├── Transferencias

├── Tarjetas

└── Reportes
```

---

## Descomposición vertical

Dividir una funcionalidad completa de extremo a extremo.

Ejemplo:

```
Transferencia bancaria

Frontend

↓

API

↓

Servicio

↓

Base de datos

↓

Notificación
```

---

En equipos modernos normalmente combinamos ambas.

---

# El tamaño correcto de una tarea

Una tarea demasiado grande:

```
Crear módulo de pagos.
```

Es difícil de estimar y validar.

Una demasiado pequeña:

```
Crear variable amount.
```

No aporta valor independiente.

Buscamos unidades que sean:

- Comprensibles.
- Estimables.
- Validables.
- Implementables.

---

# Relación con Specification Engineering

Aquí aparece una conexión importante.

Una especificación necesita tener un límite claro.

No podemos especificar correctamente algo que todavía no entendemos.

Por eso:

```
Problema complejo

↓

Descomposición

↓

Unidad de trabajo

↓

Especificación

↓

Ejecución
```

La descomposición es el paso previo a la especificación.

---

# Relación con agentes IA

Los agentes también necesitan límites.

Un agente no debería recibir:

```
Construye todo el sistema.
```

Un mejor diseño:

```
Agente autenticación

Agente pagos

Agente testing

Agente documentación
```

Cada agente tiene:

- objetivo,
- contexto,
- herramientas,
- responsabilidades.

---

# Ejemplo aplicado a desarrollo frontend

Solicitud inicial:

```
Crear módulo de usuarios.
```

Descomposición:

```
Usuarios

├── Listado

├── Búsqueda

├── Detalle

├── Creación

├── Edición

├── Eliminación

└── Permisos
```

Luego:

```
Listado usuarios

├── Diseño componente

├── Modelo Usuario

├── Servicio API

├── Estado NgRx

├── Tests

└── Documentación
```

Ahora sí tenemos unidades donde la IA puede aportar valor.

---

# Errores comunes

## Pedir implementación demasiado pronto

```
Genera código.
```

Antes de entender el problema.

---

## No definir límites

```
Haz una aplicación completa.
```

---

## Mezclar múltiples objetivos

```
Diseña arquitectura, genera código, crea tests y documenta.
```

Mejor dividir.

---

# 💻 Flujo recomendado AI Champion

A partir de ahora utilizaremos este flujo:

```
Problema

↓

Descomposición

↓

Especificación

↓

Conversación IA

↓

Implementación

↓

Validación

↓

Iteración
```

---

# 🧠 Para desarrolladores Senior

La descomposición es una de las habilidades que más diferencia el desarrollo tradicional del desarrollo aumentado por IA.

Cuando una IA genera código incorrecto, muchas veces el problema no está en el código generado.

Está en que recibió una unidad de trabajo mal definida.

Un desarrollador senior actúa como arquitecto del problema:

- define límites,
- establece contratos,
- identifica dependencias,
- reduce ambigüedad.

---

# Conceptos clave

- Los problemas grandes deben dividirse.
- La IA funciona mejor con unidades claras.
- La especificación necesita una buena descomposición previa.
- Los agentes requieren responsabilidades acotadas.
- La calidad del resultado depende de la calidad del problema definido.

---

# Resumen

La descomposición de problemas es una habilidad fundamental para trabajar con IA.

La IA puede acelerar la implementación, pero necesita recibir problemas correctamente estructurados.

El desarrollador del futuro no será quien escriba más código.

Será quien mejor pueda transformar problemas complejos en especificaciones claras que sistemas inteligentes puedan ejecutar.

---

# 📝 Ejercicios

1. ¿Por qué una tarea grande produce peores resultados con IA?
2. Diferencia entre problema, funcionalidad y tarea técnica.
3. Descompón una aplicación de reservas de hoteles.
4. Toma una funcionalidad y divídela verticalmente.
5. Diseña cómo dividirías responsabilidades entre agentes IA.

---

# 🎯 Desafío

Selecciona una aplicación real.

Puede ser:

- banca,
- e-commerce,
- red social,
- sistema empresarial.

Realiza:

1. Descomposición por capacidades.
2. Selección de una capacidad.
3. Nueva descomposición en funcionalidades.
4. Creación de una primera especificación.

Esta especificación será reutilizada en capítulos futuros.

---

# Próximo capítulo

## IA dentro del ciclo de desarrollo

En el próximo capítulo veremos dónde exactamente aporta valor la IA dentro del proceso completo de ingeniería:

```
Idea

↓

Análisis

↓

Diseño

↓

Código

↓

Testing

↓

Documentación

↓

Mantenimiento
```
