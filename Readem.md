graph TD
    A[Inicio] --> B[Cargar datos desde archivos .pkl];
    B --> C{Mostrar Menú Principal};
    
    C -->|Opción 1| D[Registrar Nueva Solicitud];
    D --> E[Guardar datos en solicitudes.pkl];
    E --> C;

    C -->|Opción 2| F[Registrar Nuevo Técnico];
    F --> G[Guardar datos en tecnicos.pkl];
    G --> C;

    C -->|Opción 3| H[Asignar Solicitud];
    H --> I{¿IDs válidos?};
    I -->|Sí| J[Actualiza Solicitud y Guarda];
    I -->|No| K[Mostrar Error];
    J --> C;
    K --> C;

    C -->|Opción 4| L[Actualizar Estado Solicitud];
    L --> M{¿ID encontrado?};
    M -->|Sí| N[Actualiza Estado y Guarda];
    M -->|No| O[Mostrar Error];
    N --> C;
    O --> C;

    C -->|Opción 6| Z[Fin];

    C -->|Inválido| P[Mostrar 'Opción no válida'];
    P --> C;

    C -->|Opción 5: Reportes| R_A;

    subgraph Menú de Reportes
        R_A[Mostrar Menú de Reportes] --> R_B{Elegir Opción de Reporte};
        R_B -->|Opción 1| R_C[Reporte por Estado];
        R_C --> R_A;
        R_B -->|Opción 2| R_D[Reporte por Técnico];
        R_D --> R_A;
        R_B -->|Opción 3| R_E[Reporte por Área];
        R_E --> R_A;
        R_B -->|Inválido| R_F[Mostrar 'Opción no válida'];
        R_F --> R_A;
    end

    R_B -->|Opción 4: Volver| C;