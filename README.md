# charly-openclaw

The `charly-openclaw` family — the owning skills for the OpenClaw AI-gateway
layers.

The `charly-openclaw` candy is a **concept candy**: it ships no install content
and owns the `openclaw` family's `skill:` entities whose names have no namesake
candy. It carries three entities:

- `openclaw-layer` — the OpenClaw AI gateway service: port 18789, the `data`
  volume, the `openclaw` host alias, the npm install, and the loopback port relay.
- `openclaw-full-layer` — the maximal OpenClaw metalayer: the gateway plus Chrome
  and the full tool/skill set.
- `openclaw-full-ml-layer` — the maximal metalayer extended with the ML tools
  (Whisper speech-to-text, sherpa-onnx text-to-speech, CUDA).

The image, box, and tool skills of the same family are owned by their own repos
(`/charly-openclaw:openclaw`, `/charly-openclaw:openclaw-desktop`,
`/charly-tools:clawhub`). `candy/plugin-marketplace` regenerates the standalone
[opencharly/marketplace](https://github.com/opencharly/marketplace) corpus from
these entities, so the skills are authored here and projected there.

## What it provides

| Property | Value |
|---|---|
| Layer / candy | `charly-openclaw` (concept candy) |
| Install content | none — a `true` no-op `plan:` |
| Owns | 3 `skill:` entities: `openclaw-layer`, `openclaw-full-layer`, `openclaw-full-ml-layer` |
| Projected to | `marketplace/openclaw/skills/` |
| Service / port | none (the `openclaw-layer` skill documents port 18789) |

## How to use it

This repo is consumed as a **skill source**, not as an image layer. Edit the
`skill:` entities in `charly.yml`; the marketplace regeneration projects them
into the `/charly-openclaw:*` pages. To reference the repo directly, compose it
in a box. A box is a `candy:` node carrying the box's `base:` image and a nested
`candy:` list of layer refs (the nested `candy:` is the composition list; the
outer `candy:` is the box body):

```yaml
my-box:
  candy:                  # the box body (an IMAGE is a `candy:` node carrying `base:`)
    base: fedora          # the box's base image
    candy:                # the box's composition list
      - '@github.com/opencharly/layer-charly-openclaw:v2026.265.1914'
```

The OpenClaw gateway itself is installed by the `openclaw` image candy; the
`openclaw-full` metalayer composes it with the tool set.

## Layout

- `charly.yml` — the `charly-openclaw:` concept candy entity plus three `skill:`
  entities (`openclaw-layer`, `openclaw-full-layer`, `openclaw-full-ml-layer`).
- `.github/workflows/tag-on-merge.yml` — CalVer tag + `CHANGELOG/` on merge.
- `README.md` — this user overview.

## Related

- Owning skills: `/charly-openclaw:openclaw-layer`, `/charly-openclaw:openclaw-full-layer`, `/charly-openclaw:openclaw-full-ml-layer`
- Image / box skills: `/charly-openclaw:openclaw`, `/charly-openclaw:openclaw-desktop`
- Authoring reference: `/charly-image:layer`
- [`opencharly/marketplace`](https://github.com/opencharly/marketplace) — the projected corpus
- [`opencharly/charly`](https://github.com/opencharly/charly) — the charly CLI and image builder
- [`opencharly/opencharly`](https://github.com/opencharly/opencharly) — the umbrella
