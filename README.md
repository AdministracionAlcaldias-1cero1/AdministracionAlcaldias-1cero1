
<p align="center">
  <span
    style="
      display:block;
      width:100%;
      max-width:1200px;
      aspect-ratio: 5 / 1;
      position:relative;
      overflow:hidden;
      border-radius:16px;
    "
  >
    <!-- Fondo: misma imagen, blur -->
    <img
      src="./assets/Gemini_Generated_Image_6tqpfo6tqpfo6tqp.png"
      alt=""
      style="
        position:absolute;
        inset:0;
        width:100%;
        height:100%;
        object-fit:cover;
        filter: blur(18px);
        transform: scale(1.12);
        opacity:0.95;
      "
    />
    <img
      src="./assets/Gemini_Generated_Image_6tqpfo6tqpfo6tqp.png"
      alt="Soporte, Desarrollo e Innovación — iCERO1"
      style="
        position:absolute;
        inset:0;
        margin:auto;
        width:25%;
        height:100%;
        object-fit:contain;
        filter:none;
      "
    />
  </span>
</p>
# 🚀 Integración Vue + SharePoint  
> **Objetivo ejecutivo:** desacoplar el **Front** del **Back** y dejar **SharePoint** en modo **gestor de archivos** (assets, versionado y permisos).  
> Traducción: menos “pegote” en páginas, más control del producto, y deploys sin sudor frío.

![Vue](https://img.shields.io/badge/Vue-Front%20Moderno-42b883?style=for-the-badge&logo=vuedotjs&logoColor=white)
![SharePoint](https://img.shields.io/badge/SharePoint-Assets%20%26%20Versionado-0078d4?style=for-the-badge&logo=microsoftsharepoint&logoColor=white)
![Architecture](https://img.shields.io/badge/Arquitectura-Desacoplada-8A5CFF?style=for-the-badge)
![Status](https://img.shields.io/badge/Plan-Listo%20para%20ejecutar-7CF7C5?style=for-the-badge)
---

## 🎯 Qué vamos a lograr (sin humo)
- **Vue** se vuelve la **capa de presentación**: UI/UX, componentes, rutas y estado.
- **SharePoint** se queda como **biblioteca corporativa**: aloja **JS/CSS**, imágenes, fuentes, y maneja **permisos + versionado**.
- El **Back / Datos** se consumen por **APIs** (SharePoint REST / Microsoft Graph / servicios existentes).

> [!TIP]
> SharePoint deja de ser “donde vive el front” y pasa a ser “donde viven los archivos”.  
> Vue deja de ser “un script más” y pasa a ser “el producto”.

---

## 🧠 La idea en una línea
**SharePoint = Storage + Governance** ✅  
**Vue = Experiencia + Velocidad** ⚡  
**Back/APIs = Datos + Reglas** 🛡️

---

## 🏗️ Arquitectura objetivo (como debe verse en el mundo real)
```mermaid
flowchart LR
  A[Vue App<br/>UI / Componentes / Rutas] --> B[SharePoint<br/>Gestor de Archivos<br/>JS/CSS/Imgs + Versionado]
  B --> C[Back / Datos<br/>APIs / Graph / REST]
  C --> A
