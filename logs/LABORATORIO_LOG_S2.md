# LOG_PROJETO — Semana S2 (LD1)

**Grupo:** SEM GRUPO  
**Integrantes presentes:** José Vinícius Jesus do Rosário  
**Data:** 17/03/2026 - 22/03/2026  
**Repositório/Commit base:** [Acessar Repositório](https://github.com/ViniRosarioCIC/Projeto-ULA-4.git)  
**Arquivo Logisim:** `ULA4_core.circ`  
**Milestone da semana:** M2 (Implementação de subcircuitos logic4 e codes4)

---

## 1) Objetivo do encontro
* Implementar os blocos de lógica e códigos, garantindo a conversão para Gray, detecção de paridade e detecção de zero.

---

## 2) O que foi feito
- [x] Implementado subcircuito `my_xor` usando portas básicas (AND, OR, NOT).
- [x] Implementado conversor binário para gray de 4 bits (`bin2gray4`) utilizando o `my_xor`.
- [x] Implementado gerador de paridade de 8 bits (`parity8_gen`) em cascata de XORs.
- [x] Implementado detector de zero de 8 bits (`z_detect8_v1`) com porta NOR de 8 entradas.
- [x] Atualizado o arquivo `CONTRATO_TESTES v0.2.md` com 18 vetores de teste totais.
- [x] Atualizado arquivo de `evidencias/S2/` e `logs/LABORATORIO_LOG_S2.md`.

---

## 3) O que foi testado (e como)
* **Bin2Gray:** Testados 8 vetores (bordas, alternâncias e blocos). Sucesso em todos os casos (ex: A=F -> F=8).
* **Paridade:** Validados casos par e ímpar com 8 bits. Testada a "injeção de erro" mudando um bit e observando a inversão da saída P.
* **Z-Det:** Confirmado que a saída Z=1 apenas quando a entrada é estritamente 00.

---

## 4) O que falhou

| Falha ID | Caso | Sintoma | Esperado | Observado | Hipótese | Próximo teste/ação |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| F-001 | TC-001 | Fio Laranja no pino A | Sinal verde | Fio Laranja | Pino com 1 bit para cabo de 4 bits. | Alterar Bit Width do Pino A para 4. |
| F-002 | TC-008 | Saída incorreta Gray | Resultado "8" | Resultado "F" | Conexão invertida no Splitter. | Revisar mapeamento do Splitter. |
| F-003 | TC-013 | Fio Vermelho | Propagação ok | Fio Vermelho | `my_xor` esperando 8 bits em vez de 1. | Definir Pins do `my_xor` como 1 bit. |
| F-004 | TC-014 | Valor "E" na saída | Hexadecimal | Caractere "E" | Fan-out menor que o nbr de bits. | Reconfigurar Fan-out para 8. |

> Não houve falhas críticas. Todas as ocorrências foram corrigidas durante o desenvolvimento.

---

## 5) Evidências
* **Prints de testes:** Localizados em `evidencias/S2/`
* **Contrato de testes:** [CONTRATO_TESTES v0.2.md](../tests/CONTRATO_TESTES%20v0.2.md)
* **Commit final:** `feat(codes4): finalize gray, parity and z-detect logic`

---

## 6) Decisões tomadas
* Padronização dos Splitters: Bit 0 (topo) e Bit 3/7 (base).
* Representação de 8 bits sempre com 2 dígitos hexadecimais (ex: 03h).

---

## 7) Próximos passos
* **Semana S3:** Início do bloco `arith4` (Somadores e Subtratores).
