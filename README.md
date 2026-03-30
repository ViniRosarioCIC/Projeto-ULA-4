| Passo | Expressão | Transformação | Regra/Lei | Observação |
|---|---|---|---|---|
| 1 | A⊕B=AB'+A'B | Expressão Original | - | Definição padrão do XOR |
| 2 | AB'+A'B | Dupla Negação | Regra 9 | Preparando para DeMorgan |
| 3 | (AB')⋅(A'B) | DeMorgan | Teorema 2 | Convertendo Soma em Produto Negado |
| 4 | - | Refatoração NAND | NAND-only | Implementação final com 4 portas |