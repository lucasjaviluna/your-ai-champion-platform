---
sidebar_position: 9
title: "Specifications y evidencia"
description: "Comprender cómo validar que una Specification fue implementada correctamente mediante evidencia verificable."
---

# Specifications y evidencia

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Comprender la relación entre Specification y evidencia.
- Diferenciar implementación de validación.
- Diseñar criterios de evidencia verificables.
- Entender por qué la evidencia es fundamental para agentes IA.
- Construir cadenas completas de confianza.

---

# Introducción

En ingeniería de software existe una diferencia importante entre:

```
Creer que algo funciona
```

y:

```
Demostrar que funciona
```

---

Una Specification madura no solamente define:

```
¿Qué debe construirse?
```

También define:

```
¿Cómo comprobaremos que fue construido correctamente?
```

---

# Del conocimiento a la evidencia

El flujo completo de SDD puede verse así:

```
Intención

↓

Specification

↓

Implementación

↓

Evidencia

↓

Confianza
```

---

La evidencia es el puente entre lo esperado y lo realizado.

---

# ¿Qué es evidencia?

Una evidencia es cualquier artefacto verificable que demuestra que una condición se cumple.

Puede ser:

- un test automatizado;
- un resultado de pipeline;
- una validación manual;
- una métrica;
- un reporte de seguridad;
- una captura;
- un registro de auditoría.

---

Ejemplo:

Specification:

```
Un usuario bloquea su cuenta después de 5 intentos fallidos.
```

Evidencia:

```
Test automático:

✓ 4 intentos -> usuario activo

✓ 5 intentos -> usuario bloqueado
```

---

# Specification sin evidencia

Ejemplo:

```
Implementar sistema de descuentos.
```

Problema:

¿Cómo sabemos que está terminado?

---

Podemos tener:

- código compilando;
- una pantalla funcionando;
- un endpoint creado.

Pero todavía no sabemos si cumple la intención original.

---

# Specification con evidencia

Ejemplo:

```
Objetivo:

Aplicar descuentos premium.

Criterios:

✓ Usuario premium obtiene descuento.

✓ Usuario estándar no obtiene descuento.

✓ Descuento máximo respetado.

Evidencia:

✓ Tests automáticos.

✓ Validación funcional.

✓ Registro de ejecución.
```

---

Ahora existe una relación verificable.

---

# Tipos de evidencia

## 1. Evidencia funcional

Demuestra comportamiento.

Ejemplos:

- tests;
- pruebas de aceptación;
- escenarios BDD.

---

Ejemplo:

```
Given:
Usuario premium

When:
Realiza compra

Then:
Recibe descuento
```

---

# 2. Evidencia técnica

Demuestra propiedades internas.

Ejemplos:

- cobertura;
- análisis estático;
- validaciones de API;
- benchmarks.

---

Ejemplo:

```
API responde en menos de 300ms.
```

---

# 3. Evidencia operacional

Demuestra funcionamiento en producción.

Ejemplos:

- métricas;
- logs;
- monitoreo;
- alertas.

---

Ejemplo:

```
Error rate < 1%
durante despliegue.
```

---

# 4. Evidencia de seguridad

Demuestra cumplimiento de controles.

Ejemplos:

- análisis de vulnerabilidades;
- auditorías;
- pruebas de permisos.

---

# La matriz Specification-Evidence

Una práctica útil es relacionar requisitos con evidencia.

Ejemplo:

| Requirement | Evidence |
|-|-|
| Usuario puede pagar | Test integración |
| Pago rechazado correctamente | Test API |
| Auditoría registrada | Log validation |
| Datos protegidos | Security scan |

---

Esto evita requisitos sin validación.

---

# Evidencia y agentes IA

Este concepto es crítico.

Un agente IA puede generar:

- código;
- tests;
- documentación.

Pero la pregunta sigue siendo:

```
¿Cómo sabemos que el resultado es correcto?
```

---

La respuesta es:

```
Specification

↓

Evidencia verificable
```

---

Un agente confiable no debería decir:

> "Creo que funciona."

Debería poder decir:

> "La Specification requería X. Se ejecutaron estas validaciones. La evidencia obtenida fue Y."

---

# Human-in-the-middle

La evidencia también permite una colaboración más segura entre humanos y agentes.

Un posible flujo:

```
Agente propone cambio

↓

Genera implementación

↓

Ejecuta validaciones

↓

Presenta evidencia

↓

Humano revisa

↓

Aprobación
```

---

El humano no revisa solamente código.

Revisa:

- intención;
- cambio;
- evidencia.

---

# Evidencia como memoria del sistema

Con el tiempo, la evidencia se convierte en conocimiento histórico.

Ejemplo:

```
Specification:

Migrar sistema de pagos

↓

Implementación

↓

Tests

↓

Resultado producción

↓

Métricas posteriores
```

---

El sistema aprende de su propia evolución.

---

# 📖 Evolución del pensamiento

La evolución de la validación:

```
Funciona en mi máquina

↓

Pruebas manuales

↓

Tests automatizados

↓

Pipelines CI/CD

↓

Evidencia vinculada a Specifications

↓

Sistemas verificables por agentes
```

---

El objetivo final no es solamente automatizar.

Es aumentar la confianza.

---

# Caso de estudio: Your Harness

Una posible capacidad futura para una plataforma como Your Harness sería registrar:

```
Specification

↓

Agent execution

↓

Generated changes

↓

Validation results

↓

Human approval
```

---

Esto permitiría responder:

```
¿Por qué se aceptó este cambio?

¿Qué Specification lo originó?

¿Qué evidencia existía?
```

---

Nuevamente, esto representa una posible evolución del diseño de Your Harness, no una funcionalidad actualmente implementada.

---

# 🧠 AI Engineer Mindset

Un desarrollador pregunta:

> ¿El código funciona?

Un AI Engineer pregunta:

> ¿Qué evidencia demuestra que cumple la intención definida?

---

# Resumen

En este capítulo aprendimos:

- una Specification necesita evidencia asociada;
- implementar no significa demostrar;
- existen diferentes tipos de evidencia;
- los agentes necesitan mecanismos de verificación;
- la evidencia crea confianza en sistemas asistidos por IA.

---

# Ejercicio

Elige una funcionalidad simple y crea:

```
Specification

↓

Criterios de aceptación

↓

Evidencia esperada
```

Ejemplo:

```
Login

↓

Usuario puede autenticarse

↓

Test + auditoría + validación manual
```

---

# Proyecto incremental

En el próximo capítulo veremos:

```
Specifications

+

Versionado

+

Evolución histórica
```

Analizaremos cómo mantener conocimiento válido cuando un sistema cambia durante años.
