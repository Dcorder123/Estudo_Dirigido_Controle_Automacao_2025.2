# Capítulo 13 — Análise e Projeto Avançado (Resumo do Notebook)

**Objetivos de Aprendizado:**

- Consolidar conceitos avançados abordados no Capítulo 13 do material do curso.
- Executar simulações práticas presentes no notebook `Controle_e_Automação_cap_13ipynb.ipynb` e interpretar resultados (resposta ao degrau, diagramas de Bode, estabilidade e margens).
- Relacionar técnicas de análise com aplicações industriais e com tópicos de Indústria 4.0.

## Resumo

O Capítulo 13 aprofunda técnicas de análise e projeto que complementam os métodos clássicos (LGR, Routh, compensadores). Aqui encontramos exemplos e aplicações práticas — incluindo simulações com `python-control` — que permitem validar desempenho e robustez dos projetos.

## Notebook desta pasta

- `Controle_e_Automação_cap_13ipynb.ipynb` — contém:
  - explicações e lembretes teóricos;
  - células de simulação em `python-control` (modelagem, resposta ao degrau, Bode e margem de fase/ganho);
  - exemplos aplicados e exercícios comentados.

## Como executar (local / Colab)

- Local (recomendado via ambiente virtual):

```bash
python -m venv .venv
source .venv/bin/activate
pip install -U pip
pip install numpy scipy matplotlib control jupyterlab
jupyter lab
```

- Google Colab: execute as células que instalem dependências (`!pip install control`) se necessário.

## Conteúdos principais (orientação rápida)

- Modelagem e verificação de ganhos DC;
- Uso de `ct.step_response`, `ct.bode_plot` e `ct.root_locus` para analisar comportamento em tempo e frequência;
- Interpretação de margens de ganho/fase para robustez;
- Comparação entre respostas antes/depois de compensadores projetados.

## Exercícios sugeridos

1. Rode as células de resposta ao degrau do notebook e compare as curvas para diferentes valores de ganho K.
2. Gere o diagrama de Bode para a planta do capítulo e estime as margens de ganho e fase; discuta como isso impacta escolha de controlador.
3. Proponha um pequeno compensador (Lead ou Lag) presente no notebook e valide por simulação a melhoria no desempenho.

## Integração com Indústria 4.0

As análises de robustez e resposta em frequência são essenciais para sistemas industriais com rede de sensores/atuadores (IIoT). Margens adequadas e testes de sensibilidade contribuem para designs confiáveis em aplicações como controle de processo, robótica e sistemas embarcados conectados.
## Vídeos e leituras recomendadas


- Google Colab Notebook: https://colab.research.google.com/drive/1pUlFoa-XpJ7urDQyXjpgFC9cYGYtqC-N?usp=sharing

