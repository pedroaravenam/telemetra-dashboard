# STATUS — telemetra-dashboard

> Snapshot del estado actual, ≤120 líneas. El detalle histórico va en `docs/history/HISTORIAL.md` y los planes largos en `docs/ROADMAP.md`.

## Resumen
- Fecha: 2026-09-23
- Último commit: `e015075` — Fix de lectura de clima en dashboard
- ¿Publicado?: Sí, en https://pedroaravenam.github.io/telemetra-dashboard/

## Entorno
- Destino público: https://pedroaravenam.github.io/telemetra-dashboard/ (GitHub Pages, hosting estático desde rama `main`).
- Página de validaciones: https://pedroaravenam.github.io/telemetra-dashboard/validaciones/ (documentación interna de pruebas contra el juego).
- Origen del build: Artefactos compilados de `apps/web-dashboard` en el repositorio privado `f1app`.
- Backend y autenticación: Supabase Auth (URL y anon key públicas incluidas en el bundle compilado; protección de datos mediante RLS).

## Próximo paso exacto
Al recibir cambios o correcciones desde el repositorio privado `f1app`, ejecutar `flutter build web --release --base-href "/telemetra-dashboard/"`, copiar los archivos compilados a la raíz de este repositorio y hacer push a `main`.

## Pendientes priorizados
1. Sincronizar nuevo build compilado cuando se actualice `apps/web-dashboard` en `f1app`.
2. Validar en el dashboard web la visualización de Car Status (combustible y ERS) tras captura de paquetes UDP 2026.
3. Validar en el dashboard web el desgaste de neumáticos (Car Damage) tras ajuste de guards en el parser.
4. Validar visualización de piloto y equipo con formato UDP 2026 (`teamId` de 2 bytes).
5. Validar renderizado de sesiones largas (carrera de 25%+ de distancia).
6. Mantener actualizada la página de validaciones internas (`validaciones/index.html`) con nuevos resultados de prueba en pista.

## Riesgos activos
- Desincronización por edición manual en este repo: Modificar archivos JS o HTML compilados directamente se perderá en la siguiente compilación desde `f1app` — mitigación: nunca editar código a mano aquí; regenerar siempre desde `f1app`.
- Guards de tamaño en paquetes UDP F1 2026 descartan datagramas silenciosamente si cambian las specs de EA — mitigación: capturar tráfico UDP crudo en pruebas antes de actualizar el parser en `f1app`.

## Enlaces
- `docs/ROADMAP.md`
- `docs/history/HISTORIAL.md`
