# ola

One line answer mode for AI agents.

## What it does

Forces every model response into exactly one sentence. No preamble, no elaboration, no "let me know if", no trailing questions. The answer is the line. Answers follow ASD-STE100 Simplified Technical English.

## How to invoke

```
/ola on     # activate one-line mode
/ola off    # back to normal prose
/ola        # report current state
```

## Example

Question: "Why did the deploy fail?"

Normal prose:
> The deploy failed because the Docker image `ghcr.io/example/app:v2` couldn't be pulled — the registry returned a 404, which usually means the tag was deleted or the image was never pushed. You can verify by running `docker pull` locally.

Ola:
> The registry returned 404 for `ghcr.io/example/app:v2` — the tag doesn't exist.

## See also

- [`SKILL.md`](./SKILL.md) — full LLM-facing instructions
