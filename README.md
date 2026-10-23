# Departamento en Mar del Plata: disponibilidad y tarifas

Página estática con calendario de disponibilidad y cotizador. Funciona en GitHub Pages, sin servidor.

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `index.html` | La página. Al principio tiene el bloque `CONFIG` con precios, fechas especiales, feriados, textos, horarios y WhatsApp. |
| `reservas.js` | Fechas reservadas. Es el archivo que vas a actualizar seguido. |

## Publicar en GitHub Pages (una sola vez)

1. Creá un repositorio nuevo en GitHub (por ejemplo `depto-mdp`).
2. Tocá **Add file → Upload files**, arrastrá los dos archivos (`index.html` y `reservas.js`), sueltos y no la carpeta, y tocá **Commit changes**.
3. Andá a **Settings → Pages**. En *Source* elegí **Deploy from a branch**, branch `main` y carpeta `/ (root)`. Guardá.
4. Esperá uno o dos minutos. La página queda en `https://TU-USUARIO.github.io/depto-mdp/`.

## Cargar reservas

**Opción A: desde la página**
1. Abrí `https://TU-USUARIO.github.io/depto-mdp/?admin`.
2. Elegí la entrada y la salida en el calendario y tocá **Marcar estas fechas como reservadas**.
3. Tocá **Descargar reservas.js**.
4. En GitHub, subí ese archivo con **Add file → Upload files** (reemplaza al anterior) y tocá **Commit changes**.

**Opción B: a mano**
Abrí `reservas.js` en GitHub, tocá el lápiz y agregá una línea por reserva:
```js
{ entrada: "2026-12-26", salida: "2027-01-02" },
```

La salida queda libre para que otro huésped entre ese mismo día a las 14 h.

> **Importante:** el repositorio es público. En `reservas.js` cargá solo fechas, nunca nombres, teléfonos ni otros datos de huéspedes.

## Cómo se calcula la tarifa

Cada noche se cotiza por separado y después se suma todo:

1. **Fechas especiales** (siempre): 19 al 21/11, 23 al 31/12, viernes y sábados desde el 16/1, y 1 al 8/2.
2. **Estadías largas y días de semana:**
   - Noviembre: más de 7 noches, o noches de lunes a jueves sin feriado.
   - Diciembre: solo del 1 al 15, con más de 7 noches o de lunes a jueves.
   - Enero: solo para reservas de 15 noches o más.
   - Febrero: solo del 16 en adelante, con más de 7 noches o de lunes a jueves.
3. **Tarifa general:** todo lo demás.

Todo esto se cambia en el bloque `CONFIG` al principio de `index.html` (en GitHub: abrís el archivo y tocás el lápiz).

## Probar en la compu

Descomprimí el zip primero y abrí `index.html` desde la carpeta descomprimida. Si lo abrís desde adentro del zip, no encuentra `reservas.js`.
