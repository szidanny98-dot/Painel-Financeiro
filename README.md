# Simulador de investimentos — Selic, CDI, IPCA e Poupança

Painel interativo, em um único arquivo HTML, para simular o retorno líquido
(já descontando IR e IOF) de investimentos de renda fixa comuns no Brasil,
usando a Selic como taxa de referência mestre.

## O que o painel faz

- **Taxas de referência editáveis**: Selic, CDI, IPCA (12 meses) e poupança.
- **Selic como taxa mestre**: ao atualizar a Selic (por exemplo, após uma
  reunião do Copom), o CDI e a poupança são recalculados automaticamente
  seguindo as regras oficiais. Pode ser destravado para edição manual.
- **Simulador de retorno líquido**: CDB / Tesouro Selic, LCI/LCA (isento de
  IR), Tesouro IPCA+, poupança e previdência privada (PGBL/VGBL, regime
  regressivo), com valor inicial, aporte mensal e prazo configuráveis.
- **Comparativo entre produtos**: gráfico e cartões comparando o valor
  líquido final dos principais produtos, lado a lado.

## Como usar localmente

Basta abrir o arquivo `index.html` em qualquer navegador. Não depende de
servidor ou instalação — só a biblioteca de gráficos (Chart.js) é carregada
de um CDN, então é necessário estar conectado à internet.

## Como publicar no GitHub Pages

1. Crie um repositório novo no GitHub (público, se quiser usar o GitHub
   Pages gratuito).
2. Envie o arquivo `index.html` para a raiz do repositório.
3. No repositório, vá em **Settings → Pages**.
4. Em **Source**, selecione a branch `main` (ou `master`) e a pasta `/root`.
5. Salve. Em alguns minutos o GitHub fornece um link do tipo
   `https://SEU_USUARIO.github.io/NOME_DO_REPOSITORIO/`.

## Comandos de exemplo (Git via terminal)

```bash
mkdir simulador-investimentos
cd simulador-investimentos
git init
# copie o index.html e o README.md para esta pasta
git add index.html README.md
git commit -m "Primeira versão do simulador de investimentos"
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/simulador-investimentos.git
git push -u origin main
```

## Atualizando as taxas

As taxas de Selic, CDI e IPCA usadas por padrão refletem julho de 2026. Elas
não se atualizam sozinhas (o arquivo não faz chamadas a nenhuma API) — a
ideia é que você mesmo atualize a Selic no painel sempre que houver uma
nova decisão do Copom, e o restante recalcula a partir dela.

Fontes oficiais recomendadas para conferência:
- Selic: Banco Central do Brasil (bcb.gov.br)
- IPCA: IBGE (ibge.gov.br)
- CDI: B3 (b3.com.br)

## Aviso

Esta é uma ferramenta educativa de simulação. Não constitui recomendação de
investimento. As taxas de mercado reais variam por instituição financeira —
confirme sempre antes de investir.
