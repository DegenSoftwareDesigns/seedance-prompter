# Seedance Prompter

Plugin de Claude Code para generar prompts de video para **Seedance 2.5**. Una skill base define la estructura, vocabulario de cámara y flujo de trabajo compartidos; skills de estilo la extienden con la sensibilidad de cada género.

## Instalación

```bash
claude plugin install DegenSoftwareDesigns/seedance-prompter
```

O en local, durante desarrollo:

```bash
cc --plugin-dir /ruta/a/seedance-prompter
```

## Skills incluidas

| Skill | Qué aporta |
|---|---|
| `seedance-core` | Esqueleto del prompt, vocabulario de cámara, modo entrevista/experto, estrategia de imágenes de referencia. Se carga siempre primero. |
| `seedance-cinematic` | Look narrativo/dramático: luz motivada, planos lentos, atmósfera de cine. |
| `seedance-advertising` | Producto/marca: hero shots, luz de estudio, ritmo rápido, restricciones para spots. |
| `seedance-anime` | Estilo animación japonesa: cel-shading, poses dinámicas, SFX de género. |
| `seedance-docufiction` | Found-footage/documental: cámara en mano, imperfección deliberada, audio crudo. |

## Cómo funciona

1. `seedance-core` decide si hace falta preguntar (falta sujeto/acción/número de planos) o si ya hay info suficiente para redactar directo.
2. Detecta el tipo de secuencia: plano único continuo, multi-shot con movimiento narrativo, o multi-shot con **hard cut** (cuando el sujeto está quieto y solo cambia el ángulo — p. ej. un personaje fumando en un balcón cubierto desde varios ángulos).
3. La skill de estilo que corresponda rellena estilo visual, luz y audio sobre ese esqueleto.
4. Entrega el prompt final **siempre en inglés**, como texto plano listo para copiar en Seedance.

## Imágenes de referencia

Ninguna skill de este plugin hardcodea personajes, productos ni localizaciones — están escritas para servir igual con un personaje que ya tengas creado, un producto, o algo futuro. Al adjuntar imágenes, se etiquetan por elemento (`@Image 1 defines the character's face`, `@Image 2 defines the product`, etc.) en vez de redescribirlas en texto. Detalle completo en [`skills/seedance-core/references/reference-image-strategy.md`](skills/seedance-core/references/reference-image-strategy.md).

## Añadir una skill de estilo nueva

Crear `skills/seedance-<estilo>/SKILL.md` siguiendo el mismo patrón que las existentes: frontmatter con `description` en tercera persona y frases disparadoras concretas, y un cuerpo que solo rellena los bloques 4 (estilo visual), 6 (luz/atmósfera) y 7 (audio) del esqueleto — nunca redefine estructura ni idioma de salida, eso vive únicamente en `seedance-core`.

## Estructura del repo

```
.claude-plugin/plugin.json
skills/
├── seedance-core/
│   ├── SKILL.md
│   └── references/
│       ├── prompt-skeleton.md
│       ├── camera-vocabulary.md
│       └── reference-image-strategy.md
├── seedance-cinematic/SKILL.md
├── seedance-advertising/SKILL.md
├── seedance-anime/SKILL.md
└── seedance-docufiction/SKILL.md
```
