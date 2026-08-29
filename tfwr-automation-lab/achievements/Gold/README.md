# 💰 Gold

## 🎯 Objetivo
O script busca acumular Gold até atingir a meta definida no código: `num_items(Items.Gold) >= 100000000`.

## 📋 Estratégia
Ele ajusta o tamanho do mundo, planta `Entities.Bush`, usa `Items.Weird_Substance` e observa o tipo da entidade atual. Quando a entidade aparece como `Entities.Treasure`, o código usa a substância, acompanha a sequência de ocorrências e faz a coleta no momento correto.

## 🌀 Maze e Treasure
O processo depende de `Entities.Bush` para iniciar o ciclo e de `Items.Weird_Substance` para agir sobre a entidade atual. O código verifica `get_entity_type() == Entities.Treasure` em vários pontos e realiza `harvest()` quando a sequência de eventos indica que a coleta deve acontecer.

## 🤖 Drones
A função `drone()` conta ocorrências, registra a sequência de hits e usa a substância quando encontra `Entities.Treasure`. O código também pode limitar a quantidade de drones com `num = length ** 2 - 1` quando `length ** 2 <= max_drones()`, e cada drone realiza o mesmo ciclo de verificação e coleta.

## 🔄 Ciclo
Criar Maze
↓
Usar Weird Substance
↓
Mover/acompanhar Treasure
↓
Harvest
↓
Repetir

## ▶️ Como usar
Execute `gold.py` no ambiente que disponibiliza as funções globais do jogo. O arquivo não recebe argumentos e a execução é controlada por seus loops internos.

## ⚙️ Configuração
`length` é definido como `5` e `set_world_size(length)` é chamado no início. A meta de Gold está em `100000000`, e a quantidade de substância usada depende de `length * 2 ** (num_unlocked(Unlocks.Mazes) - 1)`.

## 📁 Arquivos
Gold/
├── gold.py
└── README.md

## ⚠️ Observações
- O contador `n` é reiniciado quando ultrapassa `1000000`.
- O loop principal também reinicia `n` depois de `harvest()` quando a contagem atingir `299`.
- A execução termina quando a meta de Gold é alcançada ou quando o ciclo de coleta conclui as condições do código.
