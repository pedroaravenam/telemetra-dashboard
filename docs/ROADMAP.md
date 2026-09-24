# Roadmap — telemetra-dashboard

## Fase actual: Despliegue de builds compilados y validaciones de telemetría
- [x] Build inicial y configuración de GitHub Pages para `apps/web-dashboard`
- [x] Soporte multi-idioma (español, portugués, inglés) y componentes de `ui_kit`
- [x] Comparación de vueltas, delta acumulado y visualización de condiciones climáticas
- [x] Leaderboard por circuito con opt-in
- [x] Página de validaciones pendientes contra el juego (`validaciones/index.html`)
- [ ] Integrar nuevo build compilado con soporte corregido para paquetes UDP F1 2026 (Car Status, Car Damage, Participants)
- [ ] Validar visualización completa de telemetría en sesiones largas (carrera 25%+)

## Próximas fases
### Automatización del flujo de entrega
- Automatizar la exportación y sincronización de artefactos compilados desde el repositorio privado `f1app` hacia este repositorio.
- Incorporar comprobaciones de integridad del bundle web previo al despliegue.

### Consolidación de métricas y validaciones en pista
- Actualizar `validaciones/index.html` con datos de pruebas en simulador/juego real.
- Incorporar visualizaciones de nuevas métricas validadas contra telemetría real.

## Ideas sin compromiso
- Modo offline / PWA con persistencia local de vueltas consultadas.
- Exportación de telemetría de vueltas en formatos abiertos (CSV / JSON).
