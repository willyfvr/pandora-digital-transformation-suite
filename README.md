
# Digitalización y Automatización de Gestión de Socios - Pandora Box Gym

Rol: Data Analyst & Digital Strategist.

## 📋 Contexto y Problema

El gimnasio "Pandora Box" operaba con fichas de salud en formato papel (ficheros físicos). Este sistema presentaba los siguientes riesgos:

Pérdida de información: Difícil recuperación de datos históricos.

Riesgo Legal: Dificultad para auditar quién presentó el certificado médico obligatorio (ley 25.326).

Inexistencia de métricas: Imposibilidad de conocer la edad promedio, horas pico o patologías prevalentes de la población activa.



## 🚀 Solución Implementada

Diseñé un ecosistema digital de bajo costo (zero budget) y alta escalabilidad:

Captura de Datos: Formulario en Google Forms con lógica condicional para reducir la fatiga del usuario y validación de tipos de datos (RegEx para DNI y Teléfonos).

Base de Datos: Vinculación en tiempo real con Google Sheets, estructurada para análisis estadístico (Limpieza de datos automática).

UX & Comunicación: Implementación de un flujo de confirmación con redirección directa a WhatsApp mediante enlaces dinámicos (wa.link).


## 🛠️ Stack Tecnológico

Google Workspace: Forms & Sheets (Core de recolección).

Markdown: Para documentación técnica.

WhatsApp Business API (Concept): Planificado para la V2.


## 📊 Valor Agregado (Insights)

Gracias a la estructura de "Cuadrícula de opciones" en la sección de enfermedades, el negocio ahora puede:

Filtrar socios por nivel de riesgo médico en 1 clic.

Identificar el porcentaje de menores de edad para gestión de autorizaciones.

Automatizar el seguimiento de certificados de aptitud física (vencimientos a 60 días).