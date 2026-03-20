# Arquitectura del Sistema de Gestión de Datos - Pandora Box Gym

Este documento detalla la infraestructura técnica y el flujo de datos (Data Pipeline) implementado para la transformación digital del gimnasio. El diseño se centra en la **integridad de los datos**, la **escalabilidad** y la **experiencia del usuario (UX)**.

## 1. Diagrama de Flujo de Datos (Mermaid)

Utilizamos un modelo de arquitectura centralizado en el ecosistema de Google para asegurar disponibilidad 24/7 y costo operativo cero.

```mermaid
graph TD
    A[Socio / Usuario] -->|Escaneo de QR / Link WA| B(Google Forms)
    
    subgraph Captura_y_Validacion
    B --> C{Logica de Secciones}
    C -->|Validacion RegEx| D[Datos Personales]
    C -->|Input Condicional| E[Ficha Medica]
    C -->|Aceptacion Legal| F[Declaracion Jurada]
    end

    subgraph Almacenamiento
    D & E & F --> G[(Google Sheets - Raw Data)]
    end

    subgraph Salida_y_Accion
    G --> H[Gestion Manual / Consultas]
    B -.->|Redirect| I[WhatsApp Business]
    end

    subgraph Roadmap
    G -.-> J[Looker Studio Dashboard]
    G -.-> K[Google Apps Script Automation]
    end

    style B fill:#4285F4,stroke:#333,stroke-width:2px,color:#fff
    style G fill:#34A853,stroke:#333,stroke-width:2px,color:#fff
    style J fill:#FBBC05,stroke:#333,stroke-width:2px,color:#333