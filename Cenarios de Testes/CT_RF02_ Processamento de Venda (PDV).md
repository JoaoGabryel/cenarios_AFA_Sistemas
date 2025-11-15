2. Rotina: Processamento de Venda (PDV) 
Descrição: 
- Iniciar nova venda com 5 itens 
- Aplicar desconto promocional em 1 item 
- Finalizar venda com pagamento misto (cartão 70% + 
dinheiro 30%) 
- Fechamento de caixa e validação por tipo de documento
Validação BD: 
– Checar integridade dos cálculos e registros financeiros. 
– Objetivo Final: Validar fluxo completo de vendas e caixa.

# **Cenário RF02: Processamento de Venda (PDV)**

---

## **Caso de Teste CT_RF02_01: Iniciar nova venda com 5 itens**

| ID | Descrição |
| :-- | :-- |
| CT_RF02_01 | Registrar uma nova venda contendo 5 itens no módulo PDV. |

### **Pré-condições**
- Sistema com módulo PDV ativo.  
- Produtos cadastrados para venda.  
- Caixa aberto.  

### **Passos**
**DADO** que o usuário acessa o módulo PDV  
**E** inicia uma nova venda  
**QUANDO** o usuário adicionar 5 itens diferentes ao carrinho  
**ENTÃO** os itens devem ser registrados corretamente e o total da venda deve ser calculado automaticamente.

### **Critérios de aceitação**
- Todos os 5 itens devem ser exibidos corretamente no carrinho.  
- Quantidades e valores devem ser somados corretamente.  
- O PDV deve atualizar o total de forma automática e precisa.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1F1bvwLGbqAiAmATXZs5m6MkNcAFYhlTc/view?usp=sharing)

---

## **Caso de Teste CT_RF02_02: Aplicar desconto promocional em 1 item**

| ID | Descrição |
| :-- | :-- |
| CT_RF02_02 | Aplicar desconto promocional em um item do carrinho. |

### **Pré-condições**
- Venda em andamento com itens adicionados.  
- Política de desconto ativa.  
- Usuário com permissão para aplicar descontos.  

### **Passos**
**DADO** que existe uma venda em andamento com itens cadastrados  
**QUANDO** o usuário selecionar um item do carrinho  
**E** aplicar um desconto promocional (ex.: 10%)  
**ENTÃO** o desconto deve ser aplicado corretamente e o total atualizado.

### **Critérios de aceitação**
- Percentual de desconto deve ser aplicado apenas ao item selecionado.  
- O total da venda deve refletir a redução no valor.  
- O PDV deve exibir mensagem confirmando o desconto aplicado.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1Zq-lt9MmpESbBQYuxg43J6YVycW3Aivb/view?usp=sharing)

---

## **Caso de Teste CT_RF02_03: Finalizar venda com pagamento misto (70% cartão, 30% dinheiro)**

| ID | Descrição |
| :-- | :-- |
| CT_RF02_03 | Finalizar venda utilizando duas formas de pagamento: cartão e dinheiro. |

### **Pré-condições**
- Venda em andamento.  
- Caixa aberto.  
- PDV deve suportar pagamento misto.  

### **Passos**
**DADO** que o usuário está finalizando uma venda  
**QUANDO** selecionar pagamento em cartão para 70% do valor  
**E** selecionar pagamento em dinheiro para 30% restantes  
**ENTÃO** a venda deve ser concluída e os dois pagamentos registrados corretamente.

### **Critérios de aceitação**
- Os percentuais devem ser aplicados corretamente.  
- O sistema deve validar e registrar ambas as formas de pagamento.  
- A venda deve ser finalizada com sucesso.  
- Deve gerar comprovante/registro de pagamento múltiplo.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1X37sq-iUuB7aUV5Bf3HErGDwMRERPuWk/view?usp=sharing)

---

## **Caso de Teste CT_RF02_04: Fechamento de caixa e validação por tipo de documento**

| ID | Descrição |
| :-- | :-- |
| CT_RF02_04 | Fechar o caixa e validar os totais por tipo de documento (cartão e dinheiro). |

### **Pré-condições**
- Vendas registradas no caixa.  
- Usuário com permissão para fechamento.  
- Sistema deve estar com todos os pagamentos processados.  

### **Passos**
**DADO** que o usuário acessa a rotina de fechamento de caixa  
**QUANDO** realizar o fechamento  
**ENTÃO** os totais devem ser exibidos por tipo de documento  
**E** os valores devem estar consistentes com as vendas realizadas.

### **Critérios de aceitação**
- Totais devem ser gerados separados por tipo de pagamento.  
- Fechamento deve ser concluído sem inconsistências.  
- Sistema deve exibir mensagem de fechamento realizado com sucesso.  

### **Evidência(s)**
[Vídeo]()

---

## **Caso de Teste CT_RF02_05: Validação no Banco de Dados**

| ID | Descrição |
| :-- | :-- |
| CT_RF02_05 | Validar os registros financeiros no BD após finalização da venda e fechamento de caixa. |

### **Pré-condições**
- Venda finalizada e caixa fechado.  
- Acesso às tabelas financeiras no BD.  

### **Passos**
**DADO** que a venda foi concluída e o caixa fechado  
**QUANDO** consultar o BD nas tabelas de movimentação financeira  
**ENTÃO** os registros devem apresentar:  
- valores corretamente calculados  
- formas de pagamento separadas  
- total final igual ao registrado no PDV

### **Critérios de aceitação**
- Nenhuma divergência entre PDV e banco de dados.  
- Registros devem estar completos e consistentes.  
- Todos os documentos financeiros devem estar gravados corretamente.  

### **Evidência(s)**
[Vídeo]()

