<p align="center">
  <img src="./assets/banner_1200x300.png" alt="Soporte, Desarrollo e Innovación — iCERO1" width="100%">
</p>

# Panel Administrativo — Portales Institucionales

Bienvenido al **centro de control** de los portales institucionales. Este panel está pensado para que la gestión diaria sea **ágil, predecible y sin fricción**: menos “recargar para ver si sí”, más “clic y listo”.

La nueva dinámica es simple (y rentable en paz mental):
- **SharePoint** opera como **gestor corporativo de archivos**: un repositorio gobernado para **assets** (JS/CSS, imágenes, fuentes) con **versionado y permisos** que juegan en equipo.
- **Vue** es la **experiencia de usuario** del panel: navegación fluida tipo app, interacción inmediata, y una interfaz consistente que se adapta sin drama a escritorio, tablet y móvil.

## Qué vas a sentir en la operación
- **Fluidez**: moverte entre secciones se siente como una aplicación, no como una maratón de recargas.
- **Respuesta rápida**: acciones con feedback claro (el sistema “responde”, no “piensa en voz alta”).
- **Consistencia en cualquier dispositivo**: el panel mantiene la misma lógica y comodidad en pantallas grandes o táctiles.
- **Satisfacción operativa**: cambios más controlados, menos sorpresas; el versionado y permisos ponen orden donde antes había “fe”.

```mermaid
flowchart LR
  A[Vue App<br/>UI / Componentes / Rutas] --> B[SharePoint<br/>Gestor de Archivos<br/>JS/CSS/Imgs + Versionado]
  B --> C[Back / Datos<br/>APIs / Graph / REST]
  C --> A
