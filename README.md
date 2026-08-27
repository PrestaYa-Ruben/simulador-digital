# Simulador de Crédito — PrestaYa

Simulador de crédito y formulario de solicitud (HTML + Tailwind CDN + JS vanilla, un solo archivo, sin dependencias de build). Incluye 3 perfiles configurables y envío de la solicitud por WhatsApp.

## Cómo subirlo a tu repositorio (GitHub Pages)

1. En tu repositorio, crea una carpeta — por ejemplo `simulador/`.
2. Sube el archivo `index.html` (de esta misma carpeta) dentro de esa carpeta del repo.
3. Haz commit y push.
4. Si GitHub Pages ya está activado en el repositorio, el simulador queda disponible en:

   ```
   https://<usuario>.github.io/<repositorio>/simulador/
   ```

   Reemplaza `<usuario>` y `<repositorio>` por los tuyos.

No necesita ningún paso de instalación ni build — es HTML plano, funciona apenas GitHub Pages lo sirve.

## Los 3 perfiles

Se activan agregando `?perfil=` al final del link. Si no se indica, o el valor no es válido, se usa **estandar** por defecto.

| Perfil | Parámetro en la URL | Monto máx. | Cuotas máx. | Datos personales que pide |
|---|---|---|---|---|
| Cliente nuevo | `?perfil=nuevo` | $400.000 | 8 | Completo (Nombre, Cédula, Celular, Dirección, Barrio, Ciudad) |
| Estándar | `?perfil=estandar` | $1.000.000 | 10 | Reducido (Nombre, Cédula, Celular, Dirección) |
| Monto alto | `?perfil=alto` | $2.500.000 | 10 | Reducido (igual que estándar) |

En todos los perfiles se mantienen las secciones de Información laboral (Ocupación + Empresa o lugar de trabajo) y Recomendado@ por.

### Ejemplo de links finales

```
https://tuusuario.github.io/turepo/simulador/?perfil=nuevo
https://tuusuario.github.io/turepo/simulador/?perfil=estandar
https://tuusuario.github.io/turepo/simulador/?perfil=alto
```

## Qué se puede editar dentro del archivo

Todo está en el bloque `<script>` al final de `index.html`:

- **`CONFIG.whatsappNumber`** — número de WhatsApp al que llega la solicitud.
- **`CONFIG.tasaMensual`** — tasa de interés fija por mes (hoy 10%).
- **`CONFIG.cuotasPorMes`** — cuántas cuotas equivalen a 1 mes, por frecuencia (semanal: 4, quincenal: 2).
- **`PROFILES`** — monto máximo, cuotas máximas y si pide Barrio/Ciudad, para cada uno de los 3 perfiles.
