3. Rotina: Compra com Fornecedores 
Descrição: 
- Cadastrar novo fornecedor 
- Gerar pedido de compra com 10 itens 
- Simular parcelamento de contas a pagar em 5 vezes e pagar a 
primeira parcela de forma total e a segunda de forma parcial; 
- Fechamento de caixa 
Validação BD: 
Confirmar atualização de estoque apenas para itens recebidos. 
Objetivo Final: Testar gestão de supply chain e controle de pagamento 
total e parcial.
# **Cenário RF03: Compra com Fornecedores**

---

## **Caso de Teste CT_RF03_01: Cadastrar novo fornecedor**

| ID | Descrição |
| :-- | :-- |
| CT_RF03_01 | Cadastrar um novo fornecedor no sistema. |

### **Pré-condições**
- Sistema com módulo de compras ativo.  
- Usuário com permissão de cadastro.  

### **Passos**
**DADO** que o usuário acessa o módulo de fornecedores  
**QUANDO** inserir os dados de um novo fornecedor  
**E** salvar o cadastro  
**ENTÃO** o fornecedor deve ser cadastrado com sucesso e exibido na lista de fornecedores.

### **Critérios de aceitação**
- O fornecedor deve aparecer imediatamente na listagem.  
- Dados devem ser gravados corretamente no banco.  
- Deve ser exibida mensagem de sucesso.  

### **Evidência(s)**
[Vídeo](https://docs.google.com/videos/d/1cvdcBARrWTFuYYa9JWJhQPV71yefFYyO_vujbjtYOE0/edit?usp=drive_link)

---

## **Caso de Teste CT_RF03_02: Gerar pedido de compra com 10 itens**

| ID | Descrição |
| :-- | :-- |
| CT_RF03_02 | Criar pedido de compra com 10 itens para fornecedor cadastrado. |

### **Pré-condições**
- Fornecedor cadastrado.  
- Produtos disponíveis para compra.  

### **Passos**
**DADO** que o usuário acessa o módulo de pedidos de compra  
**QUANDO** selecionar um fornecedor  
**E** adicionar 10 itens ao pedido  
**E** salvar o pedido  
**ENTÃO** o pedido deve ser gerado com os 10 itens registrados corretamente.

### **Critérios de aceitação**
- Todos os itens devem estar listados no pedido.  
- Quantidades e valores devem ser calculados corretamente.  
- Pedido deve ficar disponível para consulta posterior.  

### **Evidência(s)**
[Vídeo](https://docs.google.com/videos/d/1WiIwLm-nW8dM-hNSwsNsABKYl_0XJCIGQE0NhKppNjA/edit?usp=drive_link)

---

## **Caso de Teste CT_RF03_03: Simular parcelamento e pagamentos**

| ID | Descrição |
| :-- | :-- |
| CT_RF03_03 | Parcelar contas a pagar em 5 vezes e registrar pagamento total da primeira parcela e parcial da segunda. |

### **Pré-condições**
- Pedido de compra registrado.  
- Parcelamento habilitado no sistema.  

### **Passos**
**DADO** que o usuário acessa as contas a pagar do pedido  
**QUANDO** parcelar o valor total em 5 vezes  
**E** registrar o pagamento total da primeira parcela  
**E** registrar pagamento parcial da segunda parcela  
**ENTÃO** o sistema deve atualizar corretamente o status de cada parcela.

### **Critérios de aceitação**
- 1ª parcela com status **PAGA**.  
- 2ª parcela como **PAGAMENTO PARCIAL** com saldo restante.  
- Demais parcelas como **PENDENTES**.  
- Movimentações financeiras registradas corretamente no BD.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1fohYli5AlHly1iUG8f6i9le7zLlYNxbz/view?usp=drive_link)

---

## **Caso de Teste CT_RF03_04: Fechamento de caixa**

| ID | Descrição |
| :-- | :-- |
| CT_RF03_04 | Realizar fechamento de caixa após os pagamentos. |

### **Pré-condições**
- Pagamentos registrados (parcial e total).  
- Caixa aberto.  

### **Passos**
**DADO** que o usuário acessa o módulo de fechamento de caixa  
**QUANDO** realizar o fechamento  
**ENTÃO** o sistema deve confirmar o fechamento e exibir os valores consolidados.

### **Critérios de aceitação**
- Caixa deve fechar sem inconsistências.  
- Valores registrados devem bater com os pagamentos feitos.  
- Deve ser exibida mensagem de fechamento concluído.

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1eOBAz7Zq2lkPZIQV7_iy7kfLTjjYpD8E/view?usp=drive_link)

---

## **Caso de Teste CT_RF03_05: Validação no Banco de Dados**

| ID | Descrição |
| :-- | :-- |
| CT_RF03_05 | Validar atualização de estoque somente para itens recebidos. |

### **Pré-condições**
- Pedido de compra registrado.  
- Itens com status de recebidos e não recebidos.  

### **Passos**
**DADO** que o pedido de compra foi emitido  
**QUANDO** consultar o banco de dados na tabela de produtos  
**ENTÃO** apenas os itens marcados como recebidos devem ter atualizado o estoque.

### **Critérios de aceitação**
- Nenhuma alteração no estoque para itens não recebidos.  
- Itens recebidos devem refletir aumento no estoque.  
- Registros devem estar devidamente vinculados ao pedido.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1q988SwAZBsEGnIKqCRxoiybPjzRyMGap/view?usp=drive_link)
