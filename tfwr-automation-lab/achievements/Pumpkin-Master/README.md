# 🎃 Pumpkin Master

## 🎯 Objetivo
Este script automatiza a plantação e a colheita de Pumpkins em um mundo de fazenda, ajustando o mapa para a quantidade de drones disponíveis e processando a área em faixas.

## 📋 Estratégia
O código entra em um loop principal, lê o tamanho do mundo, importa a biblioteca auxiliar `f0.py`, calcula o número de drones e divide a grade em blocos. Cada drone planta em uma parte da área, verifica o que pode ser colhido e replantia o que estiver morto.

## 🤖 Drones
A distribuição do trabalho acontece com `spawn_drone()`. Cada drone recebe uma faixa da matriz do mundo para plantar e verificar, e o código espera o término de todos os drones com `wait_for()` antes de colher o resultado final.

## 🎃 Pumpkins
Antes de plantar, o script verifica a água com `get_water()` e usa `Items.Water` quando o nível está abaixo de `0.7`. Se o solo não for `Grounds.Soil`, chama `till()`. Em seguida, planta `Entities.Pumpkin`. Quando encontra `Entities.Dead_Pumpkin`, faz `harvest()` e replantia imediatamente.

## 🔄 Funcionamento
Plantio
↓
Verificação
↓
Replantio de Pumpkins mortas
↓
Sincronização dos drones
↓
Harvest

## ▶️ Como usar
Os arquivos necessários são `f0.py` e `pumkin_v3_multi.py`. O script principal é `pumkin_v3_multi.py`; ele importa `f0` e executa o loop principal em ambiente com as funções globais do jogo disponíveis.

## 📁 Arquivos
Pumpkin-Master/
├── f0.py
├── pumkin_v3_multi.py
└── README.md

## ⚠️ Observações
O código ajusta o tamanho do mundo para múltiplo do número de drones com `set_world_size()`. A automatização depende de funções globais como `move`, `plant`, `harvest`, `can_harvest`, `get_entity_type`, `spawn_drone`, `wait_for` e `use_item`, além do movimento auxiliar definido em `f0.py`.
