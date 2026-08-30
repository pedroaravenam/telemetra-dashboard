# Telemetra — dashboard web

Sitio publicado: **https://pedroaravenam.github.io/telemetra-dashboard/**

Este repo contiene **solo el build compilado** de `apps/web-dashboard`. El
codigo fuente vive en el repo `f1app`, que es privado — este existe unicamente
porque GitHub Pages no sirve sitios desde repos privados en el plan gratuito.

No editar a mano: todo lo de aca se regenera con
`flutter build web --release --base-href "/telemetra-dashboard/"`.

El dashboard pide login (Supabase Auth). La URL y la anon key de Supabase van
incluidas en el bundle a proposito: son publicas por diseno y los datos estan
protegidos por RLS a nivel de base de datos.
