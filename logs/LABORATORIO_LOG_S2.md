# LOG_PROJETO — Semana S2 (LD1)
**Grupo:** GXX
**Integrantes presentes:** José Vinícius Jesus do Rosário
**Data:** 17/03/2026 - 22/03/2026
**Repositório/Commit base:** <https://github.com/ViniRosarioCIC/Projeto-ULA-4.git>
**Arquivo Logisim:** <ULA4_core.circ>
**Milestone da semana:** MM2 (Implementação de subcircuitos logic4 e codes4)
---

## 1) Objetivo do encontro (1–2 linhas)
- Implementar os blocos de lógica e códigos, garantindo a conversão para Gray, detecção de paridade e detecção de zero.

---

## 2) O que foi feito (bullet curto)
- [x] Implementado subcircuito my_xor usando portas básicas (AND, OR, NOT).
- [x] Implementado conversor binário para gray de 4 bits (bin2gray4) utilizando o my_xor.
- [x] Implementado gerador de paridade de 8 bits (parity8_gen) em cascata de XORs.
- [x] Implementado detector de zero de 8 bits (z_detect8_v1) com porta NOR de 8 entradas.
- [x] Atualizado o arquivo CONTRATO_TESTES v0.2.md com 18 vetores de teste totais.
- [x] Atualizado arquivo de evidencias/s2/... e logs\LABORATORIO_LOG_S2.md
---

## 3) O que foi testado (e como)
**Bin2Gray:** Testados 8 vetores (bordas, alternâncias e blocos). Sucesso em todos os casos (ex: A=F -> F=8).
**Paridade:** Validados casos par e ímpar com 8 bits. Testada a "injeção de erro" mudando um bit e observando a inversão da saída P
**Z-Det:** Confirmado que a saída $Z=1$ apenas quando a entrada é estritamente 00.
---

## 4) O que falhou (se houver) — “testado vs falhou”

| Falha ID | Caso (TC-xxx) | Sintoma | Esperado | Observado | Hipótese | Próximo teste/ação |
|----------|----------------|---------|----------|-----------|----------|-------------------|
| F-001 | TC-001 | Fio Laranja no pino A | Sinal verde (binário) | Fio Laranja (largura incompatível) | O pino estava com 1 bit, mas o cabo era de 4 bits. | Alterar Propriedades: Bit Width do Pino A para 4. |
| F-002 | TC-008 | Saída incorreta no Gray | Resultado "8" hex | Resultado "F" hex | Conexão invertida entre Bit 3 e Bit 0 no Splitter. | Revisar mapeamento do Splitter (Top/Bottom). |
| F-003 | TC-013 | Fio Vermelho no Parity8 | Propagação do sinal | Fio Vermelho (Bit Width Mismatch) | Entrada do subcircuito my_xor configurada para 8 bits em vez de 1. | Editar my_xor e definir Pins A/B como 1 bit. |
| F-004 | TC-014 | Valor "E" no pino de saída | Número hexadecimal | Caractere "E" (Erro de barramento) | Splitter de saída com Fan-out menor que o número de bits. | Reconfigurar Splitter de saída para Fan-out 8. |

> Não houve falhas críticas que impedissem a conclusão do milestone. As falhas listadas foram identificadas e corrigidas durante o desenvolvimento, garantindo funcionamento correto de todos os subcircuitos.
---
## 5) Evidências (links/arquivos)
- Print testes: `evidencias\S2`
- Contrato de testes: [CONTRATO_TESTE v0.2](<../tests/CONTRATO_TESTES v0.2.md>)
- Commit(s): `<feat(codes4): finalize gray, parity and z-detect logic>`
---

## 6) Decisões tomadas (curto)
- Utilizar o bit 0 no topo e bit 3/7 na base nos splitters para manter o padrão visual do grupo.
- Representar entradas de 8 bits sempre com 2 dígitos hexadecimais no contrato de testes.
---

## 7) Próximos passos (ponte para a próxima semana)
- Semana S3: a definir

