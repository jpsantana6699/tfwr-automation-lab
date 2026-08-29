# 🤖 Full Automation

## 🎯 Objetivo
A estratégia tem como objetivo percorrer uma sequência de unlocks e produzir os itens necessários para desbloquear `Unlocks.Leaderboard`, usando módulos especializados em cada recurso.

## 📋 Estratégia
O núcleo está em `full_reset/full_reset_solution.py`: define `unlock_order` e chama `unlock_wrapper()` para cada unlock. Para cada etapa, calcula o custo com `get_cost()`, coleta os itens necessários por módulos de farm, e executa `unlock()`.

## 🔄 Fluxo
Início
↓
`full_reset_solution.py`
↓
sequência de unlocks
↓
coleta dos itens de cada etapa
↓
`Unlocks.Leaderboard`
↓
conclusão

## 🧩 Arquivos
- `full_reset`: pasta com os módulos de coleta e o driver principal de unlocks.
- `leaderboard.py`: arquivo que dispara `leaderboard_run(Leaderboards.Fastest_Reset, "full_reset_solution", 1000)`.
- Não há `start_full_reset.py` neste diretório; a execução real do fluxo é iniciada pelo `leaderboard`.

## ▶️ Como usar
1. Coloque os arquivos da pasta `full_reset` no ambiente do jogo, mantendo os imports entre módulos.
2. Execute `leaderboard.py` para iniciar a simulação do leaderboard.
3. Não execute diretamente `full_reset_solution.py` como ponto de entrada principal neste diretório.

## ⚙️ Configuração
- `POWER_THRESHOLD = 250` em `full_reset_solution.py`.
- `unlock_order` define a sequência completa de unlocks executada pelo script.
- `leaderboard_run(Leaderboards.Fastest_Reset, "full_reset_solution", 1000)` define o alvo e a velocidade da simulação.

## 📌 Requisitos
- Os módulos precisam estar no mesmo ambiente e com os imports resolvidos (`wood`, `hay`, `carrot`, `power`, `pumpkin`, `gold`, `weird_substance`, `cacti`, `bone`).
- O ambiente precisa expor `Unlocks`, `Items`, `get_cost()`, `unlock()`, `leaderboard_run()` e as funções globais de farm e coleta usadas nos módulos.

## ⚠️ Observações
- A automação depende de uma sequência fixa de unlocks em `unlock_order`.
- O loop principal usa módulos separados para cada recurso e não trata o processo como uma única rotina monolítica.
- O código não inclui um arquivo de inicialização alternativo no diretório atual; o gatilho oficial presente é o `leaderboard.py`.

## 📁 Arquivos
Full-Automation/
├── full_reset/
└── README.md
