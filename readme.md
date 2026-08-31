# 📊 Calculadora do Fator R — Simples Nacional

Aplicação web interativa e responsiva desenvolvida para simulação e planejamento tributário estratégico no **Simples Nacional**, fundamentada na **Lei Complementar nº 123/2006** e na **Resolução CGSN nº 140/2018**.

A ferramenta analisa a relação entre a massa salarial (folha de pagamento/pró-labore) e o faturamento bruto acumulado de empresas de prestação de serviços, determinando se a tributação ocorrerá pelas alíquotas reduzidas do **Anexo III** ou pelas alíquotas do **Anexo V**.

---

## 🛠️ Funcionalidades Principais

- **Cálculo Dinâmico do Fator R:** Processamento instantâneo da razão percentual ($\text{Fator R} = \frac{\text{Folha 12}}{\text{RBT12}} \times 100$).
- **Diagnóstico Tributário em Tempo Real:** 
  - **Fator R $\ge$ 28%:** Recomenda o **Anexo III** (alíquota inicial a partir de 6,00%), destacando a economia mensal projetada no DAS.
  - **Fator R < 28%:** Identifica o enquadramento no **Anexo V** (alíquota inicial a partir de 15,50%) e calcula exatamente o valor adicional necessário na folha/pró-labore acumulado para atingir a migração.
- **Formatação de Moeda Brasileira (pt-BR):** Máscara automática de entrada para valores monetários (`R$`).
- **Proteção de Código-Fonte:** Implementação de camadas de bloqueio contra cópia do código-fonte e atalhos de inspeção do navegador (`F12`, `Ctrl+U`, `Ctrl+Shift+I`, etc.), mantendo contudo a seleção/cópia de dados e textos visíveis liberada para uso pelo usuário.
- **Design System Moderno:** Layout responsivo baseado na paleta e estrutura visual corporativa do setor fiscal/contábil (Slate/Dark Navy e Esmeralda).

---

## 📂 Estrutura do Repositório

```text
fator-r/
├── index.html        # Arquivo principal (HTML5, CSS3 inline e JavaScript ES6)
└── README.md         # Documentação completa do repositório