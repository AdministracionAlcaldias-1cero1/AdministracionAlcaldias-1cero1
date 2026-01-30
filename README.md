<p align="center">
  <img src="./assets/banner_1200x300.png" alt="Soporte, Desarrollo e Innovación — iCERO1" width="100%" />
</p>

# 🌐 Panel Administrativo — Portales Institucionales (Portales Lite)

## ✨ iCERO1 presenta: el panel que sí se siente como producto
Había una época (todos la vivimos) donde administrar un portal era como jugar *Jenga* con guantes:  
mueves una cosa… y te tiemblan otras tres. 😅

Entonces llegó **iCERO1** con una idea simple y poderosa:  
hacer que el panel administrativo sea **rápido**, **claro** y **amable** con el día a día —  
sin sacrificar gobernanza, permisos ni control corporativo.

### 🚀 ¿Qué cambió?
En esta nueva etapa, cada pieza hace lo que mejor sabe hacer:

- 🧩 **Vue** se encarga de la **experiencia**: interfaz moderna, navegación fluida, respuesta inmediata y consistencia visual.
- 🗂️ **SharePoint** se queda como el **gestor de archivos con gobierno**: assets con versionado, permisos y orden institucional.

### 🧠 ¿Y la experiencia cómo se siente?
- ⚡ **Fluidez real**: el panel se mueve como app, no como “página que piensa mucho”.
- 📲 **Multidispositivo sin drama**: en escritorio, tablet o móvil todo mantiene lógica, tamaño y claridad.
- 🧭 **Orientación constante**: siempre sabes dónde estás y qué toca hacer (sin perderte en laberintos).
- 🛡️ **Tranquilidad operativa**: cambios con control, con rastro, con estructura. Menos sustos, más confianza.

> **Resultado:** menos fricción, más velocidad; menos “¿por qué no cargó?”, más “listo, siguiente”. ✅

---

## 🏗️ Arquitectura final (la verdad detrás del telón)
```mermaid
flowchart LR
  A[Vue App<br/>UI / Componentes / Rutas] --> B[SharePoint<br/>Gestor de Archivos<br/>JS/CSS/Imgs + Versionado]
  B --> C[Back / Datos<br/>APIs / Graph / REST]
  C --> A
