# Capítulo 5 — O Desempenho de Sistemas de Controle

## Objetivos de Aprendizado

- Entender medidas de desempenho temporal (tempo de subida, overshoot, tempo de acomodação).
- Avaliar erro em regime permanente para entradas padrão (degrau, rampa, parábola) e relação com o tipo do sistema.
- Conhecer índices de desempenho (ISE, IAE, ITAE) e sua utilização em projeto e comparação de controladores.
- Relacionar localização de pólos/zeros com comportamento transitório e estabilidade.
- Executar simulações práticas em Python/Jupyter e interpretar gráficos de resposta no tempo e no domínio da frequência.

## Resumo (breve)

O capítulo aborda como quantificar e interpretar o desempenho de sistemas de controle, com ênfase em métricas temporais e em erro em regime permanente. Discute também índices de desempenho integrados (ISE, IAE, ITAE) usados para comparar controladores e ajustar ganhos, e mostra a ligação entre a posição dos pólos no plano s e as características transitórias observadas.
## Conteúdo disponível neste diretório

```
Capitulo_05/
	README.md
	Controle_e_Automação_cap_05.ipynb
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
- Google Colab Notebook: https://colab.research.google.com/drive/1UknAS6TtT-yU12_WCEg3gq-gzoTgycqE?usp=sharing
- Vídeo 1 - Sinais de Entrada para Teste e Resposta Transitória: https://www.youtube.com/watch?v=J8jp_3KaXLw
- Vídeo 2 - Erro de Estado Estacionário e Tipos de Sistemas: https://www.youtube.com/watch?v=hG7dq-51AAg
- Vídeo 3 - Localização dos Pólos e Zeros e a Resposta no Tempo: https://www.youtube.com/watch?v=OtaorqVoO0k
- Vídeo 4 - Índices de Desempenho (ISE, IAE, ITAE): https://www.youtube.com/watch?v=0HcUDa0CRPc
