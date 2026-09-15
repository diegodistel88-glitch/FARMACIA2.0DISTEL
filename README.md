# 🏥 UCI · Sistema de Indicaciones Médicas y Farmacia

Sistema web para la gestión integral de indicaciones médicas, atención de enfermería y pedidos a farmacia en unidades de cuidados intensivos e intermedios.

![Estado](https://img.shields.io/badge/estado-activo-brightgreen)
![Versión](https://img.shields.io/badge/versión-5.0-blue)
![Licencia](https://img.shields.io/badge/licencia-privada-red)

---

## 📋 Descripción General

Aplicación HTML/CSS/JS de una sola página (SPA) que permite gestionar el flujo completo de indicaciones médicas en un servicio de internación:

- **Médicos** autorizan indicaciones con detalle clínico + items de farmacia
- **Enfermeros** ejecutan las indicaciones organizadas por turno y cargan EPP
- **Farmacia** recibe todos los pedidos con trazabilidad completa
- **Historial** de indicaciones finalizadas y suspendidas

Diseñada para funcionar **offline** (salvo la carga del vademécum desde `data/vademecum.json`) y adaptable a tablets, monitores de enfermería y computadoras de escritorio.

---

## 🎯 Funcionalidades principales

### 👨‍⚕️ Pestaña Médico
- Alta de indicaciones con **tipo, indicación médica (texto libre), vía, frecuencia y médico**.
- Columna **Farmacia 🔍** con buscador de vademécum para agregar múltiples insumos a la indicación.
- Ejemplo: `PHP` + `Sol Fis 500 ml + Sulfato de Magnesio 1 amp + 30 meq Cloruro de Potasio`.
- **Autorización** bloquea la fila y envía los items a Farmacia multiplicados por cada horario.
- Botón **Finalizar / Suspender** con trazabilidad del médico responsable.
- **Historial** visible al pie de la pestaña.

### 👩‍⚕️ Pestaña Enfermería
- Indicaciones del médico **organizadas por turno** (Mañana · Tarde · Vespertino · Noche).
- **Atenciones de Enfermería** dentro de cada turno (con botón "+ Nueva atención").
- Carga de materiales por indicación ejecutada.
- Botón **"Agregar más EPP"** por turno (permite múltiples cargas durante el turno).
- **Historial de cargas EPP** por turno con quién, cuándo y qué.

### 💊 Pestaña Farmacia
- **Resumen agrupado**: sumatoria total por material + código.
- **Detalle por acción**: cada pedido individual con origen (M / ENF / AISL / MAN), profesional responsable, fecha y hora.
- Trazabilidad completa para auditoría.

### 📜 Pestaña Finalizadas
- Tabla con todas las indicaciones **finalizadas y suspendidas**.
- Muestra médico que autorizó, médico que finalizó, motivo y observaciones.

### 🦠 Precauciones de Aislamiento
Soporte para 13 tipos con colores distintivos:

| Precaution | Color |
|---|---|
| Estándar | 🟢 Verde |
| Contacto | 🟡 Amarillo |
| Contacto Esporas | 🟠 Naranja |
| Contacto MR | 🔴 Rojo |
| Por Gotas | 🔵 Azul |
| Aéreo | 🟢 Verde |
| Protectivo / Ambiente Protegido | 🩵 Celeste |
| Contacto + Gotas | 🟡🔵 Degradado |
| Contacto + Aéreo | 🟡🟢 Degradado |
| Contacto MR + Gotas | 🔴🔵 Degradado |
| Contacto MR + Aéreo | 🔴🟢 Degradado |
| Contacto Esporas + Gotas | 🟠🔵 Degradado |
| Aéreo + Gotas | 🟢🔵 Degradado |

Cada precaution trae su EPP sugerido automáticamente.

> **Nota:** el Barbijo N95 no se carga desde este sistema. Se gestiona por otras vías por ser reutilizable.

---

## 📁 Estructura del proyecto
