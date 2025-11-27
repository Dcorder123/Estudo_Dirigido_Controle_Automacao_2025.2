# Capítulo 10 — Projeto de Sistemas de Controle com Retroação

## Objetivos de Aprendizado

- Entender as estratégias de projeto em controle clássico (Lead, Lag, Lead-Lag) e sua relação com requisitos transitórios e em regime permanente.
- Aprender a usar o Lugar das Raízes (LGR) para projetar compensadores que movam pólos dominantes para regiões desejadas.
- Explorar como P, PI, PD e PID se relacionam com compensadores por avanço/atraso.
- Simular e validar projetos via `python-control` (resposta ao degrau, LGR e análise de ganhos).

## Resumo (breve)

Este capítulo foca no projeto — isto é, em como modificar a dinâmica de uma planta por meio de compensadores para atender especificações de desempenho (tempo de acomodação, overshoot, erro estacionário). A abordagem inclui compensadores em série (lead/lag), projeto geométrico via LGR e uso prático de controladores PID.

## Notebook / Exemplos nesta pasta

- `Controle_e_Automação_cap_10.ipynb` — contém:
  - introdução teórica sobre compensadores Lead, Lag e Lead-Lag;
  - procedimento de projeto via Lugar das Raízes (determinando pólos desejados, teste de ângulo, posicionamento de zero/pólo do compensador e cálculo de K);
  - exemplos de simulação (Lead para dupla integração, Lag para redução de erro estacionário);
  - exemplos com `python-control` (traço de LGR, step response, escolha de K);
  - discussão de aplicações industriais (CNC, bobinadeiras, gimbals).

> Observação: o notebook inclui células de instalação de pacotes para execução no Colab. Recomenda-se renomear/mover o notebook para `Capitulo_10/notebooks/` para manter a organização.

## Como executar localmente e no Colab

- Local (JupyterLab/Notebook): criar ambiente Python 3.10+ e instalar dependências:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -U pip
pip install numpy scipy matplotlib control jupyterlab
jupyter lab
```

- No Google Colab, execute as células com `!pip install control` quando solicitado.

## Principais blocos do notebook

1. Introdução e exemplos teóricos sobre Lead, Lag e Lead-Lag.
2. Procedimento passo-a-passo para projeto via LGR (escolha de pólos desejados, teste de ângulo, posicionamento de compensador e cálculo de ganho).
3. Exemplos de projeto (duplo integrador) e simulações de resposta ao degrau antes/depois do compensador.
4. Implementações de Compensador de Atraso (Lag) para aumentar ganho DC e reduzir erro estacionário.
5. Blocos com código prático em `python-control` para traçar LGR e simular respostas.

## Exemplos extraídos do notebook

- Projeto Lead para `G(s)=1/s^2` com `Gc_lead = (s+1)/(s+10)` e análise do LGR e resposta ao degrau (exemplo com K=20).
- Compensador Lag para `G(s)=1/((s+1)(s+2))` com pólo próximo da origem para aumentar ganho DC (z/p = 0.1/0.01 = 10) e reduzir o erro estacionário.

## Exercícios sugeridos

1. Execute o exemplo Lead do notebook e varie o zero e o pólo do compensador; compare overshoot e tempo de acomodação.
2. Para a planta `G(s)=1/(s(s+2)(s+4))`, use Routh para encontrar faixa de K estável e valide por LGR e polos do sistema fechado.
3. Projete um compensador Lead-Lag que satisfaça `Ts < 2s` e `Mp < 10%` para um sistema dado; valide por simulação.

## Vídeos e leituras recomendadas

- Google Colab Notebook: https://colab.research.google.com/drive/1fjoU4nntLm7gqJb9NxGIUus5bTiDjA-E?usp=sharing
- Vídeo 1 - Compensadores por Avanço de fase via LGR ( 1/2): https://www.youtube.com/watch?v=41eDOqnu680
- Vídeo 2 - Compensador por Atraso de Fase - Análise em Frequência: https://www.youtube.com/watch?v=5aQi9V5zkC8
- Vídeo 3 - Atuação de controladores Feedback P, PI e PID em sistema FOPDT: https://www.youtube.com/watch?v=kMRIKncdOQE
- Vídeo 4 - Projeto na Frequência: Avanço de Fase (ELT009, ELT035): https://www.youtube.com/watch?v=6TfPk_Xd9cI

## Integração com Indústria 4.0

Os compensadores e o projeto via LGR têm aplicações diretas em controle de processo e controle de movimento industrial. Exemplos práticos incluem tuning de servomecanismos em CNC, controladores de tensão em bobinadeiras e filtros em sistemas embarcados — todos relevantes para APC, MES e Digital Twin.
