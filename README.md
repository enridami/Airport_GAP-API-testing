# Airport Gap REST API Testing Project - Postman

## Descripción
Proyecto de **API Testing Manual** enfocado en el aseguramiento de la calidad (QA) sobre el backend de la plataforma **Airport Gap**. El objetivo fue auditar la lógica de negocio del servidor mediante solicitudes HTTP, verificando la gestión de recursos públicos y privados, validaciones de esquemas de datos y resiliencia del backend ante fallos simulados.

---

## API y Entorno Bajo Prueba
*   **Plataforma:** Airport Gap API
*   **Base URL:** `https://airportgap.com`
*   **Módulo Auditado:** Gestión de Catálogos y Usuarios Privados (Tokens / Favorites).
*   **Enfoque de Pruebas:** Caja Negra mediante comunicación directa de endpoints.

---

## Alcance de las Pruebas (8 Requisitos del Sistema)
El plan de pruebas cubrió las siguientes especificaciones operativas (REQ):
*   **REQ-001:** Consulta de directorios públicos generales del sistema mediante **GET**.
*   **REQ-002:** Generación de tokens de seguridad (Bearer Authentication) mediante **POST**.
*   **REQ-003:** Restricción estricta de rutas privadas ante accesos anónimos (**Error 401**).
*   **REQ-004:** Inserción y guardado de registros privados de favoritos mediante **POST**.
*   **REQ-005:** Actualización y modificación de datos del usuario mediante **PATCH**.
*   **REQ-006:** Eliminación individual y masiva de registros del sistema mediante **DELETE**.
*   **REQ-007:** Intercambio y estructuración obligatoria de datos en formato **JSON**.
*   **REQ-008:** Control de campos requeridos y obligatorios en el cuerpo del Payload (**Error 422**).

---

## Tipos de Testing Aplicados
*   **API Functional Testing:** Verificación del ciclo CRUD de la base de datos.
*   **Positive & Negative Testing:** Validación de flujos felices y manejo de datos erróneos/incompletos.
*   **Security Testing:** Auditoría de cabeceras de autorización (`Authorization: Bearer token`).
*   **Failure Simulation Testing:** Uso de headers avanzados (`X-Simulate`) para auditar la robustez del servidor ante contingencias.

---

## Herramientas Utilizadas
*   **Postman** 
*   **Microsoft Excel** 
*   **Airport Gap Documentation**

---

## Métricas y Control de Defectos (Bugs)

| Métrica | Valor | Estado |
| :--- | :---: | :---: |
| **Total Test Cases** | 20 | 100% |
| **Casos Exitosos (PASS)** | 19 | Validado |
| **Casos Fallidos (FAIL)** | 1 | Defectos detectados |
| **Bugs Reportados** | 1 | Documentados en Matriz |

### Registro Técnico de Incidentes (Simulados para Control de Portafolio):
**BUG-001 (TC-017):** Al simular una degradación de transferencia de red (`malformed-json`), el backend expone un cuerpo truncado que rompe el Requerimiento de integridad de datos. Estado: **FAIL**.



