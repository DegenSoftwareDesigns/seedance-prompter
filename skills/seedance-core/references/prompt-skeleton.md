# Plantilla de prompt Seedance 2.5

## Plantilla anotada (single continuous shot)

```
[GLOBAL, opcional] Duration: Ns. Aspect ratio: X:Y. [restricciones globales]
[SUJETO + ACCION] Who/what, physical description, what they are doing, direction of movement.
[ESCENA] Where, when, context.
[ESTILO VISUAL] Aporta la skill de estilo hija.
[CAMARA] Angle + movement + framing, describing how the shot evolves over its full length.
[LUZ / FISICAS / ATMOSFERA] Lighting type and direction, color grading, secondary motion (hair, cloth, smoke, particles).
[AUDIO, opcional] Dialogue, ambient sound, SFX, music, or explicit silence.
```

## Plantilla anotada (multi-shot, hard cut / coverage)

Usar cuando el sujeto permanece estatico y solo cambia el angulo de camara (no hay desplazamiento del sujeto ni movimiento de camara continuo entre planos).

```
[GLOBAL] Number of shots: N. Duration: Ns total. Aspect ratio: X:Y. [restricciones globales]

Shot 1: [encuadre] [angulo], [sujeto + accion, mismo instante], [luz/estilo]. Hard cut.
Shot 2: [encuadre distinto] [angulo distinto], [misma accion, continuidad de detalle - ej. mismo punto del cigarro], [luz/estilo]. Hard cut.
Shot 3: [encuadre distinto] [angulo distinto], [cierre de la escena].
```

Reglas para este modo:
- Especificar framing y distancia de camara en cada shot — la ambiguedad aqui es la causa mas comun de perder consistencia entre planos.
- Mantener continuidad de detalle entre shots (mismo punto de la accion, misma posicion de objetos) ya que el sujeto no se mueve.
- Cerrar cada shot con "Hard cut." en vez de nombrar una transicion fluida (match cut, whip pan) — eso le pide al modelo una transicion animada que aqui no se quiere.
- El ultimo shot de la secuencia no necesita "Hard cut." al final si es el cierre del clip.

## Plantilla anotada (multi-shot, movimiento narrativo)

Usar cuando hay progresion de accion o desplazamiento del sujeto entre planos.

```
[GLOBAL] Number of shots: N. Duration: Ns total. Aspect ratio: X:Y.

Shot 1 (0-Ns): [sujeto + accion], [camara: angulo + movimiento], [escena/luz].
Shot 2 (Ns-Ms): [continuacion de accion o nueva accion], [camara], [transicion desde shot 1: match cut / continuous / smash cut].
```

## Ejemplo completo — single shot

```
Duration: 8s. Aspect ratio: 16:9.
A woman in a rain-soaked trench coat walks briskly across a neon-lit street, checking over her shoulder.
Downtown alley at night, wet asphalt reflecting pink and blue signage.
Gritty neo-noir style, high contrast, desaturated except for neon accents.
Low angle tracking shot, camera moves alongside her at hip height, slight handheld shake.
Hard directional light from neon signs, rim light on her silhouette, steam rising from a street vent.
Ambient city noise, distant traffic, her footsteps on wet pavement.
```

## Ejemplo completo — multi-shot hard cut (coverage estatico)

```
Number of shots: 3. Duration: 9s total. Aspect ratio: 2.39:1.

Shot 1: medium shot, eye-level, a man leans on a balcony railing smoking, city lights blurred behind him, cigarette half-consumed, exhaling slowly. Warm interior light spilling from behind. Hard cut.
Shot 2: low-angle close-up, same instant, same cigarette length, smoke curling upward past his jaw, distant contemplative expression. Hard cut.
Shot 3: wide shot from inside the room looking out through the balcony door, his silhouette framed against the city skyline, motionless.
```

## Checklist antes de entregar

- [ ] Sujeto y accion estan en las primeras 20-30 palabras.
- [ ] Camara nunca va antes que sujeto+accion.
- [ ] Si hay mas de un shot, cada uno especifica framing y angulo propio.
- [ ] Si el sujeto no se mueve entre shots, se uso "Hard cut" y no una transicion fluida.
- [ ] Idioma final: ingles.
- [ ] Sin markdown ni comentarios dentro del bloque de prompt.
