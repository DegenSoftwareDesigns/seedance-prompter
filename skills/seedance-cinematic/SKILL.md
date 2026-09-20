---
name: seedance-cinematic
description: This skill should be used when the user asks to "hacer un video cinematografico con Seedance", "quiero un plano tipo pelicula", "dale un look de cine a este prompt", "video narrativo dramatico", "estilo neo-noir/thriller/drama para Seedance", or wants a narrative, film-like visual treatment (dramatic lighting, shallow depth of field, deliberate pacing) rather than a fast commercial or stylized-animation look. Requires seedance-core to already be loaded for the shared prompt skeleton, camera vocabulary, and workflow.
version: 0.1.0
---

# Seedance Cinematic

Aportar la sensibilidad de cine narrativo sobre el esqueleto de `seedance-core`. Esta skill no redefine estructura ni idioma — solo rellena los bloques de estilo visual, luz/atmosfera, ritmo de plano y audio con convenciones de cine dramatico.

## Cuando aplicarla

Escenas donde el objetivo es contar algo con peso emocional: un personaje reflexionando, una confrontacion, un momento de tension o intimidad. Prioriza composicion y atmosfera sobre ritmo rapido o texto de marca.

## Vocabulario de estilo visual (bloque 4)

- `neo-noir`, `gritty realism`, `period drama`, `psychological thriller` segun el tono pedido.
- `shallow depth of field`, `anamorphic lens flare`, `film grain`, `35mm look`.
- Paletas: `desaturated with isolated color accents`, `warm practical lighting`, `cool moonlit tones`.

## Luz / atmosfera (bloque 6)

Preferir fuentes de luz motivadas por la escena (practicals: lamparas, neones, ventanas) sobre luz generica. Contraste alto para drama, contraste bajo y luz difusa para intimismo. Especificar direccion: `rim light`, `hard directional light from [fuente]`, `soft window light`.

## Ritmo de plano

Cine narrativo tolera planos mas largos y movimientos de camara lentos y deliberados: `slow push-in`, `static hold`, `slow tracking shot`. Evitar cortes rapidos salvo que la escena sea de accion — en ese caso, usar `whip pan` o `smash cut` puntualmente para impacto, no como default.

Para escenas de personaje quieto/reflexivo cubierto desde varios angulos (ver logica de hard cut en `seedance-core`), este estilo favorece encuadres intimos: alternar `medium shot` y `close-up`, evitar `wide shot` salvo como plano de cierre.

## Audio (bloque 7)

Sonido ambiente diegetico prioritario sobre musica: `distant traffic`, `rain on glass`, `room tone`. Musica solo si el usuario la pide explicitamente, y entonces describir instrumentacion y no solo genero: `sparse piano`, `low string drone` en vez de "sad music".

## Ejemplo de aplicacion

```
Duration: 6s. Aspect ratio: 2.39:1.
A man stands motionless on a rain-streaked balcony, cigarette smoke curling past his face as he stares at the city skyline, lost in thought.
High-rise balcony at night, city lights blurred and soft-focus behind him.
Neo-noir style, shallow depth of field, desaturated palette with warm amber window light as the only color accent.
Static medium shot at eye level, slow almost imperceptible push-in over the full duration.
Warm practical light spilling from behind him, rim light along his shoulder, smoke lit from below by neon glow.
Distant city hum, faint rain, his slow exhale.
```
