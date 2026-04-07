# Contributing to Auctionator (Efficient Trading) 📊💰

¡Gracias por contribuir a la economía del **Séquito del Terror**! Para mantener el estándar **Diamond Tier** de **DarckRovert**, todas las contribuciones deben priorizar la velocidad de respuesta de la subasta y la integridad de los datos de precios.

---

## 🛡️ Estándares Técnicos (Trading Core)

Este AddOn está optimizado para **Turtle WoW** (WoW v1.12.1). Las contribuciones DEBEN cumplir con:

1.  **Scan Efficiency**: No introduzcas funciones que bloqueen el hilo principal durante el escaneo masivo de la subasta. Usa micro-latencias para mantener la estabilidad del GUI.
2.  **No Lua 5.1+**: El motor es Lua 5.0. Prohibido el operador `#` (usa `table.getn`).
3.  **Database Compression**: Los datos de precios almacenados en `SavedVariables` deben ser compactos. Evita redundancias en el guardado de materiales pesados.
4.  **UI Harmony**: Cualquier nueva pestaña de comercio debe integrarse visualmente con el perfil Apex-Tier (pfUI).

## 📐 Arquetipo de Desarrollo

Si deseas contribuir:
- **`Auctionator.lua`**: Es el motor central de escaneo y cálculo de precios. Requiere validación estricta de rendimiento.
- **`Auctionator.xml`**: Definición de la interfaz de usuario. Mantén el minimalismo característico.
- **`SavedVariables`**: Gestión de perfiles de usuario y bases de datos locales de precios.

## 💎 Proceso de Pull Request

1.  **Fork & Branch**: Trabaja en ramas descriptivas (`fix/scan-latency`, `feature/sell-optimizer`).
2.  **Documentación**: Actualiza `CHANGELOG.md` antes de enviar el PR.
3.  **Branding**: Mantén los enlaces institucionales oficiales de **DarckRovert**.

---
© 2026 **DarckRovert** — El Séquito del Terror.
*Comercio inteligente para la conquista de Azeroth.*
