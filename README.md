# Student Hub - Portal Central

Un dashboard académico e integrador de recursos diseñado como una Single Page Application (SPA) para la gestión organizada de actividades de estudio, portales universitarios y marcadores.

---

## Características principales

* **Gestión Académica**: Visualización dinámica de universidades, carreras y accesos directos a aulas virtuales.
* **Marcadores Recientes**: Clasificación, filtrado por tipo (PDF, Video, Curso, Sitio) y búsqueda rápida de enlaces de interés.
* **Calendario Dinámico**: Control de fechas clave, agendamiento de entregas académicas y seguimiento del vencimiento de la colegiatura.
* **Portabilidad de Datos**: Herramientas para importar y exportar la configuración completa en formato JSON.
* **Interfaz Adaptable**: Soporte para temas claro/oscuro y diseño optimizado para pantallas móviles y de escritorio.

---

## Estructura del Dashboard

El siguiente diagrama explica el flujo de datos, la navegación y las vistas integradas dentro de la SPA:

```mermaid
graph TD
    %% Navegación y Vistas
    Sidebar[Navegación / Sidebar] -->|Cambio de Vista| SPA{Controlador SPA}
    SPA -->|Vista Activa| V1[Dashboard Principal]
    SPA -->|Vista Activa| V2[Archivo de Marcadores]
    SPA -->|Vista Activa| V3[Configuración Académica]

    %% Flujos de Información en Dashboard
    subgraph V1 [Dashboard Principal]
        A1[Tarjeta de Universidades] --- Subject[Materias & Aulas]
        A2[Gestor de Marcadores] --- BookmarkList[Lista Filtrable]
        A3[Calendario Académico] --- EventList[Tareas & Colegiaturas]
    end

    %% Flujos de Información en Archivo
    subgraph V2 [Archivo de Marcadores]
        B1[Historial de Enlaces] -->|Restaurar| A2
        B1 -->|Eliminar| DB[(LocalStorage)]
    end

    %% Flujos de Información en Configuración
    subgraph V3 [Configuración Académica]
        C1[Gestor de Universidades] -->|Crear/Editar/Eliminar| DB
        C2[Portabilidad JSON] -->|Exportar / Importar| DB
    end

    %% Persistencia Común
    DB -.->|Sincronización| V1

```

---

## Tecnologías utilizadas

* **HTML5** y **Tailwind CSS** (para la maquetación y estilos interactivos adaptables).
* **JavaScript (Vanilla)** (para la lógica SPA, manipulación del DOM y procesamiento del calendario).
* **FontAwesome Icons** (para el soporte gráfico iconográfico).
* **LocalStorage** (para la persistencia local de los datos del usuario).

## Licencia

Este proyecto está licenciado bajo la Licencia MIT. Para más detalles consulta el archivo [LICENSE](LICENSE).

## Autor

Proyecto desarrollado por **Rosendo Camal**.

Contacto:
* [`GitHub`](https://github.com/rosendocamal)
* [`Linkedin`](https://www.linkedin.com/in/rosendocamal)
