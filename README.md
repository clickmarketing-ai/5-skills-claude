# 5 skills para o Claude Code

Manual em português para instalar cada uma. Precisa do [Claude Code](https://code.claude.com/docs) instalado.

Comando que começa com `/` roda dentro do Claude Code. Os outros rodam no terminal, ou peça para o Claude rodar.
Depois de instalar, abra uma sessão nova para a skill valer.

Antes de instalar qualquer skill, leia o que ela faz. Ela passa a ter influência sobre o que o seu agente faz.

## 1. Superpowers

Faz a IA planejar antes e testar antes de dizer que terminou.

```text
/plugin install superpowers@claude-plugins-official
```

Repositório: https://github.com/obra/superpowers

## 2. Graphify

Desenha um mapa do seu projeto, para você ver como tudo se liga. Precisa do [uv](https://docs.astral.sh/uv/).

```bash
uv tool install graphifyy
graphify install
```

Depois, dentro do projeto:

```text
/graphify .
```

O `graphify install` acrescenta uma seção ao seu `CLAUDE.md`. No nosso teste, o mapa foi útil para enxergar o projeto, mas a busca comum achou mais arquivos ao procurar quem usa uma tabela. Use como mapa, não como substituto da busca.

Repositório: https://github.com/Graphify-Labs/graphify

## 3. Impeccable

Ajuda a tirar a cara de site feito por IA. Precisa do Node.

```bash
npx impeccable install
```

Abra uma sessão nova e rode uma vez em cada projeto:

```text
/impeccable init
```

Depois, por exemplo: `/impeccable critique a página de preços`.

Repositório: https://github.com/pbakaus/impeccable

## 4. Security Audit, da Cloudflare

Procura falha de segurança no seu código. Precisa do Node.

```bash
npx skills add https://github.com/cloudflare/security-audit-skill --skill security-audit --global
```

Use só em código seu ou que você tem autorização para testar. Ela é pesada: no nosso teste, a rodada rápida num app de 24 arquivos levou cerca de 1h30 e 3 milhões de tokens. Sem um ambiente isolado, os achados saem como "precisa verificar", e cada um pede conferência.

Repositório: https://github.com/cloudflare/security-audit-skill

## 5. Ponytail

Faz a IA escrever só o código necessário, sem cortar validação, tratamento de erro, segurança nem acessibilidade.

```text
/plugin marketplace add DietrichGebert/ponytail
/plugin install ponytail@ponytail
```

Para mudar a intensidade: `/ponytail lite`, `/ponytail full` ou `/ponytail ultra`.

Repositório: https://github.com/DietrichGebert/ponytail
