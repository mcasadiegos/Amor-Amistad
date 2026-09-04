# Velada en la Bahía

Invitación web animada a la **Cena Empresarial de Amor y Amistad** de la
Agencia de Aduanas ASCOINTER S.A.S.

- **Fecha:** viernes 18 de septiembre de 2026, 5:00 p. m.
- **Lugar:** Restaurante Bahía Club — Manga, Cuarta Avenida #18 B-29, Cartagena de Indias
- **Código de vestimenta:** rojo y blanco

## El archivo

Todo vive en [`invitacion.html`](invitacion.html): un único archivo autónomo,
sin dependencias ni proceso de compilación. Se abre con doble clic en cualquier
navegador moderno. El logo de Ascointer va incrustado como `data:` URI, así que
la página funciona también sin conexión.

La única petición externa es la hoja de estilos de Google Fonts
(Bodoni Moda, Parisienne y Jost). Sin ella la página se ve igual de bien con
las tipografías de reserva.

## Cómo está hecha

| Pieza | Cómo funciona |
|---|---|
| **El sobre** | El sello de lacre se parte en dos mitades con `clip-path` irregular, la solapa gira en 3D (`rotateX` sobre un contenedor con `perspective`) y la carta sale del bolsillo. |
| **La escritura** | Un solo guion en orden de documento reparte el texto en palabras y letras, y las revela de arriba a abajo. La pluma sigue al lector: espera cuando el siguiente bloque está bajo el borde de la pantalla y alcanza el retraso si se adelanta. |
| **Ambiente** | Brasas rojas dibujadas en `<canvas>` con degradados radiales en modo `lighter`, más globos y corazones SVG desenfocados que suben en bucle. |
| **Cuenta regresiva** | Calculada contra `2026-09-18T17:00:00-05:00`; al llegar la fecha cambia sola a «¡Hoy es la noche!». |

### Movimiento reducido

Con `prefers-reduced-motion: reduce` se apaga solo el movimiento continuo de
fondo (brasas, globos y el latido del sello). La apertura del sobre y la
escritura se conservan: ocurren una sola vez y las inicia la persona con un
clic, así que son contenido y no decoración.

El botón **Ver otra vez** al pie rebobina la secuencia completa sin recargar.

---

Creado por: **Maycol Casadiegos**
