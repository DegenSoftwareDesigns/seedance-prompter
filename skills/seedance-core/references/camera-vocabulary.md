# Vocabulario de camara para Seedance 2.5

Terminos verificados contra guias de referencia de Seedance 2.5 (higgsfield.ai, fal.ai, openart.ai, ByteDance blog oficial). Usar estos terminos tal cual, en ingles, dentro del bloque de prompt.

## Angulos

- `eye level` — neutro, altura de los ojos del sujeto.
- `low angle` — camara por debajo del sujeto, mirando hacia arriba; transmite poder/amenaza.
- `high angle` — camara por encima, mirando hacia abajo; transmite vulnerabilidad.
- `bird's eye` / `aerial` — vista cenital completa.
- `dutch angle` — camara inclinada lateralmente; transmite tension o desorientacion.
- `POV` — punto de vista subjetivo del personaje.
- `over-the-shoulder` — desde detras del hombro de un personaje, encuadrando a otro.
- `FPV` — primera persona, tipico de drones/accion inmersiva.

## Movimientos

- `static` — camara fija, sin movimiento.
- `push-in` / `dolly in` — avanza hacia el sujeto.
- `pull-out` / `dolly out` — se aleja del sujeto.
- `pan` — giro horizontal sobre eje fijo.
- `tilt` — giro vertical sobre eje fijo.
- `crane` — movimiento vertical amplio, tipicamente subiendo/bajando con brazo de grua.
- `tracking shot` / `follow` — la camara se desplaza junto al sujeto en movimiento.
- `handheld` — imperfeccion e inestabilidad deliberada, sensacion documental/urgente.
- `whip pan` — giro horizontal muy rapido, tipico de transicion entre planos.
- `orbit` — la camara rodea al sujeto manteniendo distancia.
- `dolly zoom` — efecto vertigo, la camara se mueve mientras el zoom compensa en direccion opuesta.

Preferir siempre un movimiento especifico ("slow push-in") sobre una palabra vaga como "cinematic camera" — el modelo responde mejor a instrucciones concretas de como evoluciona el plano a lo largo de su duracion completa, no a un frame congelado.

## Encuadre / distancia

- `extreme wide shot` — sujeto pequeno en el entorno.
- `wide shot` — cuerpo completo mas contexto.
- `medium shot` — de cintura para arriba.
- `close-up` — rostro/detalle.
- `extreme close-up` — detalle muy cercano (ojos, manos, objeto).

## Tipos de corte / transicion (multi-shot)

- `hard cut` — corte seco sin transicion animada; usar cuando el sujeto no se mueve entre shots y solo cambia el angulo (coverage).
- `match cut` — corte que conecta dos planos por similitud visual o de movimiento.
- `smash cut` — corte abrupto y deliberadamente brusco, para impacto.
- `continuous` / sin mencion de corte — indica que la camara sigue en movimiento ininterrumpido (single continuous shot).

Regla practica: en escenas de coverage (sujeto estatico, cambia solo el angulo), cerrar cada shot con "Hard cut." explicitamente. Dejarlo ambiguo es la causa mas comun de que el modelo intente animar una transicion fluida no deseada entre angulos que deberian ser cortes secos.

## Restricciones globales utiles

Anadir en la cabecera cuando aplique, para evitar artefactos no deseados:

- `no subtitles`
- `no on-screen text`
- `no BGM` (cuando se quiere solo sonido ambiente/dialogo, sin musica)
- `aspect ratio: 16:9` / `9:16` / `2.39:1` / etc.
