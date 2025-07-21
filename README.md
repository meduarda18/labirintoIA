# Trabalho V - Aplicação de Q-Learning: Navegação em Labirinto

## Introdução

Este trabalho tem como objetivo demonstrar a aplicação do algoritmo de Aprendizado por Reforço **Q-Learning** em um ambiente simulado de navegação. O cenário proposto é o de um **agente autônomo que deve atravessar um labirinto**, partindo de uma posição inicial até alcançar o objetivo final, evitando obstáculos e terrenos desfavoráveis.

## Contextualização

Neste trabalho, utilizamos a biblioteca `pygame` para construir visualmente um ambiente de labirinto 2D onde:

- O agente (representado como um círculo colorido) aprende progressivamente a melhor rota.
- Paredes (obstáculos) impedem a movimentação direta.
- Terrenos com "lama" reduzem a recompensa e devem ser evitados.
- O objetivo final (meta) está localizado em uma célula específica.

## Descrição do Ambiente

- **Tamanho do labirinto**: 12x12 células.
- **Ações possíveis**: cima, baixo, esquerda e direita.
- **Posição inicial (START)**: `(5, 0)`
- **Objetivo (GOAL)**: `(5, 11)`
- **Obstáculos (OBSTACLES)**: células que não podem ser atravessadas.
- **Lama (MUD)**: células que representam terrenos difíceis, com grande penalidade.

## Recompensas

A função de recompensa foi definida da seguinte forma:

- +100 para alcançar o objetivo (GOAL)
- -30 ao entrar em uma célula de lama (MUD)
- -10 ao tentar mover-se para um obstáculo (o agente permanece no mesmo lugar)
- -1 para cada movimento padrão, incentivando o agente a encontrar o caminho mais curto

## Resultados

Durante o treinamento, o agente explora diferentes caminhos e aprende a evitar obstáculos e regiões de lama. Após o treinamento, ele consegue navegar de forma eficiente até o objetivo, utilizando o conhecimento adquirido.

A execução do agente treinado mostra visualmente o caminho aprendido, destacando a eficiência do algoritmo mesmo em um ambiente com penalidades e múltiplos caminhos possíveis.

## Conclusão

O experimento demonstra que o Q-Learning é eficaz para treinar agentes em ambientes com incerteza e múltiplos obstáculos. A aplicação no contexto de um labirinto ilustra bem a capacidade do algoritmo de encontrar estratégias ótimas mesmo sem conhecimento prévio do ambiente, apenas com tentativa e erro.
