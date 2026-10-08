# layer-charly-openclaw — RETIRED

This repo is retired: the OpenClaw family was consolidated into
[`opencharly/openclaw`](https://github.com/opencharly/openclaw)
(opencharly/opencharly#431), and this repo's four entities each had a different
fate.

| was here | fate |
|---|---|
| `openclaw-layer-skill` (`/charly-openclaw:openclaw-layer`) | **moved** to `candy/openclaw/charly.yml` in the family repo, updated for the consolidated family (owner re-homed, npm `openclaw@2026.9.8`, the dropped variant reference removed) |
| `openclaw-full-layer-skill` (`/charly-openclaw:openclaw-full-layer`) | **dropped** — the `-full` metalayer is not replaced, in any variant |
| `openclaw-full-ml-layer-skill` (`/charly-openclaw:openclaw-full-ml-layer`) | **dropped** — the `-ml` metalayer is not replaced |
| `charly-openclaw:` (documentation-only concept candy) | **dropped** — it existed only to carry those three skills, and the family repo carries its own two skills now |

The family's skills are `/charly-openclaw:openclaw` (the gateway image) and
`/charly-openclaw:openclaw-layer` (the gateway layer). Nothing should compose this
repo. It is kept only until the operator archives it.
