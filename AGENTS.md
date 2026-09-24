# telemetra-dashboard

Las reglas globales (cierre de avance, producción, estructura documental, modelos, secretos) están en `~/.codex/AGENTS.md` y aplican aquí. Este archivo tiene solo lo propio del proyecto (≤120 líneas).

## Proyecto
Telemetra Dashboard es la interfaz web compilada de telemetría de carreras para F1 (Telemetra Racing). Permite a pilotos y equipos analizar setups, tiempos por vuelta, telemetría detallada, combustible/ERS, desgaste de neumáticos y comparar vueltas en español, portugués e inglés. Este repositorio contiene exclusivamente los artefactos compilados para su distribución estática en GitHub Pages; el código fuente Flutter/Dart se desarrolla en el repositorio privado `f1app` (`apps/web-dashboard`).

## Leer primero
- `STATUS.md` (snapshot corto del estado actual).
- `README.md` (contexto del build compilado y autenticación con Supabase).
- `validaciones/index.html` (documentación interna de validaciones pendientes contra el juego).
- `docs/history/HISTORIAL.md` solo con búsqueda, nunca completo.

## Comandos
| Para qué | Comando |
|---|---|
| Instalar | N/A (repositorio de artefactos estáticos compilados) |
| Verificar (lint, tipos, tests) | `test -f index.html && test -f main.dart.js` |
| Ejecutar en local | `python3 -m http.server 8080` |

> Nota: La compilación del código fuente se realiza en el repositorio privado `f1app` mediante `flutter build web --release --base-href "/telemetra-dashboard/"`.

## Publicar
- Destino: https://pedroaravenam.github.io/telemetra-dashboard/
- Tipo: estático
- Comando: `git push origin main` (GitHub Pages sirve directamente la raíz de la rama `main`)

## Reglas propias
- Este repositorio contiene únicamente los archivos compilados generados desde `f1app`. No editar manualmente archivos `.js`, `.html` ni assets en este repo; cualquier modificación de código debe hacerse en el repositorio fuente `f1app`.
- La URL y anon key de Supabase están incluidas deliberadamente en el bundle compilado ya que son públicas por diseño; la seguridad y control de acceso se gestionan mediante políticas RLS en la base de datos.
