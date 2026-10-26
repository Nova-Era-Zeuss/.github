# .github da Nova-Era-Zeuss

Padrões compartilhados pelos repositórios do ZEUSS. A decisão que rege este repositório é o ADR-0015 (`zeuss-produto/docs/adr/transversal/`).

Este repositório é público (exigência do GitHub Free para herdar os arquivos). **Nunca guarde aqui segredo, URL interna, OCID ou dado de cliente.**

## O que os outros repos herdam
Todo repositório da organização que não tiver arquivo próprio usa estes:
- `PULL_REQUEST_TEMPLATE.md`
- `ISSUE_TEMPLATE/` (item do roadmap, bug)
- `CONTRIBUTING.md` (branch, commits e PR)
- `SECURITY.md`

## O que NÃO é herdado
O GitHub não herda `dependabot.yml`, `CODEOWNERS` nem workflows. Esses ficam no `.github/` de cada repositório.

## Workflows reutilizáveis
Ficam em `.github/workflows/` e são chamados pelos repositórios com `uses:`.

| Workflow | Para quê |
|---|---|
| `ci-node-pnpm.yml` | instala com pnpm (versão do `packageManager`) e roda o comando de verificação do repo |

Exemplo de chamada (no `.github/workflows/ci.yml` do repositório):

```yaml
name: CI
on:
  pull_request:
  push:
    branches: [main]
jobs:
  ci:
    uses: Nova-Era-Zeuss/.github/.github/workflows/ci-node-pnpm.yml@main
    with:
      verify-command: pnpm verify
```
