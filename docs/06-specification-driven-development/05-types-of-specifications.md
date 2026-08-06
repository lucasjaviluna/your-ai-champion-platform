---
sidebar_position: 5
title: "Tipos de Specifications"
description: "Comprender los diferentes tipos de especificaciones y cómo organizan el conocimiento de un sistema."
---

# Tipos de Specifications

## 🎯 Objetivos de aprendizaje

Al finalizar este capítulo podrás:

- Identificar diferentes tipos de Specifications.
- Comprender qué problema resuelve cada una.
- Evitar mezclar niveles de conocimiento.
- Diseñar una arquitectura documental escalable.
- Preparar Specifications para ser utilizadas por humanos y agentes IA.

---

# Introducción

En capítulos anteriores definimos Specification como:

> Un contrato de conocimiento que guía la construcción y evolución de un sistema.

Pero un sistema moderno contiene muchos tipos de conocimiento.

Por ejemplo:

```
¿Por qué existe una funcionalidad?

¿Cómo debe comportarse?

¿Cómo debe implementarse?

¿Cómo debe operar?

¿Cómo debe protegerse?
```

Intentar responder todas estas preguntas en un único documento genera confusión.

---

# La necesidad de separar conocimiento

Un error común es crear documentos enormes:

```
Sistema completo.doc
```

con:

- requerimientos,
- arquitectura,
- decisiones técnicas,
- configuración,
- operación.

El resultado suele ser:

- difícil de mantener;
- difícil de buscar;
- difícil de automatizar.

---

La alternativa es separar Specifications por intención.

---

# Clasificación general

Una posible clasificación es:

```
Specifications

├── Product Specification

├── Functional Specification

├── Technical Specification

├── Architecture Specification

├── Operational Specification

├── Security Specification

└── Quality Specification
```

---

# 1. Product Specification

Responde:

> ¿Por qué construimos esto?

Está orientada al valor de negocio.

Incluye:

- problema;
- usuarios;
- objetivos;
- métricas;
- alcance.

---

Ejemplo:

```
Product Specification:

Objetivo:

Aumentar la conversión permitiendo
pagos simplificados.
```

---

No define:

- clases;
- APIs;
- tablas.

Define valor.

---

# 2. Functional Specification

Responde:

> ¿Qué debe hacer el sistema?

Describe comportamiento.

Incluye:

- casos de uso;
- reglas;
- escenarios;
- criterios de aceptación.

---

Ejemplo:

```
Cuando un usuario realiza una compra:

1. Validar identidad.

2. Procesar pago.

3. Confirmar resultado.

4. Registrar operación.
```

---

Esta Specification suele estar muy relacionada con QA.

---

# 3. Technical Specification

Responde:

> ¿Cómo implementaremos una solución?

Aquí aparecen detalles técnicos.

Incluye:

- APIs;
- modelos de datos;
- contratos;
- librerías;
- integraciones.

---

Ejemplo:

```
Technical Specification:

Endpoint:

POST /payments

Request:

{
 amount,
 currency
}

Response:

{
 transactionId,
 status
}
```

---

Importante:

La Technical Specification depende de la Functional Specification.

No debería reemplazarla.

---

# 4. Architecture Specification

Responde:

> ¿Cómo encajan los componentes?

Describe decisiones estructurales.

Incluye:

- componentes;
- relaciones;
- límites;
- patrones;
- decisiones arquitectónicas.

---

Ejemplo:

```
Payment Service

↓

Payment Provider Adapter

↓

External Gateway
```

---

Aquí aparecen conceptos como:

- ADR;
- bounded contexts;
- dependencias.

---

# 5. Operational Specification

Responde:

> ¿Cómo funciona el sistema en producción?

Incluye:

- despliegue;
- monitoreo;
- escalabilidad;
- recuperación;
- alertas.

---

Ejemplo:

```
Operational Specification:

Disponibilidad requerida:

99.9%

Backup:

Cada 24 horas.

Alertas:

Error rate > 5%.
```

---

# 6. Security Specification

Responde:

> ¿Qué condiciones de seguridad debe cumplir?

Incluye:

- autenticación;
- autorización;
- cifrado;
- auditoría;
- cumplimiento.

---

Ejemplo:

```
Security Specification:

Los usuarios deben autenticarse
mediante OAuth2.

Todas las acciones críticas
deben generar auditoría.
```

---

# 7. Quality Specification

Responde:

> ¿Qué características no funcionales debe cumplir?

Incluye:

- rendimiento;
- accesibilidad;
- mantenibilidad;
- compatibilidad.

---

Ejemplo:

```
Quality Specification:

Tiempo máximo respuesta:

300ms.

Cobertura mínima:

80%.
```

---

# Relación entre Specifications

Estas Specifications no viven aisladas.

Existe una relación:

```
Product

↓

Functional

↓

Technical

↓

Architecture

↓

Implementation
```

Con aspectos transversales:

```
Security

Quality

Operations
```

---

# Una visión completa

```text
                    Product

                       |

                  Functional

                       |

        ------------------------------

        |             |              |

   Technical   Architecture    Security

        |

   Implementation

        |

    Evidence
```

---

# Specifications y trazabilidad

Una ventaja importante de separar tipos es poder responder:

```
¿Por qué existe este código?
```

La respuesta puede recorrer:

```
Código

↓

Technical Specification

↓

Functional Specification

↓

Product Specification
```

---

# Relación con agentes IA

Los diferentes agentes pueden consumir diferentes Specifications.

Ejemplo:

```
Product Agent

consume:

Product Specification
```

---

```
Developer Agent

consume:

Functional + Technical Specification
```

---

```
Security Agent

consume:

Security Specification
```

---

La separación permite crear agentes especializados.

---

# 📖 Evolución del pensamiento

La evolución del conocimiento estructurado:

```
Un documento gigante

↓

Documentos separados

↓

Documentación organizada

↓

Specifications relacionadas

↓

Knowledge Graph de Specifications
```

---

El siguiente paso natural no es tener más documentos.

Es tener relaciones entre ellos.

---

# Caso de estudio: Your Harness

Una posible arquitectura para Your Harness podría considerar un Specification Registry.

Ejemplo conceptual:

```
specs/

├── product/

├── functional/

├── technical/

├── architecture/

├── security/

└── operational/
```

Este diseño permitiría que diferentes agentes consulten solamente el conocimiento relevante.

Por ejemplo:

Un Security Agent no necesita conocer todos los detalles funcionales de una pantalla.

Necesita acceder a las restricciones de seguridad relacionadas.

---

# 🧠 AI Engineer Mindset

Un ingeniero tradicional organiza archivos.

Un AI Engineer organiza conocimiento.

La pregunta deja de ser:

> ¿Dónde guardo este documento?

Y pasa a ser:

> ¿Qué tipo de conocimiento representa este artefacto y quién necesita consumirlo?

---

# Resumen

En este capítulo aprendimos que:

- existen diferentes tipos de Specifications;
- cada una representa un nivel distinto de conocimiento;
- separar responsabilidades mejora mantenimiento;
- los agentes IA pueden consumir Specifications específicas;
- una arquitectura de Specifications puede convertirse en una base de conocimiento.

---

# Ejercicio

Para una aplicación web empresarial define:

1. Una Product Specification.
2. Una Functional Specification.
3. Una Technical Specification.
4. Una Architecture Specification.

Luego identifica qué agente IA podría consumir cada una.

---

# Proyecto incremental

En el próximo capítulo estudiaremos el ciclo de vida de una Specification:

```
Creación

↓

Revisión

↓

Aprobación

↓

Implementación

↓

Evolución

↓

Deprecación
```

Porque una Specification no es un documento estático.

Es un artefacto vivo.
