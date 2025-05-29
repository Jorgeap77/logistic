graph TD
    subgraph Cadena de Abastecimiento FENIX 4-8-37 al SDT
        direction LR

        A[**ORIGEN DE MATERIA PRIMA** - Servicio de Alimentación GNB] --> B{**TRANSPORTE INICIAL** - Materia Prima a Carúpano};

        subgraph PRODUCCIÓN Y PROCESAMIENTO - Planta FENIX Carúpano
            direction TB

            C[**RECEPCIÓN Y PREPARACIÓN** - Verificación y Almacenamiento de Insumos];

            subgraph Producción de Menús FENIX
                C --> C_M1(Producir MENÚ 1);
                C --> C_M2(Producir MENÚ 2);
                C --> C_M3(Producir MENÚ 3);
            end

            C_M1 & C_M2 & C_M3 --> C_Proceso(Envasado Retortable y Esterilización Comercial);
            C_Proceso --> C_QC(Control de Calidad);
            C_QC --> C_Assembly(Ensamblaje de Ración incluyendo Calentador Táctico sin Llama, Utensilios, Misc.);
            C_Assembly --> C_Packaging(Empaque Final en Bolsa Máster de Polipropileno con Ziplock y Codificación de Menú);
            C_Packaging --> H(**PRODUCCIÓN FENIX TERMINADA** - 10.000 Raciones por Lote a $12 por ración);
        end

        B --> C;
        H --> D{**ALMACENAMIENTO Y GESTIÓN LOGÍSTICA** - Centro Logístico Regional / Punto Adaptado URRA};
        D --> E[**DISTRIBUCIÓN FINAL** - A Unidades del SDT incluyendo GUC, GC y Formaciones];
        E --> F{**CONSUMO Y RECOLECCIÓN DE RETROALIMENTACIÓN** - Uso en Campo y Satisfacción};
        F --> G(**ANÁLISIS Y AJUSTE DEL SISTEMA**);
        G --> A;
        G --> C;
        G --> D;

        A -- Materias Primas Diversas por 3 Menús --> B;
        C_Assembly -- Integración de Componentes --> H;
        H -- Despacho de Lote de 10.000 Raciones --> D;
        D -- Gestión de Inventario por Menú --> E;
        E -- Entrega Efectiva al SDT --> F;
        F -- Informes de Desempeño y Sugerencias --> G;
        G -- Directivas de Optimización --> A;
        G -- Ajustes de Proceso --> C;
        G -- Rediseño de Ruta y Almacenamiento --> D;

    end
