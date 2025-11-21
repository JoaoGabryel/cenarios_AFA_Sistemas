4. Rotina: Gestão de Clientes
Descrição:
- Cadastrar 6 clientes (PJ e PF) 
- Habilitar limite de credito para 2 clientes
- Acrescentar dependente para 2 clientes
- Registrar compras para os 6 clientes, sendo em nome do cliente e 
dependente par os 2 clientes com dependentes. Para os 2 clientes com limite 
realizar compra dentro do limite para um e fora do limite para o outro 
- Atualizar limite de crédito 
- Gerar relatório de contas a receber 
Validação BD: 
Verificar histórico de compras e bloqueios por crédito. 
Objetivo Final: Validar controle de relacionamento e regras de crédito.

# **Cenário RF04: Gestão de Clientes**

---

## **Caso de Teste CT_RF04_01: Cadastrar 6 clientes (PJ e PF)**

| ID | Descrição |
| :-- | :-- |
| CT_RF04_01 | Cadastrar 6 clientes, sendo 3 pessoas jurídicas (PJ) e 3 pessoas físicas (PF). |

### **Pré-condições**
- Módulo de clientes ativo.  
- Usuário com permissão de cadastro.  

### **Passos**
**DADO** que o usuário acessa o módulo de clientes  
**QUANDO** cadastrar 3 clientes PJ  
**E** cadastrar 3 clientes PF  
**ENTÃO** todos os 6 clientes devem ser registrados corretamente no sistema.

### **Critérios de aceitação**
- Todos os clientes devem aparecer na listagem.  
- Dados devem ser armazenados corretamente no banco.  
- Deve ser exibida mensagem de cadastro concluído.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1-JlIohhocNu1eFJ8nQ1f7vGEjCzw5Xx5/view?usp=drive_link)

---

## **Caso de Teste CT_RF04_02: Habilitar limite de crédito para 2 clientes**

| ID | Descrição |
| :-- | :-- |
| CT_RF04_02 | Configurar limite de crédito para 2 clientes previamente cadastrados. |

### **Pré-condições**
- Clientes cadastrados no sistema.  
- Permissão para editar regras financeiras.  

### **Passos**
**DADO** que existem clientes cadastrados  
**QUANDO** o usuário selecionar 2 clientes  
**E** habilitar e definir limite de crédito  
**ENTÃO** o limite deve ser salvo e exibido corretamente no cadastro.

### **Critérios de aceitação**
- Limite exibido no perfil do cliente.  
- Valor deve ser persistido no banco de dados.  
- Sistema deve permitir edição futura do limite.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/101MHoEYnrLtNEkmZKtYMzyakkneJq7Vb/view?usp=drive_link)

---

## **Caso de Teste CT_RF04_03: Acrescentar dependente para 2 clientes**

| ID | Descrição |
| :-- | :-- |
| CT_RF04_03 | Adicionar dependentes vinculados a 2 clientes. |

### **Pré-condições**
- Clientes cadastrados como PF.  
- Usuário com permissão para adicionar dependentes.  

### **Passos**
**DADO** que o usuário acessa o cadastro de clientes  
**QUANDO** selecionar 2 clientes  
**E** adicionar dependentes vinculados  
**ENTÃO** os dependentes devem ser cadastrados e exibidos na listagem de vínculos.

### **Critérios de aceitação**
- Dependentes devem aparecer associados ao cliente.  
- Banco de dados deve registrar a relação cliente → dependente.  
- Deve permitir compras futuras em nome dos dependentes.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1q2cU9h_3w-TduKSMcS17UE40eHbLnjeC/view?usp=drive_link)

---

## **Caso de Teste CT_RF04_04: Registrar compras para os 6 clientes e dependentes**

| ID | Descrição |
| :-- | :-- |
| CT_RF04_04 | Registrar compras para todos os clientes e dependentes. |

### **Pré-condições**
- Clientes cadastrados.  
- Dependentes vinculados a 2 clientes.  
- Produtos disponíveis.  

### **Passos**
**DADO** que o usuário acessa o módulo de vendas  
**QUANDO** registrar compras para 4 clientes sem dependentes  
**E** registrar compras para 2 clientes com dependentes  
**E** registrar compras também para os dependentes  
**ENTÃO** todas as compras devem ser registradas corretamente.

### **Critérios de aceitação**
- Compras vinculadas corretamente ao cliente ou dependente.  
- Histórico deve ser exibido no módulo do cliente.  
- Valores devem refletir na movimentação financeira.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1dHcabs2Eak0vu9kFlT23uHVMdQN_kCyB/view?usp=drive_link)

---

## **Caso de Teste CT_RF04_05: Realizar compra dentro e fora do limite de crédito**

| ID | Descrição |
| :-- | :-- |
| CT_RF04_05 | Testar o comportamento do sistema em compras dentro e fora do limite. |

### **Pré-condições**
- Limite de crédito habilitado para 2 clientes.  
- Clientes com compras registradas.  

### **Passos**
**DADO** que o usuário possui 2 clientes com limite habilitado  
**QUANDO** realizar uma compra dentro do limite para o Cliente A  
**ENTÃO** a compra deve ser aprovada  
**QUANDO** realizar uma compra que exceda o limite para o Cliente B  
**ENTÃO** o sistema deve bloquear a compra ou gerar aviso de crédito excedido.

### **Critérios de aceitação**
- Consumo de crédito deve ser atualizado.  
- Cliente dentro do limite deve ter compra aprovada.  
- Cliente fora do limite deve ser bloqueado ou avisado conforme regra do sistema.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1ayC0jJiSM92JRyLKLy0hY3ZkgESpR5DN/view?usp=drive_link)

---

## **Caso de Teste CT_RF04_06: Atualizar limite de crédito**

| ID | Descrição |
| :-- | :-- |
| CT_RF04_06 | Alterar o limite de crédito de um cliente. |

### **Pré-condições**
- Cliente com limite já habilitado.  

### **Passos**
**DADO** que o usuário acessa o cadastro do cliente  
**QUANDO** aumentar ou reduzir o limite de crédito  
**E** salvar a atualização  
**ENTÃO** o novo limite deve ser aplicado e refletido imediatamente.

### **Critérios de aceitação**
- Banco de dados deve refletir o novo valor.  
- Histórico de alterações deve ser mantido (se o sistema possuir esse recurso).  
- Compras futuras devem respeitar o novo limite.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1Y1zLVl-1cygGXYDuUCNXiEq9YBkPBcMA/view?usp=drive_link)

---

## **Caso de Teste CT_RF04_07: Gerar relatório de contas a receber**

| ID | Descrição |
| :-- | :-- |
| CT_RF04_07 | Gerar relatório de contas a receber. |

### **Pré-condições**
- Clientes com compras registradas.  
- Pagamentos pendentes ou parcialmente pagos.  

### **Passos**
**DADO** que o usuário acessa o módulo de relatórios  
**QUANDO** selecionar “Contas a Receber”  
**E** gerar relatório  
**ENTÃO** o relatório deve listar corretamente os valores pendentes de cada cliente.

### **Critérios de aceitação**
- Relatório deve exibir os valores por cliente e dependente.  
- Total consolidado deve estar correto.  
- Deve permitir exportação (PDF/Excel), se disponível.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1kiH37zS_h986ZIRspfi-mvDd1ltSOPCa/view?usp=drive_link)

---

## **Caso de Teste CT_RF04_08: Validação no Banco de Dados**

| ID | Descrição |
| :-- | :-- |
| CT_RF04_08 | Validar histórico de compras e regras de crédito no banco de dados. |

### **Pré-condições**
- Compras registradas.  
- Limites configurados.  
- Bloqueios aplicados quando necessário.  

### **Passos**
**DADO** que todas as operações de clientes foram concluídas  
**QUANDO** consultar o BD  
**ENTÃO** deve ser possível verificar:  
- compras vinculadas corretamente  
- dependentes associados  
- limites e consumo de crédito  
- bloqueios por crédito excedido

### **Critérios de aceitação**
- Nenhuma inconsistência entre sistema e banco.  
- Registros financeiros devem refletir fielmente as operações realizadas.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1Mm1FF_hQpDym89XKCMwaTdcsPnm5iw9n/view?usp=drive_link)
