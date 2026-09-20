---
name: seedance-docufiction
description: This skill should be used when the user asks to "hacer un video estilo documental con Seedance", "quiero un look found-footage", "video estilo camara en mano/reportaje", "docuficcion", "que parezca grabado con movil o camara de mano", or wants a raw, unpolished, documentary/found-footage visual treatment for Seedance rather than a polished cinematic or commercial look. Requires seedance-core to already be loaded for the shared prompt skeleton, camera vocabulary, and workflow.
version: 0.1.0
---

# Seedance Docufiction

Aportar la sensibilidad de documental/found-footage sobre el esqueleto de `seedance-core`. Rellena estilo visual, luz, ritmo de plano y audio con convenciones de grabacion cruda, no coreografiada en apariencia.

## Cuando aplicarla

Escenas que deben parecer capturadas, no dirigidas: reportaje, found-footage de terror/misterio, entrevista tipo documental, grabacion casera. La imperfeccion es una eleccion de estilo, no un defecto a corregir.

## Vocabulario de estilo visual (bloque 4)

- `documentary realism`, `found-footage style`, `handheld camcorder look`, `raw unpolished footage`.
- Variantes: `vérité documentary` (natural, observacional), `horror found-footage` (inestable, oscuro, luz de linterna/vision nocturna), `home video aesthetic` (grano, ligera sobreexposicion, encuadre imperfecto).
- Evitar vocabulario de composicion demasiado pulida (`anamorphic lens flare`, `studio gloss`) salvo que el usuario pida un hibrido.

## Luz / atmosfera (bloque 6)

Luz motivada y a menudo imperfecta: `natural available light`, `slightly overexposed`, `flashlight beam cutting through darkness`, `fluorescent office lighting`, `harsh on-camera flash`. Color grading minimo o inexistente: `naturalistic color, minimal grading` a menos que se pida un look mas procesado.

## Ritmo de plano

Camara casi siempre `handheld`, con imperfeccion deliberada: `slight handheld shake`, `imperfect framing`, `camera drifts and re-settles`. Planos tienden a ser mas largos y menos cortados que en publicidad — la sensacion de "una sola toma real" es parte del estilo. Cuando hay corte, que sea abrupto y no coreografiado: `hard cut`, nunca transiciones estilizadas como whip pan o match cut.

Para entrevistas o testimoniales, encuadre tipico: `medium shot, slightly off-center framing, eye level`, camara estatica con micro-ajustes de mano.

## Audio (bloque 7)

El audio es protagonista en este estilo, mas que en ningun otro: `raw ambient sound`, `wind noise on the mic`, `muffled voices`, `camera handling noise`, `diegetic sound only`. Evitar musica salvo que el usuario pida explicitamente un score — el found-footage autentico rara vez lleva musica no diegetica.

## Ejemplo de aplicacion

```
Duration: 7s. Aspect ratio: 16:9. No subtitles.
A figure crouches at the edge of a dark treeline, flashlight beam sweeping across the underbrush, breathing audible and uneven.
Dense forest at night, only the flashlight and faint moonlight providing visibility.
Horror found-footage style, handheld camcorder look, slight lens distortion at the frame edges.
Handheld, unsteady, camera drifts left as if the operator is turning to check behind them, imperfect framing.
Harsh flashlight beam cutting through darkness, naturalistic color, minimal grading, slight noise/grain.
Wind through trees, labored breathing close to the mic, distant cracking branch.
```
