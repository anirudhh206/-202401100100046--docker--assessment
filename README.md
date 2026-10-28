# Docker & Container Security — Practical Assessment (CA-2)

| | |
|---|---|
| Name | Anirudh Vashisth |
| REGNO | 202401100100046 |
| PORT | 8046 |
| Docker Hub username | cursedsoul |
| Docker Hub repository | https://hub.docker.com/r/cursedsoul/fest-backend |

## AI tools used
- **Claude Code (Anthropic)** — wrote the Dockerfiles, `compose.yaml` and this README, ran the build/scan/push/verify commands on my machine, and explained errors.

## Digest of 1.0.0 as pushed to Docker Hub
`sha256:bf261f35e584a91ac07858d9bfd14346d5f6ce5d6dd4f9ee297e19c83cc3257a`

1.0.0 is signed with cosign (`cosign.pub`); 1.0.1 (`sha256:aae80837ff66e44a123366ee998650535e870324acb28fc45a71e821d7a783b2`) is deliberately unsigned and `cosign verify` rejects it.

## Vulnerability table (Trivy 0.76.1)

| Image | Base | CRITICAL | HIGH | Size |
|---|---|---|---|---|
| `fest-backend:0.1` (before) | `python:3.9` | 234 | 2249 | 1.61 GB |
| `fest-backend:0.2` (after) | `python:3.13.18-slim` | 0 | 49 | 200 MB |

`trivy image --severity CRITICAL --ignore-unfixed --exit-code 1 fest-backend:0.2` exits with code 0.
Reports: `reports/trivy-before.txt`, `reports/trivy-after.txt`.

## Steps not completed
- None of the five stages failed. Screenshots in `screenshots/` are added separately from my own terminal.
