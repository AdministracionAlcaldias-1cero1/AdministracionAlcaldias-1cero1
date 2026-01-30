<!--
INTEGRACIÓN VUE + SHAREPOINT (Front desacoplado / SharePoint como gestor de archivos)
Nota: Este MD incluye HTML/CSS/JS embebido para “modo exótico”.
- En renderizadores tipo GitHub, parte del CSS/JS puede bloquearse.
- En SharePoint (páginas modernas con webparts/HTML permitido) o renderizadores MD “libres”, se ve completo.
-->

<div class="vx-hero">
  <div class="vx-hero__bg"></div>
  <div class="vx-hero__noise"></div>

  <div class="vx-hero__content vx-reveal">
    <div class="vx-badges">
      <span class="vx-badge">Vue</span>
      <span class="vx-badge">SharePoint</span>
      <span class="vx-badge">Front ≠ Back</span>
      <span class="vx-badge vx-badge--pulse">Integración</span>
    </div>

    <h1 class="vx-title">
      Integración <span class="vx-accent">Vue</span> + <span class="vx-accent">SharePoint</span>
      <br />
      <span class="vx-subtitle">SharePoint como gestor de archivos. Vue como experiencia de usuario.</span>
    </h1>

    <p class="vx-lead">
      Objetivo: <b>separar front del back</b> para ganar velocidad, mantenibilidad y escalabilidad.
      En términos corporativos: <i>“desacoplamos la capa de presentación”</i> y dejamos SharePoint haciendo lo que mejor sabe:
      <b>almacenar, versionar y servir assets</b>.  
      Resultado: un stack más limpio y un roadmap con menos drama.
    </p>

    <div class="vx-actions">
      <a class="vx-btn vx-btn--primary" href="#arquitectura">Ver arquitectura</a>
      <a class="vx-btn" href="#pipeline">Ver pipeline</a>
      <a class="vx-btn vx-btn--ghost" href="#checklist">Checklist</a>
    </div>

    <div class="vx-metrics vx-reveal">
      <div class="vx-metric">
        <div class="vx-metric__kpi">↓</div>
        <div class="vx-metric__txt"><b>Menos acoplamiento</b><br/>Más control del front</div>
      </div>
      <div class="vx-metric">
        <div class="vx-metric__kpi">⚡</div>
        <div class="vx-metric__txt"><b>UX más rápida</b><br/>Build optimizado</div>
      </div>
      <div class="vx-metric">
        <div class="vx-metric__kpi">🧩</div>
        <div class="vx-metric__txt"><b>Componentización</b><br/>Vue modular</div>
      </div>
      <div class="vx-metric">
        <div class="vx-metric__kpi">🗂️</div>
        <div class="vx-metric__txt"><b>SharePoint ordenado</b><br/>Assets versionados</div>
      </div>
    </div>
  </div>

  <div class="vx-orbit" aria-hidden="true">
    <div class="vx-orbit__ring"></div>
    <div class="vx-orbit__ring vx-orbit__ring--two"></div>
    <div class="vx-orbit__dot vx-orbit__dot--a"></div>
    <div class="vx-orbit__dot vx-orbit__dot--b"></div>
    <div class="vx-orbit__dot vx-orbit__dot--c"></div>
  </div>
</div>

---

## TL;DR (para directivos con agenda apretada)
- Vue se encarga del **Front (UI/UX)**: SPA o micro-front embebible.
- SharePoint queda como **gestor de archivos**: `SiteAssets/`, `PublishingImages/`, librerías, versionado, permisos.
- Datos/negocio: vía **APIs** (SharePoint REST / Microsoft Graph / servicios externos).
- Beneficio: **desacople**, **mejor rendimiento**, **deploys más previsibles**, **menos “magia negra” en páginas**.

---

## Arquitectura
<div class="vx-grid vx-reveal" id="arquitectura">
  <div class="vx-card">
    <h3>🧠 Antes (monolito emocional)</h3>
    <ul>
      <li>UI mezclada con lógica y dependencias de SharePoint.</li>
      <li>Scripts sueltos en páginas: “funciona en mi máquina”.</li>
      <li>Actualizaciones con alto riesgo y bajo control.</li>
    </ul>
    <div class="vx-diagram">
      <div class="vx-pill">Página SP</div>
      <div class="vx-arrow">→</div>
      <div class="vx-pill">JS/CSS disperso</div>
      <div class="vx-arrow">→</div>
      <div class="vx-pill vx-pill--warn">Cambios frágiles</div>
    </div>
  </div>

  <div class="vx-card vx-card--glow">
    <h3>🚀 Después (arquitectura con KPI felices)</h3>
    <ul>
      <li>Vue como capa de presentación, compilada y optimizada.</li>
      <li>SharePoint sirve assets: <code>.js</code>, <code>.css</code>, imágenes, fuentes.</li>
      <li>Back y datos por endpoints: REST/Graph/servicios.</li>
    </ul>
    <div class="vx-diagram">
      <div class="vx-pill vx-pill--ok">Vue App (dist)</div>
      <div class="vx-arrow">→</div>
      <div class="vx-pill">SharePoint (assets)</div>
      <div class="vx-arrow">→</div>
      <div class="vx-pill vx-pill--ok">APIs / Datos</div>
    </div>
  </div>
</div>

---

## Flujo de integración (operación “desacople elegante”)
<div class="vx-timeline vx-reveal">
  <div class="vx-step">
    <div class="vx-step__n">1</div>
    <div class="vx-step__b">
      <h4>Build de Vue</h4>
      <p>Se genera <code>dist/</code> con bundles minificados, hashing y assets listos para producción.</p>
    </div>
  </div>

  <div class="vx-step">
    <div class="vx-step__n">2</div>
    <div class="vx-step__b">
      <h4>Publicación en SharePoint</h4>
      <p>Se sube <code>dist/assets</code> a <code>/SiteAssets/</code> (o librería dedicada). SharePoint versiona y controla permisos.</p>
    </div>
  </div>

  <div class="vx-step">
    <div class="vx-step__n">3</div>
    <div class="vx-step__b">
      <h4>Bootstrap en la página</h4>
      <p>La página de SharePoint solo carga el bundle principal y monta el app en un <code>&lt;div id="app"&gt;</code>.</p>
    </div>
  </div>

  <div class="vx-step">
    <div class="vx-step__n">4</div>
    <div class="vx-step__b">
      <h4>Consumo de datos</h4>
      <p>Vue consume datos vía REST/Graph. SharePoint queda como “CDN corporativo con corbata”.</p>
    </div>
  </div>
</div>

---

## Estructura recomendada (SharePoint como biblioteca de assets)
```txt
/ SiteAssets
  / app-vue
    / v1.0.0
      / assets
        app.[hash].js
        vendor.[hash].js
        styles.[hash].css
        images/
        fonts/
      index-bootstrap.html (opcional)
    / current -> apunta a la versión estable (convención)
/ PublishingImages (si aplica)
