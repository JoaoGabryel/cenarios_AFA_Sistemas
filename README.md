# 📌 Cenários de Teste – Sistema ERP / PDV

**Acadêmicos:**  
- **Felipe Gustavo Ferreira Cruz – RA 13663**  
- **João Gabryel dos Santos Lima – RA 13459**

---

## **1. Rotina: Inventário de Estoque**

### 📄 Descrição
- Cadastro de produtos fictícios via importação XML  
- Realização de contagem física simulada  
- Lançamento do inventário no sistema  
- Geração de relatório de ajustes  

### 🗄️ Validação no Banco de Dados
- Verificar consistência entre **saldo contabilizado** e **saldo ajustado** após validação  

### 🎯 Objetivo Final
Garantir precisão na reconciliação entre **estoque físico** e **estoque registrado no sistema**.

---

## **2. Rotina: Processamento de Venda (PDV)**

### 📄 Descrição
- Iniciar nova venda com **5 itens**  
- Aplicar **desconto promocional** na venda  
- Finalizar com **pagamento misto** (70% cartão + 30% dinheiro)  
- Realizar fechamento de caixa com validação por tipo de documento  

### 🗄️ Validação no Banco de Dados
- Conferir integridade dos cálculos e registros financeiros  

### 🎯 Objetivo Final
Validar o **fluxo completo** de vendas e fechamento de caixa.

---

## **3. Rotina: Compra com Fornecedores**

### 📄 Descrição
- Cadastrar novo fornecedor  
- Gerar pedido de compra com **10 itens**  
- Simular contas a pagar em **5 parcelas**, pagando:
  - **1ª parcela** totalmente  
  - **2ª parcela** parcialmente  
- Realizar fechamento de caixa  

### 🗄️ Validação no Banco de Dados
- Confirmar atualização de estoque **somente para itens recebidos**  

### 🎯 Objetivo Final
Testar a gestão de **supply chain** e o controle de pagamentos **total e parcial**.

---

## **4. Rotina: Gestão de Clientes**

### 📄 Descrição
- Cadastrar **6 clientes** (PF e PJ)  
- Habilitar **limite de crédito** para 2 clientes  
- Adicionar dependentes para 2 clientes  
- Registrar compras:  
  - Para os 6 clientes  
  - Para dependentes dos clientes com dependentes  
- Para clientes com limite de crédito:  
  - 1 compra **dentro do limite**  
  - 1 compra **fora do limite**  
- Atualizar limite de crédito  
- Gerar relatório de contas a receber  

### 🗄️ Validação no Banco de Dados
- Verificar histórico de compras  
- Verificar bloqueios por limite de crédito  

### 🎯 Objetivo Final
Avaliar o controle de relacionamento e regras de crédito.

---

## **5. Rotina: Fechamento de Caixa**

### 📄 Descrição
- Simular operações em um único caixa  
- Gerar vendas com diferentes tipos de documentos  
- Realizar retiradas de valores  
- Fechar o caixa e conferir todos os documentos  
- Conciliar totais com o relatório de vendas  

### 🗄️ Validação no Banco de Dados
- Verificar equilíbrio entre movimentos financeiros e saldo contábil  

### 🎯 Objetivo Final
Garantir integridade do **fechamento financeiro diário**.
