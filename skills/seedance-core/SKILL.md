---
name: seedance-core
description: This skill should be used when the user asks to "generar un prompt de Seedance", "crear un prompt para Seedance 2.5", "escribir un prompt de video con IA", "armar una escena para Seedance", "quiero un video de [personaje/producto] haciendo X", "revisar este prompt de Seedance", or requests help structuring a video-generation prompt with camera angles, shots, transitions, or reference images for Seedance. It also applies when refining, validating, or fixing the structure of an existing Seedance prompt. This skill provides the shared skeleton, vocabulary, and workflow that every style-specific Seedance skill (seedance-cinematic, seedance-advertising, seedance-anime, seedance-docufiction, etc.) builds on top of.
version: 0.1.0
---

# Seedance Core

Proporcionar el esqueleto estructural, el vocabulario de camara, la estrategia de referencias y el flujo de trabajo compartido para redactar prompts de Seedance 2.5. Las skills de estilo (cinematic, advertising, anime, docufiction...) anaden vocabulario y sensibilidad propia por encima de esta base, pero la estructura y las reglas de esta skill siempre aplican primero.

## Regla de idioma

Redactar el prompt final **siempre en ingles**, sin importar en que idioma hable el usuario. Los terminos tecnicos de camara (dolly, push-in, hard cut...) son estandar de la industria y van siempre en ingles. La conversacion con el usuario puede ser en su idioma; el bloque de prompt entregado, no.

## Formato de entrega

Entregar el prompt final como **texto plano copiable**, en un unico bloque de codigo, sin encabezados markdown ni comentarios dentro del bloque. Explicaciones, alternativas o preguntas van fuera del bloque, nunca mezcladas dentro del prompt.

## Flujo de trabajo: modo entrevista vs modo experto

Antes de escribir nada, evaluar cuanta informacion ya dio el usuario:

- **Modo entrevista** (informacion incompleta): identificar que bloques esenciales faltan (ver `references/prompt-skeleton.md`) y preguntar solo por esos, agrupando varias preguntas relacionadas en un solo turno. No interrogar por bloques opcionales si el usuario no los menciona ni parecen relevantes a la escena.
- **Modo experto** (el usuario ya describe sujeto, accion y contexto con detalle): no relanzar preguntas basicas. Pulir directamente la estructura, completar solo los huecos tecnicos que mejoran el resultado (framing, tipo de corte) y mostrar el prompt.

Bloques que casi siempre hace falta preguntar si faltan: **sujeto**, **accion**, y si la escena tiene **mas de un plano** (para decidir estructura single-shot vs multi-shot). El resto son razonablemente inferibles o el usuario los da junto con el estilo elegido.

## Esqueleto del prompt

Todo prompt de Seedance sigue el mismo orden de bloques, ver `references/prompt-skeleton.md` para la plantilla completa anotada y ejemplos. Resumen:

1. **Cabecera global** (opcional pero recomendada si hay mas de un plano): numero de shots, duracion total, aspect ratio, restricciones globales (ej. "no subtitles", "no on-screen text", "no BGM").
2. **Sujeto + accion** — primeras 20-30 palabras, el modelo ancla aqui lo mas importante. Siempre va primero, nunca despues de la camara.
3. **Escena/entorno** — lugar, epoca, contexto.
4. **Estilo visual** — lo que aporta la skill de estilo hija (cinematic, advertising, anime, docufiction...).
5. **Camara** — angulo + movimiento + encuadre. Ver `references/camera-vocabulary.md`. En escenas multi-shot, cada Shot N lleva su propia linea de camara.
6. **Luz / fisicas / atmosfera** — iluminacion, color grading, movimiento secundario (pelo, tela, humo, particulas).
7. **Audio** (opcional, Seedance 2.5 soporta audio nativo) — dialogo, ambiente, SFX, musica, o silencio deliberado.
8. **Transicion / tipo de corte** (si multi-shot) — ver seccion siguiente.

## Tipo de secuencia: no todo es one-take

Antes de escribir la camara, decidir que tipo de secuencia es la escena:

- **Single continuous shot**: la camara se mueve de forma continua (sigue, orbita, dolly) sin cortes. Describir el movimiento como evoluciona a lo largo de todo el plano, no un frame congelado.
- **Multi-shot con movimiento narrativo**: varios planos conectados por movimiento de camara o accion continua (ej. personaje camina de habitacion a balcon). Usar transiciones tipo match cut o continuidad de accion.
- **Multi-shot con hard cut (coverage)**: mismo instante o accion estatica cubierta desde varios angulos sin que el sujeto se mueva (ej. personaje quieto fumando, cambia el angulo para dar dinamismo). Usar formato `Shot 1: ... Hard cut.` `Shot 2: ...` — especificar framing y distancia por shot, y cerrar cada uno con "Hard cut" en vez de describir una transicion fluida. Este formato rinde mejor que una descripcion continua en cuanto hay mas de un angulo de camara sobre un sujeto que no se desplaza.

No asumir por defecto que la escena es one-take con camara seleccion siguiendo al sujeto: preguntar o inferir segun si el sujeto se mueve o no.

## Estrategia de referencias de imagen

Ver `references/reference-image-strategy.md` para el detalle completo. Regla central: la skill **nunca** debe hardcodear descripciones de personajes, productos o localizaciones concretas — debe servir igual para un personaje ya creado por el usuario, un producto, o un personaje futuro. Cuando el usuario adjunte imagenes, preguntar que elemento define cada una (cara/personaje, producto, localizacion, estilo) y usar el formato de etiquetado (`@Image N defines...`) en vez de describir ese elemento de nuevo en texto.

## Como se conectan las skills de estilo

Cada skill de estilo (seedance-cinematic, seedance-advertising, seedance-anime, seedance-docufiction) asume que esta skill ya se cargo primero. Aportan: vocabulario de iluminacion/color propio del genero, ritmo tipico de plano, convenciones de encuadre y audio habituales en ese estilo. No redefinen el esqueleto ni el idioma de salida — solo rellenan los bloques 4 (estilo visual), 6 (luz/atmosfera) y 7 (audio) con su sensibilidad particular.

## Additional Resources

- **`references/prompt-skeleton.md`** — plantilla anotada completa, con ejemplo de single-shot y de multi-shot hard cut.
- **`references/camera-vocabulary.md`** — lista de angulos, movimientos, encuadres y tipos de corte verificados contra guias oficiales de Seedance 2.5.
- **`references/reference-image-strategy.md`** — como preguntar, etiquetar y usar imagenes de referencia sin hardcodear personajes.
