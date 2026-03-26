Caso | A | B | OP | F esperado | C | V | Z | Observação 
-----|---|---|----|------------|---|---|---|-----------
TC-001 |0|0|XOR|0|ASD|ASD|ASD| PASS
TC-002 |0|1|XOR|1|ASD|ASD|ASD| PASS
TC-003 |1|0|XOR|0|ASD|ASD|ASD| PASS
TC-004 |1|1|XOR|1|ASD|ASD|ASD| PASS
TC-005|0|0|GRAY|0|ASD|ASD|ASD|PASS: Borda inferior (0000 -> 0000)
TC-006|F|0|GRAY|8|ASD|ASD|ASD|PASS: Borda superior (1111 -> 1000)
TC-007|5|0|GRAY|7|ASD|ASD|ASD|PASS: Alternância (0101 -> 0111)
TC-008|A|0|GRAY|F|ASD|ASD|ASD|PASS: Alternância (1010 -> 1111)
TC-009|3|0|GRAY|2|ASD|ASD|ASD|PASS: Bloco baixo (0011 -> 0010)
TC-010|C|0|GRAY|A|ASD|ASD|ASD|PASS: Bloco alto (1100 -> 1010)
TC-011|1|0|GRAY|1|ASD|ASD|ASD|PASS: Sequencial (0001 -> 0001)
TC-012|8|0|GRAY|C|ASD|ASD|ASD|PASS: Sequencial (1000 -> 1100)
TC-013|03|0|PARITY|0|ASD|ASD|ASD|PASS: Caso Par (2 bits 1s).
TC-014|07|0|PARITY|1|ASD|ASD|ASD|PASS: Caso Ímpar (3 bits 1s). Injeção de erro validada: ao mudar 1 bit, a paridade inverteu.
TC-015|00|0|PARITY|0|ASD|ASD|ASD|PASS: Zero bits 1s é considerado Par.
TC-016|FF|0|PARITY|0|ASD|ASD|ASD|PASS: 8 bits 1s (Par).
TC-017|00|0|Z-DET|0|ASD|ASD|ASD|PASS: Entrada zero, flag Z ativa (1).
TC-018|01|0|Z-DET|1|ASD|ASD|ASD|PASS: Entrada não-zero, flag Z inativa (0).
