<p align="center">
  <img src="./assets/banner_1200x300.png" alt="Soporte, Desarrollo e Innovación — iCERO1" width="100%" />
</p>

# 🏛️ Panel Administrativo — Portales Institucionales

Bienvenidos al **nuevo sistema de administración de portales institucionales**, proporcionado por **iCERO1**.  
Este panel está diseñado para una operación **más ágil, estable y consistente** en cualquier entorno (PC, tablet o móvil), reduciendo tiempos de carga y mejorando la respuesta en tareas diarias.

## ✅ Nueva mecánica de trabajo
- 🗂️ **SharePoint** funciona como **gestor de archivos**: assets (JS/CSS, imágenes, fuentes) con **versionado** y **permisos**.
- 🧩 **Vue** es la **experiencia de usuario**: navegación fluida, interfaz moderna y una interacción más rápida (sin recargas innecesarias).

## 🎯 Qué puedes esperar
- ⚡ **Mayor fluidez** en la navegación y uso del panel.
- 📲 **Adaptación real** a diferentes dispositivos y tamaños de pantalla.
- 🔒 **Control y gobernanza** sobre los archivos (permisos + versiones).
- 🧠 **Interfaz clara** para operar con menos fricción y más precisión.

```mermaid
flowchart LR
  A[Vue App<br/>UI / Componentes / Rutas] --> B[SharePoint<br/>Gestor de Archivos<br/>JS/CSS/Imgs + Versionado]
  B --> C[Back / Datos<br/>APIs / Graph / REST]
  C --> A
