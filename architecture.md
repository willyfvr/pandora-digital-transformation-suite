# Arquitectura del Sistema de Gestión de Datos - Pandora Box Gym

Este documento detalla la infraestructura técnica y el flujo de datos (Data Pipeline) implementado para la transformación digital del gimnasio. El diseño se centra en la **integridad de los datos**, la **escalabilidad** y la **experiencia del usuario (UX)**.

## 1. Diagrama de Flujo de Datos (Mermaid)

Utilizamos un modelo de arquitectura centralizado en el ecosistema de Google para asegurar disponibilidad 24/7 y costo operativo cero.

```mermaid
graph TD
    A[Socio / Usuario] -->|Escaneo de QR / Link WA| B(Google Forms)
    
    subgraph Capa de Captura y Validación
    B --> C{Lógica de Secciones}
    C -->|Validación RegEx| D[Datos Personales]
    C -->|Input Condicional| E[Ficha Médica]
    C -->|Aceptación Legal| F[Declaración Jurada]
    end

    subgraph Capa de Almacenamiento (Estado Actual)
    D & E & F --> G[(Google Sheets - Raw Data)]
    end

    subgraph Capa de Salida y Acción
    G --> H[Gestión Manual / Consultas]
    B -.->|Redirect| I[WhatsApp Business]
    end

    subgraph Futuras Implementaciones (Roadmap)
    G -.-> J[Looker Studio Dashboard]
    G -.-> K[Google Apps Script Automation]
    end