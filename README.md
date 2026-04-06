| Passo | Expressão | Transformação | Regra/Lei | Observação |
|---|---|---|---|---|
| 1 | A⊕B=AB'+A'B | Expressão Original | - | Definição padrão do XOR |
| 2 | (AB'+A'B)'' | Dupla Negação | Regra 9 | Preparando para DeMorgan |
| 3 | ((AB')⋅(A'B))' | DeMorgan | Teorema 2 | Convertendo Soma em Produto Negado |
| 4 | - | Refatoração NAND | NAND-only | Implementação final com 4 portas |

| Componente | Versão | Mudança Principal | Justificativa |
|---|---|---|---|
| my_xor_v2 | v2 | 4 Portas NAND | Aplicação de DeMorgan |
| logic4 | v2 | Uso do my_xor_v2 | Refatoração para portas universais |
| ula4 | v2 | Integração v2 | Otimização de hardware |
