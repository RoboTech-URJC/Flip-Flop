<img width="6912" height="3456" alt="Copia de Banner HiroBot" src="https://github.com/user-attachments/assets/3716a34b-37c2-400c-9244-db1a0f0de220" />

<div align="center">

# 🔄 Flip-Flop Display System
### *Sistema de visualización electromecánico modular tipo Split-Flap*

[![Status](https://img.shields.io/badge/Status-In%20Development-orange?style=for-the-badge&logo=git)]()
[![Hardware](https://img.shields.io/badge/Hardware-ELEGOO%20UNO%20%7C%20ESP32-blue?style=for-the-badge&logo=arduino)]()
[![CAD](https://img.shields.io/badge/CAD-Fusion%20360-E54825?style=for-the-badge&logo=autodesk)]()
[![Association](https://img.shields.io/badge/RoboTech-URJC-red?style=for-the-badge)](https://github.com/RoboTech-URJC)

<br/>

> *Reviviendo la nostalgia de los icónicos paneles de estaciones y aeropuertos mediante fabricación aditiva, robótica modular y conectividad IoT.*

</div>

---

## 📖 Índice

- [Acerca del Proyecto](#-acerca-del-proyecto)
- [Características Principales](#-características-principales)
- [Arquitectura del Sistema](#-arquitectura-del-sistema)
- [Hardware & Componentes](#-hardware--componentes)
- [Diseño Mecánico y CAD](#-diseño-mecánico-y-cad)
- [Estado del Prototipo](#-estado-del-prototipo)
- [Hoja de Ruta (Roadmap)](#-hoja-de-ruta-roadmap)
- [Estructura del Repositorio](#-estructura-del-repositorio)
- [Equipo & Contacto](#-equipo--contacto)

---

## 💡 Acerca del Proyecto

El proyecto **Flip-Flop** es un desarrollo de ingeniería electromecánica llevado a cabo en la asociación **RoboTech URJC**. Consiste en la recreación moderna de un panel de información clásico tipo **split-flap** (pantalla de solapas mecánicas divididas).

El objetivo principal es construir una matriz modular de caracteres físicos donde cada unidad individual integra su propio actuador mecánico y lógica de control. El sistema completo estará conectado en red mediante microcontroladores, permitiendo el despliegue sincronizado de palabras, frases e información dinámica recibida de forma remota a través de una aplicación web.

---

## ✨ Características Principales

- **Mecanismo Split-Flap Clásico:** Rotación electromecánica precisa de solapas con respuesta sonora y visual característica.
- **Diseño Modular Encadenable:** Estructura pensada para acoplar múltiples módulos adyacentes y formar líneas o matrices completas de texto.
- **Control Inteligente IoT:** Transición hacia microcontroladores ESP32 con soporte Wi-Fi/Bluetooth.
- **Interfaz Web Remota:** Plataforma cliente-servidor para enviar textos, mensajes en tiempo real o integrar APIs externas (clima, eventos, avisos).
- **Fabricación 100% Repetible:** Piezas diseñadas para impresión 3D FDM de fácil ensamblaje y mantenimiento.

---

## 🛠 Arquitectura del Sistema

```text
       [ Dispositivo Usuario ] (Navegador Web / API)
                  │  (Wi-Fi / HTTP / WebSockets)
                  ▼
       [ Módulo Maestro ESP32 ] ──── Panel Web Local
                  │
      ┌───────────┴───────────┬──────────────────────┐
      │ (I2C / UART / Bus)    │                      │
      ▼                       ▼                      ▼
┌──────────────┐       ┌──────────────┐       ┌──────────────┐
│  Módulo #1   │       │  Módulo #2   │       │  Módulo #N   │
│  [Servo/Paso]│       │  [Servo/Paso]│       │  [Servo/Paso]│
│  [Flaps A-Z] │       │  [Flaps A-Z] │       │  [Flaps A-Z] │
└──────────────┘       └──────────────┘       └──────────────┘
```

---

## 🔌 Hardware & Componentes

| Subsistema | Componente Actual (Validación) | Migración Planificada |
| :--- | :--- | :--- |
| **Controlador** | ELEGOO UNO R3 (ATMega328P) | **ESP32 NodeMCU / WROOM** (Wi-Fi + BLE) |
| **Actuador** | Servomotor de control angular/continuo | Servomotor calibrado / Motor paso a paso |
| **Alimentación** | Bus 5V USB (Prototipado) | Fuente dedicada 5V switching multiamperaje |
| **Estructura** | PLA / PETG rosa impreso en 3D | PLA Mate industrial / ABS de alta durabilidad |
| **Solapas** | Placas impresas 3D con rotulación manual | Solapas troqueladas / Serigrafiadas / Corte láser |

---

## ⚙️ Diseño Mecánico y CAD

Todas las piezas han sido modeladas y optimizadas paramétricamente en **Autodesk Fusion 360**:

- **Carcasa exterior:** Aloja el carrusel de solapas, los topes mecánicos superiores e inferiores para la retención del caracter y las cavidades para el cableado.
- **Tambor rotatorio / Rotor central:** Tambor cilíndrico dotado de ranuras perimetrales de alta tolerancia diseñadas para retener las pestañas de giro libre de cada solapa.
- **Solapas divididas:** Tarjetas bi-partidas con bisagras integradas de baja fricción para asegurar caídas limpias en cada revolución.

---

## 🧪 Estado del Prototipo

```
[████████████░░░░░░░░] 60% Fase de Mecánica y Electrónica Básica
```

- [x] Modelado 3D de tambor, solapas y carcasa principal en Autodesk Fusion 360.
- [x] Impresión 3D y ensamblaje del primer prototipo funcional individual (PLA rosa).
- [x] Validación de giro mecánico y cambio controlado de letras mediante placa ELEGOO UNO R3.
- [ ] Implementación de sensor de posición de inicio (*home/homing*, p. ej., sensor de efecto Hall u optoacoplador).
- [ ] Migración completa de firmware a plataforma ESP32.
- [ ] Enlace del primer bus de comunicación entre 2 o más módulos.

---

## 🗺️ Hoja de Ruta (Roadmap)

### 🔹 Fase 1: Mecánica y Banco de Pruebas (Completada / En Ajuste)
- Calibración de tolerancias en piezas FDM.
- Verificación del torque requerido y respuesta del motor.

### 🔹 Fase 2: Conectividad y Modularidad Hardware
- Sustitución de la placa UNO por **ESP32**.
- Definición del conector de acople rápido entre módulos adyacentes (alimentación compartida + bus serie).
- Diseño de anclajes mecánicos con guías/clips para ensamble en bloque sin tornillería visible exterior.

### 🔹 Fase 3: Plataforma Software & Web Server
- Desarrollo del servidor web alojado en el microcontrolador (o API backend Node.js/Python).
- Frontend reactivo para ingresar texto, seleccionar transiciones mecánicas y configurar la red Wi-Fi.

### 🔹 Fase 4: Fabricación Final y Acabado Estético
- Producción de juego de solapas estandarizadas mediante serigrafía, vinilo o corte láser para caracteres nítidos y uniformes.
- Montaje de vitrina/bastidor multi-carácter (palabras completas).

---

## 📂 Estructura del Repositorio

```text
Flip-Flop/
├── cad/                     # Archivos de modelado 3D (.step, .f3d, .stl)
│   ├── chassis/             # Chasis y tapas exteriores
│   ├── rotor/               # Tambor central y piñones
│   └── flaps/               # Solapas y ejes de giro
├── firmware/                # Código fuente del microcontrolador
│   ├── uno_validation/      # Firmware básico de pruebas con Elegoo UNO R3
│   └── esp32_modular/       # Firmware final con stack Wi-Fi / I2C
├── web/                     # Interfaz web y backend de control
├── docs/                    # Dossier técnico, esquemas eléctricos y manuales
└── README.md                # Documentación principal del proyecto
```

---

## 👥 Equipo & Contacto

* **Autor del Proyecto:** Nicolás Abad Andrade  
* **Organización:** [RoboTech URJC](https://github.com/RoboTech-URJC)  
* **Sede:** Universidad Rey Juan Carlos – Campus de Fuenlabrada  
* **Correo de Contacto:** [asociacion.robotech@urjc.es](mailto:asociacion.robotech@urjc.es)

---
<div align="center">
  <sub>Desarrollado con pasión y engranajes por RoboTech URJC.</sub>
</div>
