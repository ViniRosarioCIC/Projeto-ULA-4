# LOG_PROJETO — Semana S04 (LD1)
**Grupo:** GXX
**Integrantes presentes:** José Vinícius Jesus do Rosário
**Data:** 2026-04-05
**Repositório/Commit base:** <inserir_hash_do_commit>
**Arquivo Logisim:** ULA4_core.circ
**Milestone da semana:** M2 (Estratégia de seleção via op_select e MUX de 8 bits)

---

## 1) Objetivo do encontro (1–2 linhas)
[cite_start]Implementar a unidade de controle de seleção utilizando a lógica de decodificação (op_select) e um Multiplexador para gerenciar o caminho de dados de 8 bits. 

---

## 2) O que foi feito (bullet corto)
- [x] [cite_start]Criado subcircuito `op_select` com decodificador 3-8 para geração de sinais de controle one-hot. 
- [x] [cite_start]Implementado Multiplexador (MUX) de 8 entradas e 8 bits de dados para seleção da saída final F. 
- [x] Configurados Extensores de Bits (4 para 8 bits) para padronizar as entradas das operações lógicas no MUX.
- [x] Reestruturada a conexão do detector de zero (`z_detect8_v1`) para monitorar a saída pós-seleção do MUX.
- [x] [cite_start]Mapeadas as operações iniciais: Identidade A (000), Identidade B (001), XOR (010), Gray (011) e Paridade (100). 

---

## 3) O que foi testado (e como)
- Testes executados:
  - [cite_start]Verificação da lógica SOP: cada combinação de `OP` ativa apenas uma linha `sel` no decodificador. [cite: 190]
  - Teste de fluxo de dados: confirmação de que o valor de `logic4_v2` só chega em `F` quando `OP = 010`.
  - Validação de largura de barramento: garantia de que todas as entradas do MUX possuem 8 bits.
- Critério usado:
  - Observação visual de cores dos fios (verde escuro/claro) para identificar estados lógicos.
  - [cite_start]Conferência da Tabela Verdade do slide 14 contra o comportamento do componente MUX.
  ### Tabela Verdade de Seleção (op_select)

Esta tabela define como os 3 bits de entrada do pino OP (OP[2], OP[1], OP[0]) ativam cada sinal de controle individual e selecionam o dado no MUX.

| OP[2] | OP[1] | OP[0] | Hex | Sinal Ativo | Operação Realizada | Origem do Dado |
| :---: | :---: | :---: | :---: | :---: | :--- | :--- |
| 0 | 0 | 0 | 0 | **sel0** | Identidade A | Entrada A (direto) |
| 0 | 0 | 1 | 1 | **sel1** | Identidade B | Entrada B (direto) |
| 0 | 1 | 0 | 2 | **sel2** | XOR (v2) | logic4_v2 |
| 0 | 1 | 1 | 3 | **sel3** | Código Gray | codes4 (Saída G) |
| 1 | 0 | 0 | 4 | **sel4** | Paridade | codes4 (Saída P) |
| 1 | 0 | 1 | 5 | **sel5** | *Livre (Soma)* | Unidade Aritmética |
| 1 | 1 | 0 | 6 | **sel6** | *Livre* | - |
| 1 | 1 | 1 | 7 | **sel7** | *Livre* | - | 
  

---

## 4) O que falhou (se houver) — “testado vs falhou”

| Falha ID | Caso (TC-xxx) | Sintoma | Esperado | Observado | Hipótese | Próximo teste/ação |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| F-001 | TC-010 | Fio Vermelho em F | Sinal estável | Conflito (Erro) | Colisão entre saída do MUX e logic4 | Remover conexão direta do logic4 em F |
| F-002 | TC-011 | Fio Laranja no MUX | Valor correto | Erro de largura | Incompatibilidade 4 bits vs 8 bits | Revisar todos os Extensores de Bits |

---

## 5) Evidências (links/arquivos)
- Print Circuito com MUX: `evidencias/S04/ula4_com_selecao.png`
- Print Tabela Truth Table Decodificador: `evidencias/S04/tabela_op_select.png`
- Commit(s): `<hash_implementacao_mux>`, `<hash_correcao_fio_vermelho>`

---

## 6) Decisões tomadas (curto)
- [cite_start]Adoção do MUX de 8 bits como único "funil" para a saída F para evitar curtos-circuitos.
- Uso de Zero Extension para todas as operações lógicas de 4 bits para manter o barramento de 8 bits.
- [cite_start]Centralização do pino `OP` como seletor simultâneo do decodificador de controle e do multiplexador de dados. 

---

## 7) Próximos passos (ponte para a próxima semana)
- Semana S05: Implementação da Unidade Aritmética (Somador) e integração na entrada 5 do MUX.
- Configuração das flags de estado (C, V) baseadas nos sinais de controle do `op_select`.