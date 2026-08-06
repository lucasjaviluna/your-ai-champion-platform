---
sidebar_position: 13
title: "Protocolos y comunicación entre agentes"
description: "Cómo se comunican modelos, agentes, herramientas y sistemas mediante protocolos modernos."
---

# Protocolos y comunicación entre agentes

## 🎯 Objetivos

Al finalizar este capítulo podrás:

- Comprender por qué los agentes necesitan protocolos.
- Conocer MCP.
- Comprender A2A.
- Entender Tool Calling Protocols.
- Diseñar arquitecturas desacopladas.

---

# Introducción

En Internet los sistemas hablan mediante protocolos.

Por ejemplo:

```
HTTP

HTTPS

SMTP

FTP
```

---

Los agentes también necesitan protocolos.

No deberían depender de llamadas específicas entre librerías.

---

Necesitan un lenguaje común.

---

# ¿Por qué?

Imaginemos:

```
Developer Agent

↓

Filesystem

↓

Git

↓

Database

↓

Cloud
```

Si cada integración es diferente:

```
Más código.

Más acoplamiento.

Más mantenimiento.
```

---

Un protocolo define:

- mensajes,
- formatos,
- capacidades,
- negociación,
- errores.

---

# Evolución

Primero:

```
LLM

↓

Prompt

↓

Respuesta
```

---

Luego:

```
LLM

↓

Tool Calling

↓

Respuesta
```

---

Ahora:

```
Agent

↓

Protocolos

↓

Servicios

↓

Otros agentes
```

---

# MCP

Uno de los protocolos más importantes es:

```
Model Context Protocol
```

---

Su objetivo:

Permitir que cualquier modelo pueda acceder a contexto externo mediante una interfaz estándar.

---

Modelo conceptual:

```text
LLM

↓

MCP Client

↓

MCP Server

↓

Herramientas

Datos

Servicios
```

---

Ventajas:

- desacoplamiento,
- reutilización,
- interoperabilidad.

---

# A2A

Otro concepto emergente:

```
Agent-to-Agent
```

---

Permite que un agente pueda solicitar trabajo a otro.

Ejemplo:

```
Planner

↓

Developer

↓

QA
```

---

Cada agente mantiene su propia identidad.

---

# Tool Calling

Hoy prácticamente todos los proveedores soportan herramientas.

El patrón general es:

```
Agent

↓

Tool Request

↓

Tool Execution

↓

Tool Result

↓

Agent
```

---

El runtime no necesita conocer la implementación.

Solo el contrato.

---

# Contratos

En lugar de pasar texto libre:

```json
{
  "type": "architecture-review",
  "specification": "SPEC-101",
  "constraints": [
    "Use Angular Signals",
    "Keep backward compatibility"
  ]
}
```

---

Los contratos mejoran:

- interoperabilidad,
- validación,
- versionado.

---

# Protocolos y SDD

Aquí aparece una relación muy interesante.

SDD define:

```
Qué hacer.
```

Los protocolos definen:

```
Cómo colaborar.
```

---

# Relación con Your Harness

Una posible arquitectura sería:

```text
Specification Engine

↓

Workflow Engine

↓

Agent Runtime

↓

Protocol Layer

↓

MCP

A2A

Tool Calling

↓

Integraciones
```

---

Esto permitiría cambiar un proveedor o una herramienta sin modificar el resto de la plataforma.

---

# Buenas prácticas

- Utilizar protocolos estándar cuando existan.
- Basar la comunicación en contratos.
- Versionar los mensajes.
- Evitar dependencias directas entre agentes.

---

# Conceptos clave

- Los protocolos desacoplan componentes.
- MCP estandariza el acceso al contexto.
- A2A estandariza la colaboración entre agentes.
- Los contratos son preferibles al texto libre.
- Las plataformas modernas deben diseñarse pensando en interoperabilidad.

---

# Próximo módulo

## Specification-Driven Development (SDD)

Comenzaremos estudiando el paradigma que servirá como base para todo el resto del curso.
