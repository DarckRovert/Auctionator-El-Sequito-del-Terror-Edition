# Arquitectura — Auctionator Sequito 🏗️

mermaid
graph TD
    CORE[Auctionator Core]
    EVENT[AH Event Listener]
    SELL[Sell Interface]
    PRICE[Price Database]
    UI[AH Tabs]

    EVENT --> CORE
    CORE --> PRICE
    PRICE --> SELL
    CORE --> UI


## Componentes
- **Auctionator.lua**: Lógica de gestión de datos, escaneo y comunicación con el ecosistema.
- **Auctionator.xml**: Definición de elementos de la interfaz personalizada (Frames, Buttons).
- **LAST_DEPLOY.txt**: Registro de despliegue para el control de versiones del clan.
