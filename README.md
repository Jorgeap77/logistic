# Flujograma Logístico de Abastecimiento FENIX 4-8-37 al Sistema Defensivo Territorial

Aquí se detalla el proceso de abastecimiento de las raciones FENIX 4-8-37, desde el origen de la materia prima hasta la entrega al Sistema Defensivo Territorial (SDT) y el ciclo de retroalimentación para la mejora continua.

La ración FENIX 4-8-37 es un prototipo integral de 24 horas, autosuficiente, que incluye alimentos en envases retortables esterilizados, formulados para consumo inmediato o tras calentamiento. Todos los componentes están contenidos en una bolsa máster de polipropileno de alta resistencia con cierre ziplock, e integra un calentador táctico sin llama de producción nacional. La producción está proyectada a una escala estratégica de 10.000 unidades con un costo objetivo de 12 USD por ración.

Cuenta con tres menús de inspiración venezolana, buscando satisfacer los requerimientos nutricionales y elevar la moral de la tropa:

* **Menú 1:** Desayuno (Arepa asada c/pollo mechado, Café c/leche), Almuerzo (Sopa de carne y vegetales, Pabellón criollo, Bebida papelón), Cena (Bollo aliñado c/cerdo, Bebida papelón), Misceláneos (Bocadillo plátano, Chocolate c/leche, Turrón blanco).
* **Menú 2:** Desayuno (Empanada carne molida, Café c/leche), Almuerzo (Sopa de carne y vegetales, Pasta boloñesa, Bebida papelón), Cena (Rebanadas tostadas c/ajonjolí, Mermelada de guayaba, Bebida papelón), Misceláneos (Bocadillo plátano, Chocolate c/leche, Turrón de almendras).
* **Menú 3:** Desayuno (Empanada pollo, Café c/leche), Almuerzo (Sopa de carne y vegetales, Arroz con pollo, Bebida papelón), Cena (Rebanadas tostadas c/orégano, Sardinas en salsa de tomate, Bebida papelón), Misceláneos (Bocadillo plátano, Chocolate c/leche, Turrón de almendras).

---

```mermaid
graph TD
    %% Definición de Estilos para Nodos (Opcional, para mejor visualización)
    style A fill:#D0F0C0,stroke:#3C8E3C,stroke-width:2px;
    style B fill:#FFFACD,stroke:#DAA520,stroke-width:2px;
    style C fill:#C0D9F0,stroke:#4682B4,stroke-width:2px;
    style C_M1 fill:#E0FFFF,stroke:#4682B4,stroke-width:1px;
    style C_M2 fill:#E0FFFF,stroke:#4682B4,stroke-width:1px;
    style C_M3 fill:#E0FFFF,stroke:#4682B4,stroke-width:1px;
    style C_Empaque fill:#E0FFFF,stroke:#4682B4,stroke-width:1px;
    style C_Final fill:#ADD8E6,stroke:#4682B4,stroke-width:2px;
    style D fill:#FFFACD,stroke:#DAA520,stroke-width:2px;
    style E fill:#D9EDF7,stroke:#5BC0DE,stroke-width:2px;
    style F fill:#F5DEB3,stroke:#CD853F,stroke-width:2px;
    style G fill:#FFDDC1,stroke:#E27000,stroke-width:2px;
    style H fill:#E0FFFF,stroke:#4682B4,stroke-width:2px;

    %% Subgraph principal para toda la cadena
    subgraph Cadena de Abastecimiento FENIX 4-8-37 al SDT
        direction LR

        A[**ORIGEN DE MATERIA PRIMA**<br/>Servicio de Alimentación GNB] --> B{**TRANSPORTE INICIAL**<br/>Materia Prima a Carúpano};

        subgraph PRODUCCIÓN Y PROCESAMIENTO: Planta FENIX Carúpano
            direction TB

            C[**RECEPCIÓN Y PREPARACIÓN**<br/>(Verificación, Almacenamiento Insumos)];

            subgraph Elaboración Menús FENIX (3 Tipos)
                C --> C_M1(Producción MENÚ 1);
                C --> C_M2(Producción MENÚ 2);
                C --> C_M3(Producción MENÚ 3);
            end

            C_M1 & C_M2 & C_M3 --> C_Proceso(Envasado Retortable & Esterilización Comercial);
            C_Proceso --> C_QC(Control de Calidad (Sanitario, Nutricional));
            C_QC --> C_Ensamblaje(Ensamblaje Ración Completa<br/>(Incluye Calentador Táctico SIN LLAMA, Utensilios, Misceláneos));
            C_Ensamblaje --> C_Empaque(Empaque Final en Bolsa Máster<br/>(Polipropileno c/ Ziplock, Codificación por Menú));
            C_Empaque --> H(**PRODUCCIÓN FENIX TERMINADA**<br/>(10.000 Raciones/Batch, $12/ración));
        end

        B --> C; %% Conexión del transporte a la recepción en Carúpano
        H --> D{**ALMACENAMIENTO Y GESTIÓN LOGÍSTICA**<br/>Centro Logístico Regional / Punto Adaptado URRA};
        D --> E[**DISTRIBUCIÓN FINAL**<br/>A Unidades del SDT (GUC, GC(s), Formaciones)];
        E --> F{**CONSUMO Y RECOLECCIÓN DE RETROALIMENTACIÓN**<br/>(Uso en Campo, Satisfacción)};
        F --> G(**ANÁLISIS Y AJUSTE DEL SISTEMA**<br/>(Informes de Calidad, Oportunidad, Eficiencia));
        G --> A; %% Retroalimentación al Origen
        G --> C; %% Retroalimentación a Producción para ajustes de proceso
        G --> D; %% Retroalimentación a Almacenamiento/Distribución para optimización

        %% Leyendas de flujos importantes
        A -- Materia Prima Diversa<br/>(según 3 Menús) --> B;
        C_Ensamblaje -- Integración de componentes<br/>Nacionales/Importados --> H;
        H -- Despacho de Lotes<br/>(Ej: 10.000 Raciones) --> D;
        D -- Gestión de Inventario<br/>(por Menú) --> E;
        E -- Entrega Efectiva<br/>al SDT --> F;
        F -- Informes de Desempeño<br/>y Sugerencias --> G;
        G -- Directrices de Optimización<br/>y Mejora Continua --> A;
        G -- Ajustes de Proceso<br/>en Fábrica --> C;
        G -- Rediseño de Rutas/Almacenamiento --> D;
```
    end
