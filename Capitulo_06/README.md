# Capítulo 6 — A estabilidade de sistemas lineares com retroação

## Objetivo deste README

Este README relaciona explicitamente o conteúdo do notebook presente nesta pasta com os conceitos estudados no capítulo: análise de estabilidade, Critério de Routh-Hurwitz, exemplos numéricos de faixa de ganho estável, casos de estabilidade marginal e simulações de resposta ao degrau.

## Notebook principal nesta pasta

- `Cópia_de_Controle_e_Automação_cap_06.ipynb` — notebook com texto comentado e código executável. Contém:
	- explicações teóricas (Routh-Hurwitz, casos especiais);
	- exemplo para encontrar faixa de ganho estável (G(s)=K/[s(s+2)(s+4)] e K_cr=48);
	- exemplo com linha de zeros (estabilidade marginal) e simulação da resposta ao degrau;
	- células de código com simulações (python-control) e plotagem das respostas.

> Observação: recomenda-se renomear o notebook para `Controle_e_Automação_cap_06.ipynb` e movê-lo para `Capitulo_06/notebooks/` para manter consistência com outros capítulos.

## Resumo (breve)

O capítulo aborda A estabilidade de sistemas lineares com retroação, com ênfase em métricas temporais e em erro em regime permanente. Discute também índices de desempenho integrados (ISE, IAE, ITAE) usados para comparar controladores e ajustar ganhos, e mostra a ligação entre a posição dos pólos no plano s e as características transitórias observadas.
## Conteúdo disponível neste diretório

```
Capitulo_06/
	README.md
	Controle_e_Automação_cap_06.ipynb
```


- Bibliotecas usadas: numpy, scipy, matplotlib e control (python-control). Para MATLAB, mantenha exemplos equivalentes em `code/matlab/`.

## Principais tópicos e seções do notebook

- Importação de bibliotecas e definição de funções utilitárias (métricas de desempenho).
- Simulações de resposta ao degrau e identificação dos parâmetros transitórios (tr, ts, Mp).
- Cálculo de erro em regime permanente para degrau/rampa/parábola e relação com tipo do sistema.
- Implementação e comparação de índices ISE, IAE e ITAE para diferentes controladores.
- Estudo do efeito do deslocamento de pólos (lugar das raízes) no desempenho temporal.

## Vídeos e leituras recomendadas


### (Versão consolidada de referência)
- Google Colab Notebook: https://colab.research.google.com/drive/16I_7KQDE6_PPxTnesftsA3229M8kmiFl?usp=sharing
- Vídeo 1 - Conceito de Estabilidade em Sistemas de Controle: https://www.youtube.com/watch?v=RRjz-BnZijI
- Vídeo 2 - Critério de Estabilidade de Routh-Hurwitz: https://www.youtube.com/watch?v=Vpxj4JQGdnM
- Vídeo 3 - Estabilidade Relativa e Deslocamento de Eixos: https://www.youtube.com/watch?v=jzV82SKc9JA
- Vídeo 4 - Variáveis de Estado: https://www.youtube.com/watch?v=u4aMpm0VEHI