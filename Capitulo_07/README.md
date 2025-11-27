# Capítulo 7 — O Método do Lugar das Raízes (LGR)

## Objetivos de Aprendizado

- Entender o conceito do Lugar das Raízes e como ele relaciona a posição dos polos em malha fechada com o ganho do controlador.
- Aprender a traçar LGRs para sistemas de malha aberta e interpretar pontos de intersecção com o eixo imaginário, ramos, e raízes complexas.
- Projetar compensadores (avanço/atraso, PD) usando o LGR para atender requisitos de desempenho (amortecimento, tempo de acomodação, margem de estabilidade).
- Implementar e visualizar LGRs usando `python-control` e `matplotlib`.

## Resumo (breve)

O Lugar das Raízes mostra como as raízes da equação característica em malha fechada (polos) se deslocam no plano s quando um parâmetro — tipicamente o ganho K — varia. É uma ferramenta gráfica essencial para projetar controladores em tempo contínuo que satisfaçam requisitos transitórios e de estabilidade.

## Conteúdo esperado nesta pasta

```
Capitulo_07/
    README.md 
    Controle_e_Automação_cap_07.ipynb
  
```

## Notebook / Código nesta pasta

- Notebook principal: `Controle_e_Automação_cap_07.ipynb` — contém exemplos de:
  - geração do Lugar das Raízes para plantas típicas;
  - identificação de ponto onde ramos cruzam o eixo imaginário (criterium de estabilidade);
  - projeto de compensadores por avanço/atraso a partir do LGR;
  - comparação entre respostas no tempo (degrau) antes/depois do projeto.

> Observação: se o notebook existir com outro nome (ex.: cópia), recomenda-se renomear para `Controle_e_Automação_cap_07.ipynb` e movê-lo para `Capitulo_07/notebooks/`.

## Dependências e execução

- Recomendado: Python 3.10+ com pacotes `numpy`, `scipy`, `matplotlib` e `control` (python-control).

Instalação rápida (local):

```bash
python -m venv .venv
source .venv/bin/activate
pip install -U pip
pip install numpy scipy matplotlib control jupyterlab
jupyter lab
```

No Google Colab, use as células que instalam dependências com `!pip install control`.

## Principais blocos do notebook (o que procurar)

1. Importação de bibliotecas e definições de funções utilitárias (plotagem do LGR, marcação de pólos/zeros).
2. Definição da planta em malha aberta G(s) e funções para traçar o LGR com `control.root_locus` ou `control.rlocus`.
3. Identificação de pontos críticos (pontos de encontro, ramo que cruza o eixo imaginário, ganho crítico Kcr).
4. Projeto de compensador simples via LGR (ex.: adicionar zero/pólo para deslocar ramos e melhorar amortecimento).
5. Simulação da resposta ao degrau antes e depois do compensador para validar requisitos.

## Exemplo rápido (pseudocódigo)

```python
import control as ct
import matplotlib.pyplot as plt

# Definir planta
s = ct.tf('s')
G = 1 / (s*(s+2)*(s+5))

# Traçar Lugar das Raízes
rlocus_data = ct.root_locus(G, Plot=True)

# Analisar ganhos que dão amortecimento desejado
# Escolher K, aplicar em malha fechada e comparar respostas
T = ct.feedback(K*G, 1)
ct.step_response(T)
plt.show()
```

## Exercícios sugeridos

1. Trace o LGR de `G(s)=1/(s(s+2)(s+5))`. Identifique o ramo que cruza o eixo imaginário e estime o ganho crítico K_cr.
2. Projete um compensador por avanço de fase para reduzir o overshoot em 50% e verifique no LGR se os pólos deslocados atendem o requisito.
3. Compare projeto via LGR com projeto por critérios em frequência (margens de ganho/fase) para a mesma planta.
4. Implemente uma função em `Capitulo_07/code/python/utils.py` que calcule e retorne os ganhos que colocam polos em um círculo de amortecimento especificado.

## Vídeos e leituras recomendadas

- Vídeo introdutório sobre Lugar das Raízes (procure por LGR em português ou em inglês "Root Locus tutorial").
- CTMS — Control Tutorials: seção sobre root locus.

### (Versão consolidada de referência)
- Google Colab Notebook: https://colab.research.google.com/drive/1C9PQXKQx4gVFcAj-Cv_vZ20PKkSvEDSA?usp=sharing
- Vídeo 1 - Controle e Automação - Estabilidade: Lugar das raízes: https://www.youtube.com/watch?v=lb8nQu830mQ
- Vídeo 2 - INTRODUÇÃO AO LUGAR GEOMÉTRICO DAS RAÍZES (LGR): https://www.youtube.com/watch?v=N7LuXO4bxCs

## Integração com Indústria 4.0

O LGR é usado em projeto de controladores que regulam processos industriais; projetar compensadores robustos garante atendimento a requisitos de produção (restrições de overshoot, tempo de estabilização) e evita instabilidades que podem afetar sistemas supervisionados por MES/APC. Em PIMS e Digital Twin, análises de LGR ajudam a validar faixas de ganho em simulações antes de aplicar mudanças em planta.


