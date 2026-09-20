---
name: seedance-advertising
description: This skill should be used when the user asks to "crear un video publicitario con Seedance", "video de producto para anuncio", "quiero un spot de mi producto", "video estilo comercial/marca", "hero shot de producto", or wants a fast-paced, product- or brand-focused visual treatment for Seedance rather than a slow narrative or stylized-animation look. Requires seedance-core to already be loaded for the shared prompt skeleton, camera vocabulary, and workflow.
version: 0.1.0
---

# Seedance Advertising

Aportar la sensibilidad de publicidad/producto sobre el esqueleto de `seedance-core`. Rellena estilo visual, luz, ritmo de plano y restricciones globales tipicas de un spot o video de marca.

## Cuando aplicarla

Escenas centradas en un producto, un hero shot, un lifestyle shot con producto en contexto, o un video corto de marca donde el ritmo y el impacto visual priman sobre la narrativa profunda.

## Vocabulario de estilo visual (bloque 4)

- `clean studio look`, `high-key lighting`, `commercial gloss` para producto puro sobre fondo controlado.
- `lifestyle context`, `natural light`, `editorial commercial` cuando el producto aparece en uso real.
- Paletas vibrantes y saturadas por defecto, salvo que la marca pida lo contrario: `vibrant saturated palette`, `brand-accurate color grading`.

## Luz / atmosfera (bloque 6)

Producto puro: `soft even studio lighting`, `rim light to separate product from background`, `no harsh shadows` salvo que se pida un look dramatico. Lifestyle: luz natural motivada por la escena, igual que en cinematic pero con mas contraste y saturacion.

## Ritmo de plano

Publicidad tolera cortes mas rapidos y camara mas dinamica que el cine narrativo: `whip pan`, `quick push-in`, `orbit around product`, `macro close-up on texture/detail`. Planos individuales cortos (2-4s) quando es multi-shot.

Para un hero shot de producto, considerar una secuencia multi-shot con hard cut: plano general del producto en contexto, luego macro close-up de un detalle, sin transicion fluida entre ambos — ver logica de hard cut en `seedance-core`.

## Restricciones globales especificas de este estilo

Anadir salvo que el usuario pida lo contrario, para evitar artefactos que estropean un video de marca:

- `no on-screen text` (a menos que el usuario quiera texto de marca renderizado, lo cual Seedance no siempre reproduce fielmente — avisar de esto si lo piden)
- `no subtitles`
- Aspect ratio segun plataforma destino: `9:16` para redes verticales, `16:9` para YouTube/TV, `1:1` para feed cuadrado — preguntar si no se especifica.

## Audio (bloque 7)

SFX de producto (`crisp product interaction sound`, `subtle whoosh on transition`) mas musica energica si se pide, describiendo tempo/mood en vez de genero generico: `upbeat, driving rhythm, minimal percussion`.

## Ejemplo de aplicacion

```
Number of shots: 2. Duration: 6s total. Aspect ratio: 9:16. No on-screen text. No subtitles.

Shot 1: wide shot, a matte black perfume bottle sits centered on a reflective black surface, soft studio light from above, subtle steam drifting behind it. Hard cut.
Shot 2: macro close-up, slow orbit around the bottle's cap, light catching the glass edges, droplets of condensation visible.

Soft even studio lighting, rim light separating the product from the background, vibrant but controlled color grading.
Minimal ambient product-shot sound, subtle low synth swell building through the two shots.
```
