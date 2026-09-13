# 📊 Calculadora do Fator R — Simples Nacional

Aplicação web interativa e responsiva desenvolvida para simulação e planejamento tributário estratégico no **Simples Nacional**, fundamentada na **Lei Complementar nº 123/2006** e na **Resolução CGSN nº 140/2018**.

A ferramenta analisa a relação entre a massa salarial (folha de pagamento/pró-labore) e o faturamento bruto acumulado de empresas de prestação de serviços, determinando se a tributação ocorrerá pelas alíquotas reduzidas do **Anexo III** ou pelas alíquotas do **Anexo V**.

---

## 🛠️ Funcionalidades Principais

- **Cálculo Dinâmico do Fator R:** Processamento instantâneo da razão percentual ($\text{Fator R} = \frac{\text{Folha 12}}{\text{RBT12}} \times 100$).
- **Diagnóstico Tributário em Tempo Real:**
  - **Fator R $\ge$ 28%:** Recomenda o **Anexo III** (alíquota inicial a partir de 6,00%), destacando a economia mensal projetada no DAS.
  - **Fator R < 28%:** Identifica o enquadramento no **Anexo V** (alíquota inicial a partir de 15,50%) e calcula exatamente o valor adicional necessário na folha/pró-labore acumulado para atingir a migração.
- **Validações e alertas:**
  - Aviso quando a **RBT12 ultrapassa o teto do Simples Nacional (R$ 4.800.000,00)** — Art. 3º, II, LC 123/2006.
  - Alertas para valores zerados (RBT12, Folha 12, FSPA/RPAr) que acionam regras especiais, evitando que o enquadramento seja interpretado como cálculo "normal".
  - Consistência do campo **meses em atividade** (intervalo 2 a 12).
- **Autoverificação interna:** ao carregar, um autoteste valida os cálculos-chave (Fator R, faixa, alíquota efetiva, DAS e economia vs Anexo V) e exibe o resultado no rodapé.
- **Formatação de Moeda Brasileira (pt-BR):** Máscara automática de entrada para valores monetários (`R$`).
- **Proteção básica contra cópia do código-fonte:** bloqueio de atalhos de inspeção (`F12`, `Ctrl+U`, `Ctrl+S`, `Ctrl+Shift+I/J/C`) e do menu de contexto, além de `user-select: none` na página. O **conteúdo visível permanece selecionável e copiável** (resultados do DAS, dicas, avisos, textos e valores digitados) via classe `copyable`.
- **Design System Moderno:** Layout responsivo baseado na paleta Slate/Dark Navy e Esmeralda.

> **Observação:** essa proteção é uma barreira contra cópia acidental/inspeção casual. Como todo código executado no navegador, o JavaScript é tecnicamente recuperável; o objetivo aqui é dificultar, não torná-lo hermético.

## 🔧 Correções desta versão

- **Bloqueio de código restaurado e refinado**: os atalhos de inspeção e o menu de contexto voltaram a ser bloqueados, mas mantendo a seleção/cópia do conteúdo visível liberada (resultados, avisos e campos).
- Corrigida a **dessincronização do comparativo** "Economia vs Anexo V": os valores estáticos embutidos no HTML divergiam do cálculo real do JS. Todos os resultados passaram a ser renderizados exclusivamente via JavaScript no carregamento.
- **Tratamento do teto do Simples Nacional** (RBT12 acima de R$ 4,8 mi) com alerta e cálculo exibido apenas como referência.
- **Validações de limites** e avisos para entradas zeradas/fora do intervalo.
- Autoteste interno de sanidade dos cálculos.

## 📂 Estrutura do Repositório

```text
fator-r/
├── index.html        # Arquivo principal (HTML5, CSS3 inline e JavaScript ES6)
└── README.md         # Documentação completa do repositório
```

*(Simulador com base na legislação vigente; confirme casos concretos com seu contador.)*