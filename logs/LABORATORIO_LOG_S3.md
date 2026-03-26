# LOG_PROJETO — Semana SX (LD1)
**Grupo:** GXX
**Integrantes presentes:** Nome1, Nome2, Nome3
**Data:** YYYY-MM-DD
**Repositório/Commit base:** <hash ou link>
**Arquivo Logisim:** <arquivo.circ>
**Milestone da semana:** M? (ex.: M0 esqueleto + contrato v0.1)
---

## 1) Objetivo do encontro (1–2 linhas)
Ex.: Fechar M0: esqueleto do ULA4_core + padronização do contrato de
testes v0.1 + evidências.

---

## 2) O que foi feito (bullet curto)
- [ ] Criado/ajustado circuito `ULA4_core` com pinos A, B, OP, F, C, V,
Z (larguras corretas).
- [ ] Criado `CONTRATO_TESTES.md` v0.1.
- [ ] Adicionados N casos iniciais (TC-001..TC-00N).
- [ ] Evidências coletadas (print + commit).
---

## 3) O que foi testado (e como)
> Pode ser “testes de papel” na Semana 1 (formato e cobertura), ou
testes no Logisim quando houver lógica.
- Testes executados:
- TC-001 .. TC-008 (formato e cobertura de OP/hex)
- Critério usado:
- Conferência de formato (hex 1 dígito para A/B; 2 dígitos para F; OP
0..7)
- Campos TBD com justificativa
---

## 4) O que falhou (se houver) — “testado vs falhou”
> Se não houve falha, escreva “Sem falhas nesta semana” e explique por
quê (ex.: só esqueleto/template).

| Falha ID | Caso (TC-xxx) | Sintoma | Esperado | Observado | Hipótese
| Próximo teste/ação |
|---------|----------------|---------|----------|-----------|----------
|--------------------|
| F-001 | TC-003 | Campo Evidência vazio | Evidência
preenchida | vazio | esquecimento de padrão | atualizar tabela + commit
|

---
## 5) Evidências (links/arquivos)
- Print esqueleto: `evidencias/SX/esqueleto.png`
- Print tabela/contrato: `evidencias/SX/CONTRATO_TESTES.png`
- Commit(s): `<hash1>`, `<hash2>`
- (Opcional) Demo no laboratório: “apresentado ao monitor em HH:MM”
---

## 6) Decisões tomadas (curto)
- Padrão de hex: maiúsculas, sem `0x`.
- TBD permitido somente com justificativa e gatilho de fechamento.
- Saídas stub (F/C/V/Z) mantidas em 0 enquanto não houver
implementação.
---

## 7) Próximos passos (ponte para a próxima semana)
- Semana S(X+1): atualizar casos TBD quando operações forem
definidas/implementadas.
- Preparar quiz pré-aula da semana seguinte.