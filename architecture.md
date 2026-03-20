graph LR
    A[Usuario / Socio] -- Escanea QR --> B(Google Forms)
    
    subgraph Validación y Captura
    B --> C{Lógica Condicional}
    C -- Menor de edad --> D[Alerta Tutor]
    C -- Antecedentes --> E[Alerta Médica]
    end

    subgraph Procesamiento de Datos
    D & E --> F[(Google Sheets)]
    F --> G[Data Cleaning / Fórmulas]
    end

    subgraph Visualización y Acción
    G --> H[Looker Studio Dashboard]
    G --> I[WhatsApp Link Generation]
    end

    style B fill:#4285F4,color:#fff
    style F fill:#34A853,color:#fff
    style H fill:#FBBC05,color:#333

