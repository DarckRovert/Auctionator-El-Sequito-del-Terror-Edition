# ðŸ“ Wiki: Arquitectura 'Diamond Tier' â€” Auctionator [v1.2.2]

Estructura tÃ©cnica de la gestiÃ³n de subasta mantenida por **DarckRovert**.

## ðŸ—ï¸ JerarquÃ­a del Sistema Trading (Trade Hierarchy)

Auctionator gestiona la economÃ­a mediante una capa ligera sobre la interfaz de subastas original:

1.  **Motor de Escaneo (`Auctionator.lua`)**: Interceptor de consultas al servidor de subastas. Gestiona el "Fast Scan".
2.  **Analizador de Precios (Data Logic)**: Algoritmo que procesa la competencia y sugiere el punto de venta Ã³ptimo.
3.  **Sistema de Interfaz (`Auctionator.xml`)**: AÃ±ade las pestaÃ±as de "Buy" y "Sell" de forma no intrusiva.
4.  **Capa de Persistencia (`SavedVariables`)**: Almacena el historial de precios y las preferencias de usuario (alt-enable, etc.)

---

## ðŸ§­ Diagrama de Flujo: Proceso de Venta v9.4

```mermaid
graph TD
    A[Inicio: Abrir Subasta] --> B[Escaneo de Competencia Fast-Scan]
    B --> C[ActualizaciÃ³n de CachÃ© de Precios]
    C --> D[Arrastrar Ãtem a Venta]
    D --> E{Â¿Existen Datos?}
    E -- SÃ­ --> F[Sugerencia de Precio Trade-Tier]
    E -- No --> G[PeticiÃ³n de Escaneo Individual]
    F --> H[Posteo de Ãtem]
    G --> H
    H --> I[Registro de TransacciÃ³n en Historial]
    I --> J[Sync Visual con pfUI Skin]
```

## âš¡ Estrategias de IngenierÃ­a Diamond Tier

- **Asynchronous Indexing**: Los escaneos largos se fragmentan en micro-paquetes para que la interfaz de WoW no se congele durante el proceso.
- **Price Sanitization**: Se ignoran los valores atÃ­picos (outliers) en las subastas para evitar que el precio sugerido estÃ© distorsionado por el spam.
- **Low-Footprint DB**: La base de datos local de precios se guarda de forma estructurada para minimizar el tiempo de cierre y apertura de sesiÃ³n.

---
Â© 2026 **DarckRovert** â€” El SÃ©quito del Terror.
*Comercio inteligente para la conquista de Azeroth.*

