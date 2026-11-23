# Lector de dorsales de Tu Enfoque

Lee los números de dorsal y las caras de las fotos de cada carrera, para que los corredores
encuentren sus fotos en www.tuenfoquee.com. Corre solo en GitHub Actions cada 30 minutos:

1. Le pide a la web que importe las fotos nuevas de Drive (vista con marca de agua).
2. Descarga de Drive las fotos aún sin leer, lee dorsales y caras, y le manda a la web el resultado.
3. Termina cuando no queda nada; lo que no alcance en 5 horas lo sigue la próxima vuelta.

Para que empiece al momento tras subir una carrera: pestaña **Actions** → **Lector de dorsales** → **Run workflow**.

Secretos (Settings → Secrets and variables → Actions): `LECTOR_SITIO` (la dirección de la web)
`LECTOR_CLAVE` (la clave de sincronizar, igual a `CRON_SECRET` en Vercel) y, opcional,
`NVIDIA_API_KEY`: un modelo de visión de NVIDIA da una segunda lectura de dorsales; los que solo
él ve se guardan cuando un segundo vistazo ampliado lo confirma. Este repositorio no
guarda claves ni fotos.

`lector.mjs` se genera desde el proyecto de la web con `npm run lector:build`.
