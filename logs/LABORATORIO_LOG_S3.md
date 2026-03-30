# LOG_PROJETO — Semana S03 (LD1)
**Grupo:** GXX
**Integrantes presentes:** José Vinícius Jesus do Rosário
**Data:** 2026-03-29
**Repositório/Commit base:** [Acessar Repositório](https://github.com/ViniRosarioCIC/Projeto-ULA-4.git)  
**Arquivo Logisim:** ULA4_core.circ
**Milestone da semana:** M1 (Refatoração v2 via DeMorgan + Integração funcional ULA4)

---

## 1) Objetivo do encontro (1–2 linhas)
Refatorar o subcircuito XOR para uma implementação exclusiva com portas NAND via Teoremas de DeMorgan e integrar os blocos logic4_v2 e codes4 na ULA4.

---

## 2) O que foi feito (bullet curto)
- [x] Criado subcircuito `my_xor_v2` utilizando a topologia de 4 portas NAND de 2 entradas.
- [x] Implementado `logic4_v2` com quatro instâncias de `my_xor_v2` para processamento bit-a-bit.
- [x] Ajustada a largura de barramento no `ULA4_core` para suportar entrada de 4 bits e saída de 8 bits via extensor.
- [x] Corrigido conflito de barramento (fio vermelho) nas entradas do bloco codes4 através da separação de sinais.
- [x] Acoplado detector de zero `z_detect8_v1` à saída principal F.

---

## 3) O que foi testado (e como)
- Testes executados:
  - Teste de equivalência funcional comparando saídas de `my_xor_v1` e `my_xor_v2`.
  - Validação de propagação de sinal em barramento de 4 bits no `logic4_v2`.
  - Teste de flag Z (Zero) injetando valor 0x00 na saída F de 8 bits.
- Critério usado:
  - Tabela verdade manual no Logisim para conferência de estados lógicos.
  - Uso de Probes (sondas) para validar a conversão de largura de bits nos extensores.

---

## 4) O que falhou (se houver) — “testado vs falhou”

| Falha ID | Caso (TC-xxx) | Sintoma | Esperado | Observado | Hipótese | Próximo teste/ação |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| F-001 | TC-002 | Fio vermelho (conflito) | Sinal verde estável | Erro de estado (E) | Curto-circuito entre pinos A e B | Isolar entradas de sinal |
| F-002 | TC-005 | Saída "E" nos pinos F/G | Valor binário correto | Erro de largura | Incompatibilidade 4 vs 8 bits | Configurar Extensor de Bits |

---

## 5) Evidências (links/arquivos)
- Print my_xor_v2 (NAND)
- Print ULA4_core integrado
- Print Teste de Equivalência


---

## 6) Decisões tomadas (curto)
- Padronização de subcircuitos v2 utilizando apenas portas universais (NAND) conforme requisito de laboratório.
- Utilização de Zero Extension para adequação da saída lógica de 4 bits ao padrão de 8 bits da ULA.
- Preservação dos circuitos v1 no arquivo de projeto para auditoria de rastreabilidade.

---

## 7) Próximos passos (ponte para a próxima semana)
- Semana S04: Estratégia de seleção por op_select/controle