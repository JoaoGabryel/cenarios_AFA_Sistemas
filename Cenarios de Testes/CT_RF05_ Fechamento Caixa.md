6. Rotina: Fechamento Caixa
Descrição: 
- Simular operações de 3 caixas simultâneas 
- Gerar vendas com tipos de documentos 
- Realizar retirar valores 
- Fechar o caixa e conferir os tipos de documentos
- Conciliar totais com relatório de vendas 
Validação BD:
Verificar equilíbrio entre movimentos financeiros e saldo 
contábil. 
Objetivo Final: Garantir integridade do fechamento 
financeiro diário.

# **Cenário RF06: Fechamento de Caixa**

---

## **Caso de Teste CT_RF06_01: Simular operações em 3 caixas simultâneas**

| ID | Descrição |
| :-- | :-- |
| CT_RF06_01 | Realizar operações simultâneas em 3 caixas diferentes. |

### **Pré-condições**
- Módulo de caixa ativo.  
- 3 caixas configurados e disponíveis.  
- Usuário com permissão de operação em caixa.  

### **Passos**
**DADO** que o sistema possui 3 caixas disponíveis  
**QUANDO** o usuário abrir 3 sessões de caixa simultaneamente  
**E** realizar vendas e movimentações em cada caixa  
**ENTÃO** todas as operações devem ser registradas corretamente e vinculadas ao caixa correspondente.

### **Critérios de aceitação**
- Cada caixa deve registrar apenas suas próprias operações.  
- Não deve haver mistura de registros entre caixas.  
- Operações devem aparecer no histórico individual de cada caixa.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1c3QrDaD2K0ygVAXqHdxyacbBYjyHC0cE/view?usp=drive_link)
Não foi possivel abrir mais de um caixa.
---

## **Caso de Teste CT_RF06_02: Gerar vendas com diferentes tipos de documentos**

| ID | Descrição |
| :-- | :-- |
| CT_RF06_02 | Registrar vendas utilizando diferentes tipos de documentos fiscais. |

### **Pré-condições**
- Caixas abertos.  
- Tipos de documentos configurados (ex.: NF-e, NFC-e, Cupom).  

### **Passos**
**DADO** que os caixas estão abertos  
**QUANDO** o usuário registrar vendas usando diferentes tipos de documentos fiscais  
**ENTÃO** os documentos devem ser gerados e armazenados corretamente no sistema.

### **Critérios de aceitação**
- Cada documento deve ser registrado com seu tipo correto.  
- Número fiscal deve ser gerado conforme legislação.  
- Documento deve aparecer nos relatórios e no histórico do caixa.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/16Af3TK_eJ9dKRlr8_w1-HbYbveZKHmx-/view?usp=drive_link)

---

## **Caso de Teste CT_RF06_03: Realizar retiradas de valores**

| ID | Descrição |
| :-- | :-- |
| CT_RF06_03 | Efetuar retiradas de valores dos caixas. |

### **Pré-condições**
- Caixas abertos.  
- Usuário com permissão para retirada.  

### **Passos**
**DADO** que existem caixas abertos  
**QUANDO** o usuário realizar retiradas de valores  
**E** registrar o motivo e o valor da retirada  
**ENTÃO** as retiradas devem ser registradas corretamente no sistema.

### **Critérios de aceitação**
- Retiradas devem constar no histórico do caixa.  
- Movimentações devem refletir saldo reduzido.  
- Motivo deve ser registrado corretamente no BD.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1UyneMndumbzi0IbCcLIYCJpOXLuGFF9G/view?usp=drive_link)

---

## **Caso de Teste CT_RF06_04: Fechar o caixa e conferir tipos de documentos**

| ID | Descrição |
| :-- | :-- |
| CT_RF06_04 | Realizar fechamento dos caixas e validar documentos. |

### **Pré-condições**
- Caixas com movimentações realizadas.  

### **Passos**
**DADO** que os caixas possuem vendas e retiradas registradas  
**QUANDO** o usuário realizar o fechamento de cada caixa  
**E** conferir os tipos de documentos registrados  
**ENTÃO** o fechamento deve ser concluído e os documentos listados corretamente.

### **Critérios de aceitação**
- Fechamento deve gerar resumo com todos os documentos e valores.  
- Documentos devem corresponder ao que foi registrado no caixa.  
- Sistema deve confirmar fechamento com sucesso.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/10PDcmBT-ABBdsBgR-eaj3mS6KXw3iKid/view?usp=drive_link)

---

## **Caso de Teste CT_RF06_05: Conciliar totais com relatório de vendas**

| ID | Descrição |
| :-- | :-- |
| CT_RF06_05 | Conciliar os totais do fechamento com o relatório oficial de vendas. |

### **Pré-condições**
- Fechamento de caixa realizado.  
- Relatório de vendas disponível.  

### **Passos**
**DADO** que o fechamento dos caixas foi concluído  
**QUANDO** o usuário gerar o relatório de vendas  
**E** comparar com os totais consolidados do fechamento  
**ENTÃO** todos os valores devem estar consistentes.

### **Critérios de aceitação**
- Totais de vendas devem ser idênticos entre relatório e fechamento.  
- Desvios não devem ocorrer, exceto por erro previamente registrado.  
- Sistema deve garantir integridade da conciliação.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1qJ85LEPqQEfvW_iCpxeFcW_SFpbUEup4/view?usp=drive_link)

---

## **Caso de Teste CT_RF06_06: Validação no Banco de Dados**

| ID | Descrição |
| :-- | :-- |
| CT_RF06_06 | Validar equilíbrio entre movimentos financeiros e saldo contábil. |

### **Pré-condições**
- Caixas fechados.  
- Movimentações registradas (vendas, retiradas, documentos).  

### **Passos**
**DADO** que o fechamento foi concluído  
**QUANDO** consultar o banco de dados  
**ENTÃO** o saldo final deve refletir exatamente:  
- vendas realizadas  
- retiradas registradas  
- documentos fiscais emitidos  
- saldo contábil calculado

### **Critérios de aceitação**
- BD deve refletir fielmente todas as operações.  
- Saldos devem estar alinhados entre sistema e BD.  
- Nenhuma inconsistência deve ser encontrada.  

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1WX9u1kq8reevwaciSGQjkLy-QLzQMSMh/view?usp=drive_link)

