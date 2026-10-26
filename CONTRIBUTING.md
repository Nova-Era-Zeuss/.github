# Como contribuir

Regras completas e motivos no ADR-0015 (`zeuss-produto/docs/adr/transversal/`).

## Branches
- `main` é o único branch longo. Tudo entra por PR com **squash merge**.
- Um branch por item do roadmap: `<tipo>/<id>-<slug>`, ex.: `feat/i148-adapter-http`.
- O mesmo nome em todos os repositórios que o item toca.
- Sem item: `<tipo>/<slug>`, ex.: `chore/atualizar-pnpm`.
- Tipos: `feat`, `fix`, `refactor`, `test`, `docs`, `chore`, `ci`, `build`, `perf`.

## Commits e PR
- O **título do PR** segue Conventional Commits com o id do item: `feat(i148): adapter HTTP de container`. Ele vira a mensagem do squash.
- Commits dentro do branch são livres.
- O CI precisa passar antes do merge.

## Versões
- Até produção, a versão é o SHA do commit (inclusive na tag da imagem).
- Depois de produção, SemVer com tag `v*`.

## Gerenciador de pacotes
pnpm em todos os repositórios, na versão do campo `packageManager`.

## Segredos
Nunca em código, issue, PR ou neste repositório. Na OCI ficam no Vault; no CI, em secrets do repositório e via OIDC.
