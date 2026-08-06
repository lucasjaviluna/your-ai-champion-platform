---
sidebar_position: 13
title: "Buenas prácticas y anti-patrones en SDD"
description: "Comprender qué prácticas ayudan o perjudican la adopción de Specification-Driven Development."
---

# Buenas prácticas y anti-patrones en SDD

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Identificar errores comunes al aplicar SDD.
- Diferenciar una Specification útil de documentación innecesaria.
- Conocer prácticas recomendadas.
- Evitar burocratizar el proceso.
- Diseñar una adopción progresiva.

---

# Introducción

Cuando aparece una nueva forma de trabajar, existe un riesgo:

Convertir una buena idea en un proceso pesado.

SDD no busca crear más documentos.

Busca crear mejor conocimiento.

---

La pregunta correcta no es:

> ¿Cuántos documentos tenemos?

La pregunta correcta es:

> ¿Tenemos suficiente conocimiento para tomar buenas decisiones?

---

# Anti-patrón 1: Specification como documentación burocrática

Uno de los errores más comunes:

Crear Specifications solamente porque "el proceso lo exige".

Ejemplo:

```
Crear documento de 50 páginas

↓

Guardar en repositorio

↓

Nunca actualizarlo
```

---

Resultado:

Se vuelve documentación muerta.

---

## Solución

Una Specification debe responder una necesidad real:

- reducir ambigüedad;
- definir contratos;
- guiar agentes;
- registrar decisiones.

---

# Anti-patrón 2: Especificar demasiado pronto

Otro error:

Intentar definir todo antes de comprender el problema.

Ejemplo:

```
Antes de investigar:

Crear arquitectura completa.

Definir todas las clases.

Diseñar todas las APIs.
```

---

Esto genera falsa precisión.

---

## Solución

Una Specification debe evolucionar.

Inicialmente puede contener:

```
Problema

Objetivo

Hipótesis
```

Luego incorporar detalles.

---

# Anti-patrón 3: Confundir Specification con diseño técnico

Una Specification no debería convertirse en:

```
Lista de clases

Métodos

Archivos

Variables
```

---

Eso pertenece a la implementación.

---

Ejemplo incorrecto:

```
Crear clase PaymentService
con método processPayment()
```

---

Ejemplo correcto:

```
El sistema debe permitir procesar pagos
y registrar su resultado.
```

---

# Anti-patrón 4: Ignorar restricciones

Muchos sistemas describen objetivos:

```
Mejorar rendimiento.
```

Pero olvidan límites.

---

Una buena Specification incluye:

```
No romper compatibilidad.

Mantener seguridad.

Respetar arquitectura existente.
```

---

Las restricciones son especialmente importantes para agentes IA.

---

# Anti-patrón 5: Specifications sin evidencia

Una Specification que no define validación queda incompleta.

Ejemplo:

```
Agregar autenticación segura.
```

---

Pregunta:

¿Cómo sabemos que es segura?

---

Debe existir evidencia:

```
Tests

Auditorías

Validaciones
```

---

# Anti-patrón 6: Copiar contexto infinito para agentes

Un error moderno:

Dar a un agente todo el repositorio esperando mejores resultados.

---

Más contexto no siempre significa mejor contexto.

---

Una Specification permite:

```
Contexto relevante

↓

En lugar de

↓

Información innecesaria
```

---

Esto mejora:

- precisión;
- costo;
- velocidad.

---

# Buenas prácticas

---

# 1. Mantener Specifications pequeñas y enfocadas

Una Specification debería tener un propósito claro.

Ejemplo:

Bueno:

```
SPEC-PAYMENTS-001

Procesamiento de pagos
```

---

Malo:

```
Sistema completo de la empresa
```

---

# 2. Escribir para humanos y máquinas

Una buena Specification debe ser:

- clara;
- estructurada;
- consistente.

---

Debe poder leerla:

```
Un desarrollador

Un arquitecto

Un agente IA
```

---

# 3. Versionar siempre

Toda Specification importante debería tener:

```
ID

Versión

Estado

Historial
```

---

# 4. Relacionar Specifications

Evitar documentos aislados.

Crear relaciones:

```
Product

↓

Functional

↓

Technical

↓

Evidence
```

---

# 5. Mantener trazabilidad

Poder responder:

```
¿Por qué existe este cambio?
```

---

Debe existir un camino:

```
Objetivo

↓

Specification

↓

Código

↓

Evidencia
```

---

# 6. Adoptar progresivamente

No intentar transformar toda una organización de un día para otro.

Una adopción posible:

```
Proyecto nuevo

↓

Feature nueva

↓

Equipo piloto

↓

Escalar progresivamente
```

---

# SDD no elimina la ingeniería tradicional

Es importante aclararlo.

SDD no reemplaza:

- arquitectura;
- testing;
- diseño;
- experiencia humana.

Los organiza alrededor del conocimiento.

---

# 📖 Evolución del pensamiento

La evolución de los procesos:

```
Más documentación

↓

Más procesos

↓

Más controles

↓

Mejor conocimiento

↓

Mejores decisiones
```

---

El objetivo no es agregar trabajo.

Es reducir incertidumbre.

---

# Caso de estudio: Your Harness

Un riesgo para cualquier plataforma como Your Harness sería intentar construir demasiada infraestructura antes de validar el problema.

Ejemplo de anti-patrón:

```
Crear un sistema completo de agentes

↓

Crear múltiples capas

↓

Definir todos los protocolos

↓

Sin usuarios reales
```

---

Una estrategia más saludable:

```
Resolver un flujo concreto

↓

Medir utilidad

↓

Extraer patrones

↓

Generalizar
```

---

Esta misma filosofía aplica al propio desarrollo de Your Harness.

El proyecto debe evolucionar mediante aprendizaje, no solamente mediante arquitectura.

---

# 🧠 AI Engineer Mindset

Un ingeniero tradicional piensa:

> Necesito más documentación.

Un AI Engineer piensa:

> Necesito conocimiento correcto, accesible y accionable.

---

# Resumen

En este capítulo aprendimos:

- SDD no debe convertirse en burocracia;
- una Specification debe resolver problemas reales;
- evitar especificar implementación demasiado pronto;
- la evidencia y trazabilidad son fundamentales;
- la adopción debe ser progresiva.

---

# Ejercicio

Analiza un proyecto existente.

Identifica:

1. Un documento que nadie actualiza.
2. Una decisión que vive solamente en la memoria del equipo.
3. Una regla de negocio escondida en código.

Luego piensa:

¿Cómo convertirías ese conocimiento en Specifications?

---

# Proyecto incremental

Con este capítulo cerramos la introducción conceptual de SDD.

El próximo capítulo será:

```
Módulo práctico:

Construyendo una Specification real
```

Aplicaremos todo lo aprendido creando un ejemplo completo desde cero.
