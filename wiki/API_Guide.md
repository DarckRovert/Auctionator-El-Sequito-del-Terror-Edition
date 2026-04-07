# 🛠️ Wiki: Guía de API — Efficient Trading (Auctionator)

Auctionator expone métodos para que otros AddOns del ecosistema **Séquito del Terror** puedan consultar precios de mercado en tiempo real.

## 📡 Funciones de Precios (Pricing API)

### `Auctionator_GetItemPrice(itemName)`
Consulta el precio de mercado actual registrado en la base de datos de Auctionator para un objeto específico.
- **`itemName`**: Nombre exacto del objeto.
- **Retorno**: Valor en cobre (gold/silver/copper converted).

### `Auctionator_ScanStart()`
Inicia un escaneo asíncrono de la subasta desde cualquier script externo.

## 📎 Integración con Ecosistema Gravity

- **Neural Economy**: **WCS_Brain** utiliza la API de precios de Auctionator para decidir si vale la pena comprar consumibles para la mascota basándose en el presupuesto del jugador.
- **Quest-Valuation**: pfQuest puede utilizar los precios de Auctionator para resaltar qué recompensas de misión tienen un mayor valor de reventa en la subasta.

---
© 2026 **DarckRovert** — El Séquito del Terror.
*Comercio inteligente para la conquista de Azeroth.*
