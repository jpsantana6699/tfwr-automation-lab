# � Ordem Errada

## 🎯 Objetivo

A conquista executa uma sequência de plantio, ordenação e colheita de cactos em um mundo de tamanho variável.

## 📋 Estratégia

O script obtém o tamanho do mundo e a quantidade máxima de drones, planta cactos em colunas distribuídas por offsets, ordena as colunas e depois as linhas usando comparação e troca de valores, e por fim retorna ao ponto inicial para colher o resultado.

## 🤖 Drones

A divisão do trabalho acontece com `spawn_drone()` e `offsets`: cada drone recebe um conjunto de colunas ou linhas para processar, e a execução espera por `num_drones()` antes de seguir para a próxima etapa.

## 🌵 Cactus

A função `plantar_colunas(offset)` move até a coluna correspondente, verifica se o terreno não é `Grounds.Soil`, chama `till()`, planta `Entities.Cactus` e avança pela linha. O plantio é distribuído entre vários drones por `plantar_todos()`.

## 🔄 Ordenação

As funções `ordenar_colunas()` e `ordenar_linhas()` percorrem a grade e comparam `measure()` com `measure(North)` ou `measure(East)`. Quando a condição é atendida, `swap()` troca os valores para ordenar a coluna ou a linha.

## ▶️ Como usar

Execute o arquivo `ordem_errada.py` no ambiente que disponibiliza as funções globais do jogo. O script segue a ordem: `plantar_todos()`, `ordenar_todas_colunas()`, `ordenar_todas_linhas()`, `ir_para(0, 0)` e `harvest()`.

## ⚙️ Configuração

Os valores que podem ser alterados diretamente no código são:

- `size`: obtido com `get_world_size()`.
- `drones`: obtido com `max_drones()`.
- `Entities.Cactus`: a entidade planta no código.
- `Grounds.Soil`: condição usada para decidir `till()`.

Esses valores afetam diretamente a área processada e a quantidade de drones empregados.

## 📁 Arquivos

```text
Ordem-Errada/
├── ordem_errada.py
└── README.md
```
