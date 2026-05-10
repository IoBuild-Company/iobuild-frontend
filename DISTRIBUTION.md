# 📋 Plan de Distribución de Desarrollo - Proyecto IoBuild Frontend

Este documento detalla la responsabilidad de cada integrante para la gestión de commits y desarrollo del repositorio. Cada miembro es responsable de los archivos y carpetas en sus rutas asignadas para mantener la integridad del proyecto y minimizar conflictos en Git.

---

## 1. Jhosep Argomedo: Infraestructura Core, Shared e IAM
**Objetivo:** Establecer la base técnica, los servicios compartidos y el sistema de autenticación.

*   **Archivos Base del Proyecto (Raíz de `src/`):**
    *   `src/main.js`
    *   `src/router.js`
    *   `src/pinia.js`
    *   `src/i18n.js`
    *   `src/App.vue`
    *   `src/style.css`
*   **Módulo Shared:**
    *   `src/shared/infrastructure/base-api.js`
    *   `src/shared/infrastructure/base-endpoint.js`
    *   `src/shared/presentation/components/layout.vue`
    *   `src/shared/presentation/components/language-switcher.vue`
    *   `src/shared/presentation/views/configuration.vue`
    *   `src/shared/presentation/views/page-not-found.vue`
*   **Módulo IAM (Seguridad):**
    *   `src/iam/application/iam.store.js`
    *   `src/iam/domain/model/authenticated-user.entity.js`
    *   `src/iam/domain/model/user.entity.js`
    *   `src/iam/infrastructure/authenticated-user.assembler.js`
    *   `src/iam/infrastructure/iam-api.js`
    *   `src/iam/infrastructure/user.assembler.js`
    *   `src/iam/presentation/iam-routes.js`
    *   `src/iam/presentation/views/login.vue`
    *   `src/iam/presentation/views/register-builder.vue`
    *   `src/iam/presentation/views/register-owner.vue`

---

## 2. Sebastian Ramirez: Analytics & Business Intelligence
**Objetivo:** Implementar la visualización de datos, métricas y el monitoreo de proyectos.

*   **Módulo Analytics:**
    *   **Application:** `src/analytics/application/analytics.store.js`
    *   **Domain:** `src/analytics/domain/model/builder-dashboard.entity.js`, `historical-data-point.entity.js`, `owner-dashboard.entity.js`
    *   **Infrastructure:** `src/analytics/infrastructure/analytics-api.js`, `builder-dashboard.assembler.js`, `historical-data.assembler.js`, `owner-dashboard.assembler.js`
    *   **Components:** `src/analytics/presentation/components/builder-dashboard.component.vue`, `owner-dashboard.component.vue`, `project-card.component.vue`, `stat-card.component.vue`, `unit-card.component.vue`
    *   **Views & Routes:** `src/analytics/presentation/views/analytics-dashboard.view.vue`, `src/analytics/presentation/analytics-routes.js`

---

## 3. Axel Ordoñez: Gestión de Proyectos y Clientes
**Objetivo:** El núcleo operativo del negocio (CRM y gestión de obras).

*   **Módulo Projects:**
    *   `src/projects/application/project.store.js`
    *   `src/projects/domain/model/project.entity.js`
    *   `src/projects/infrastructure/project-api.js`
    *   `src/projects/infrastructure/project.assembler.js`
    *   `src/projects/presentation/projects-routes.js`
    *   `src/projects/presentation/components/project-card.vue`
    *   `src/projects/presentation/views/project-details.vue`, `project-form.vue`, `project-grid.vue`
*   **Módulo Clients:**
    *   `src/clients/application/client.store.js`
    *   `src/clients/domain/model/client.entity.js`
    *   `src/clients/infrastructure/client-api.js`, `client.assembler.js`, `projects.facade.js`
    *   `src/clients/presentation/clients-routes.js`
    *   `src/clients/presentation/components/client-actions-menu.vue`, `client-add-dialog.vue`, `client-edit-dialog.vue`, `client-list-header.vue`, `clients-table.vue`
    *   `src/clients/presentation/views/client-list.vue`, `client-profile.vue`

---

## 4. Fabrizio Panta: Inventario de Dispositivos y Automatización
**Objetivo:** Gestión técnica de hardware, tablas de dispositivos y control de estado.

*   **Módulo Devices:**
    *   `src/devices/application/device.store.js`
    *   `src/devices/domain/model/device.entity.js`
    *   `src/devices/infrastructure/device-api.js`, `device.assembler.js`
    *   `src/devices/presentation/automation-routes.js`
    *   `src/devices/presentation/components/device-actions-menu.vue`, `device-edit-dialog.vue`, `device-list-header.vue`, `devices-table.vue`
    *   `src/devices/presentation/views/device-management.vue`

---

## 5. Brayan Ccarita: Gestión de Perfiles, Ajustes y Suscripciones
**Objetivo:** Personalización de usuario, configuración regional y sistema de monetización.

*   **Módulo Profiles:**
    *   `src/profiles/application/profile.store.js`
    *   `src/profiles/domain/model/profile.entity.js`
    *   `src/profiles/infrastructure/iam.facade.js`, `profile-api.js`, `profile.assembler.js`
    *   `src/profiles/presentation/profiles-routes.js`
    *   `src/profiles/presentation/views/profile-builder.vue`, `profile-owner.vue`, `profile-router.vue`
    *   `src/profiles/presentation/components/account-info-section.vue`, `language-section.vue`, `profile-header.vue`, `scenes-section.vue`, `toggle-item.vue`
*   **Módulo Subscriptions:**
    *   `src/subscriptions/application/subscription.store.js`
    *   `src/subscriptions/domain/model/plan.entity.js`, `subscription.entity.js`
    *   `src/subscriptions/infrastructure/iam.facade.js`, `plan-api.js`, `plan.assembler.js`, `subscription-api.js`, `subscription.assembler.js`
    *   `src/subscriptions/presentation/subscriptions-routes.js`
    *   `src/subscriptions/presentation/components/current-plan-card.vue`, `plan-card.vue`, `previous-invoices-modal.vue`
    *   `src/subscriptions/presentation/views/my-subscription.vue`
*   **Ajustes Shared & Locales:**
    *   `src/shared/presentation/components/change-password.vue`
    *   `src/shared/presentation/components/alternate-mail.form.vue`
    *   `src/locales/en.json`, `src/locales/es.json`

---

## 🛠️ Reglas de Trabajo para Git:
1.  **Aislamiento:** Trabaja estrictamente en los archivos de tu sección.
2.  **Sincronización:** Jhosep (Core) debe subir los archivos base primero.
3.  **Conflictos:** Si necesitas modificar un archivo asignado a otro compañero, consúltalo antes.
4.  **Commits:** Usa mensajes descriptivos, ej: `feat(projects): add project grid and store logic`.
