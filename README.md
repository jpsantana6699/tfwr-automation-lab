# 🌾 tfwr-automation-lab

## 📋 Sobre

Este repositório reúne scripts de automação para o jogo The Farmer Was Replaced. O foco principal está em estratégias de conquista mais exigentes, com lógica feita para automatizar tarefas que envolvem múltiplos drones, plantio, coleta, ordenação, unlocks e recursos específicos.

Além das conquistas mais simples que podem ser desbloqueadas jogando normalmente, ou que exigem automação bem leve, este projeto reúne rotinas mais pesadas e mais demoradas, como as que estão dentro da pasta `achievements`. Essas são as estratégias mais chatinhas de montar e rodar, porque costumam demorar mais e exigem uma sequência bem mais cuidadosa.

## ✨ O que está aqui

- Automação principal para cultivo e gestão do mundo
- Rotinas com múltiplos drones
- Estratégias dedicadas a recursos específicos
- Scripts de conquistas e desafios
- README próprios para cada conquista

## 🏆 Conquistas incluídas

- `Cultivo-Competitivo`
- `Ordem-Errada`
- `Pumpkin-Master`
- `Wood-Master`
- `Gold`
- `Full-Automation`

Essas são as conquistas mais relevantes que foram adicionadas no código e que demandam mais trabalho e mais tempo para rodar. Há bem mais conquistas no jogo, mas muitas são mais fáceis de fazer jogando normalmente ou com automações bem mais simples. As que estão neste repositório tendem a ser as mais complexas e mais demoradas.

## 📁 Estrutura

```text
the_farmer/
├── README.md
├── tfwr-automation-lab/
│   ├── achievements/
│   │   ├── Cultivo-Competitivo/
│   │   ├── Full-Automation/
│   │   ├── Gold/
│   │   ├── Ordem-Errada/
│   │   ├── Pumpkin-Master/
│   │   └── Wood-Master/
│   └── automation/
│       ├── bonesModule.py
│       ├── cactusModule.py
│       ├── farmModule.py
│       ├── mazeModule.py
│       ├── newMain.py
│       ├── parameters.py
│       ├── sunflowerModule.py
│       ├── tools.py
│       └── utils.py
```

- `automation/`: contém a lógica principal de cultivo, prioridade, drones e módulos especializados.
- `achievements/`: reúne conquistas e rotinas específicas, com README próprio para cada uma.

## 🤖 Como funciona

```text
Verifica o mundo
↓
Define a prioridade e o ciclo
↓
Distribui o trabalho entre os drones
↓
Executa o plantio/coleta/ordenação
↓
Repete em loop
```

A lógica principal fica em `tfwr-automation-lab/automation/newMain.py` e o comportamento de decisão e suporte está em `tools.py` e em `parameters.py`.

## 🚀 Como usar

1. Ajuste os parâmetros em `tfwr-automation-lab/automation/parameters.py`.
2. Execute a rotina principal em `tfwr-automation-lab/automation/newMain.py`.
3. Para conquistas específicas, use os scripts dentro de `tfwr-automation-lab/achievements/`.

## ⚙️ Configuração

Os parâmetros principais estão em `parameters.py` e controlam o comportamento da automação geral.

- `WORLD_SIZE`: tamanho do mundo.
- `DRONE_NUMBER`: quantidade de drones a serem usados.
- `PRIORITY_CROP`: prioridade manual da cultura.
- `SUNFLOWER_CYCLE`: ciclo relacionado ao girassol.
- `PLANTS`: lista de culturas e metas da rotina principal.

## 📌 Observações

- O projeto foi organizado para permitir tanto automação geral quanto estratégias específicas por conquista.
- Algumas rotinas dependem de unlocks e itens do jogo.
- As estratégias em `achievements` funcionam como rotinas independentes e mais focadas em uma conquista específica.

## 📄 Licença

Nenhuma licença foi definida para este projeto no estado atual.

