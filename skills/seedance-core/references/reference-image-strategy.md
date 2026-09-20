# Estrategia de imagenes de referencia

## Principio central

Esta skill (y sus hijas de estilo) deben funcionar igual de bien para un personaje que el usuario ya tiene creado, para un producto, o para un personaje que se cree en el futuro. **Nunca** escribir en un prompt de ejemplo, en SKILL.md o en references/ una descripcion fisica concreta y reutilizable como si fuera "el personaje de la skill" — cada descripcion de sujeto vive solo en la conversacion puntual con el usuario, nunca en los archivos de la skill. Esto es lo que permite que la skill se comparta con otras personas sin arrastrar personajes ajenos.

## Cuando el usuario adjunta imagenes

Seedance 2.5 acepta hasta 50 referencias multimodales (imagen, video, audio, 3D) en un solo prompt, pero mas referencias no es mejor: un set pequeno y deliberado supera a un set saturado — el propio equipo de ByteDance encontro que pasado cierto punto, mas material empeora el resultado.

Al recibir imagenes, preguntar (si no es obvio por contexto) que elemento define cada una:

- Cara / identidad de personaje
- Producto
- Localizacion / escenario
- Estilo visual de referencia (paleta, iluminacion, composicion)
- Movimiento de camara de referencia (si se adjunta un video)

## Formato de etiquetado en el prompt

En vez de re-describir en texto lo que ya muestra una imagen adjunta, referenciarla explicitamente:

```
@Image 1 defines the character's face and outfit.
@Image 2 defines the product being held.
@Image 3 defines the location and lighting mood.
```

Si se adjunta un video de referencia para copiar solo el movimiento de camara (no el contenido), aclararlo:

```
@Video 1 defines the camera move and pacing only, not the subject or scene.
```

Esto evita que el modelo intente reconciliar una descripcion textual redundante o contradictoria con la imagen, y mejora fidelidad de identidad entre shots.

## Recomendaciones de duracion/recorte de referencias

Si la referencia es un clip de video o audio, mantenerlo entre 5-10 segundos — es el rango donde el modelo reconoce y estabiliza mejor el patron a imitar.

## Cuando NO hay imagenes

Si el usuario no adjunta nada, describir sujeto/producto/localizacion completamente en texto siguiendo el bloque "sujeto + accion" y "escena" del esqueleto (`references/prompt-skeleton.md`). No asumir ni inventar rasgos no mencionados; preguntar solo si el rasgo faltante afecta directamente camara o encuadre (ej. altura del sujeto para decidir angulo).
