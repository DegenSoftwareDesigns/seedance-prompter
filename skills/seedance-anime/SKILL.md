---
name: seedance-anime
description: This skill should be used when the user asks to "hacer un video estilo anime con Seedance", "quiero un video animado/manga", "dale un look de anime a esta escena", "video estilo cel-shading/2D animado", or wants a stylized Japanese-animation visual treatment for Seedance rather than photorealistic footage. Requires seedance-core to already be loaded for the shared prompt skeleton, camera vocabulary, and workflow.
version: 0.1.0
---

# Seedance Anime

Aportar la sensibilidad de animacion estilo anime sobre el esqueleto de `seedance-core`. Rellena estilo visual, luz, ritmo de plano y audio con convenciones de anime/manga animado.

## Cuando aplicarla

Escenas que deben leerse como animacion 2D japonesa, no como video realista: personajes con proporciones estilizadas, expresiones exageradas, action poses, o escenas contemplativas con estetica de anime de autor (Ghibli-like) segun lo que pida el usuario.

## Vocabulario de estilo visual (bloque 4)

- `anime style`, `cel-shaded`, `2D animation look`, `manga-inspired line art`.
- Sub-generos: `shonen action style` (lineas dinamicas, poses exageradas), `slice-of-life anime` (paleta suave, fondos pintados tipo Ghibli), `cyberpunk anime` (neones saturados, alto contraste).
- Evitar mezclar vocabulario fotorrealista (`shallow depth of field`, `film grain`) salvo que el usuario pida explicitamente un hibrido realista/anime.

## Luz / atmosfera (bloque 6)

Anime usa iluminacion mas plana y estilizada que el cine realista: `flat cel-shaded lighting`, `bold shadow shapes`, `saturated rim light`. Para escenas de accion, anadir `speed lines`, `motion blur streaks`, `dynamic impact frames`. Para escenas contemplativas, `soft painterly background light`, `warm ambient glow`.

## Ritmo de plano

Anime tolera tanto planos muy dinamicos (accion, combate) como planos estaticos prolongados (contemplacion, dialogo) con poco movimiento de camara pero mucho movimiento interno del personaje (pelo, ropa, particulas de ambiente). Camara tipica: `dramatic low angle for power poses`, `dutch angle for tension`, `fast whip pan between reaction shots`.

En multi-shot de reaccion (personaje habla, corte a otro personaje reaccionando), usar hard cut entre shots — es el patron estandar de edicion de anime dialogado.

## Audio (bloque 7)

SFX estilizados propios del genero: `sharp impact SFX`, `anime-style whoosh`, `dramatic sting on cut`. Musica: describir instrumentacion y mood en vez de "anime music" generico: `driving synth and taiko drums for action`, `soft piano and strings for emotional beat`.

## Ejemplo de aplicacion

```
Duration: 5s. Aspect ratio: 16:9.
A young warrior leaps into the air, sword raised overhead, hair and cloak whipping violently with the motion.
Rocky cliff battlefield, stormy sky with streaks of lightning in the distance.
Shonen action anime style, cel-shaded, bold dynamic line art, high contrast shadows.
Dramatic low angle, camera whip-pans upward following the leap, slight motion blur on the sword arc.
Flat stylized lighting with a cold blue rim light from the storm, speed lines trailing the movement.
Sharp sword-swing SFX, distant thunder, driving taiko drum hit on the peak of the leap.
```
