# 🏆 Cultivo Competitivo

## 🎯 Objetivo

Esta conquista executa uma tentativa de leaderboard para `Hay_Single` e usa um script de coleta para manter `Items.Hay` em avanço até atingir o valor `100000000`.

## 📋 Estratégia

A pasta contém dois scripts: `hay_single.py` implementa a varredura da fazenda para colher Hay, e `competitivo.py` dispara a execução no leaderboard com `leaderboard_run()`. O processamento principal é um loop que percorre o mundo em linhas e colunas e coleta qualquer célula colhível.

## ▶️ Como usar

1. Mantenha os arquivos `hay_single.py` e `competitivo.py` na mesma pasta.
2. Execute `competitivo.py` primeiro.
3. O código de `competitivo.py` chama `leaderboard_run(Leaderboards.Hay_Single, "hay_single", 40960)`.
4. O script `hay_single.py` não é o ponto de entrada do leaderboard; ele é a rotina de coleta usada pela execução.

## ⚙️ Configuração

Os únicos valores diretamente relevantes no código são:

- `100000000`: limite de Hay para o loop de coleta.
- `40960`: argumento passado para `leaderboard_run()`.
- `size`: obtido por `get_world_size()`.

## 🤖 Drones

Não há uso de drones neste código. A coleta é feita por um único agente que percorre o mundo com `move()`, `can_harvest()` e `harvest()`.

## 📁 Arquivos

```text
Cultivo-Competitivo/
├── competitivo.py
├── hay_single.py
└── README.md
```

## ⚠️ Observações

- O loop em `hay_single.py` continua enquanto `num_items(Items.Hay) < 100000000`.
- O script percorre a fazenda em zigue-zague, avançando para a direita em cada coluna e voltando ao início da linha em seguida.
- O arquivo `competitivo.py` define a execução em leaderboard; o script de coleta é a lógica operativa.
