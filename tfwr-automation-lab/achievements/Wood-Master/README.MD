# 🌳 Wood Master

## 🎯 Objetivo
A conquista automatiza a produção de árvores em uma grade do mundo, usando posições fixas e processos repetidos para manter a plantação ativa.

## 📋 Estratégia
O código define pontos de plantio em posições separadas por intervalos e usa uma rotina de busca por `get_companion()` para verificar se a célula vizinha está em um estado válido. Quando a condição não é adequada, a rotina colhe e replanta.

## 🌳 Trees e Companions
A estratégia usa `Entities.Tree` como planta principal. A função `plant_companion(x, y, p)` explora posições próximas ao ponto central e consulta `get_companion()`. Se o retorno não é válido ou se a posição já foi marcada, o script realiza a colheita e replantio para manter a área em funcionamento.

## 🤖 Drones
As posições são distribuídas em um conjunto de pontos que se repetem em blocos de 8 unidades. Cada drone recebe uma tarefa de plantio em um ponto específico do conjunto, com a intenção de cobrir diferentes áreas da fazenda em paralelo.

## 🔄 Funcionamento
Distribuição das posições
↓
Plantação
↓
Busca de Companion
↓
Colheita/Replantio
↓
Repetição

## ▶️ Como usar
Os arquivos `f0.py` e `mix_plant.py` precisam existir na mesma pasta. O script executado é `mix_plant.py`, que importa `f0` e dispara a rotina principal no ambiente com as funções globais do jogo disponíveis.

## 📁 Arquivos
Wood-Master/
├── f0.py
├── mix_plant.py
└── README.md

## ⚠️ Observações
O código usa `get_companion()` para decidir o próximo passo da rotina. Ele também chama `till()` antes de plantar quando o tipo de planta exige solo preparado e usa `Items.Water` quando o nível de água está abaixo de `0.7` antes de continuar. A automação depende das funções globais do ambiente e do movimento definido em `f0.py`.
