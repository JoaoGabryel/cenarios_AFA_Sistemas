1. Rotina: Inventário de Estoque
Descrição: 
- Cadastros produtos fictícios via importação XML 
- Realização de contagem física simulada 
- Lançamento do inventário no sistema 
- Geração de relatório de ajustes 
Validação BD: 
– Verificar consistência entre saldo contabilizado vs. 
saldo ajustado após validação. 
– Objetivo Final: Testar precisão na reconciliação de 
estoque físico x sistema.

# **Cenário RF01: Inventário de Estoque**

---

## **Caso de Teste CT_RF01_01: Importação de produtos via XML**

| ID | Descrição |
| :-- | :-- |
| CT_RF01_01 | Importar produtos fictícios via arquivo XML e validar o cadastro no sistema. |

### **Pré-condições**
- O sistema deve ter o módulo de inventário ativo.  
- O arquivo XML com produtos fictícios deve estar disponível.  
- O usuário deve possuir permissão para realizar importações.

### **Passos**
**DADO** que o usuário acessa o módulo de inventário do sistema  
**E** seleciona a opção de importação de produtos  
**QUANDO** importar o arquivo XML com 10 produtos fictícios  
**ENTÃO** os produtos devem ser cadastrados corretamente e o sistema exibe uma mensagem de sucesso.

### **Critérios de aceitação**
- Os produtos devem ser exibidos corretamente no sistema após a importação.  
- Uma mensagem de sucesso deve confirmar o término do processo.  
- Os dados devem ser gravados corretamente no banco de dados.

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/12S-7mQsuJ3kqzibcALpMsxauT58CDDhE/view?usp=sharing)

---

## **Caso de Teste CT_RF01_02: Importação de produtos via XML inválido**

| ID | Descrição |
| :-- | :-- |
| CT_RF01_02 | Tentar importar um arquivo XML inválido ou corrompido e verificar se o sistema trata o erro corretamente. |

### **Pré-condições**
- O módulo de inventário deve estar ativo.  
- O arquivo XML deve estar corrompido ou com estrutura inválida.  
- O usuário deve ter permissão de importação.

### **Passos**
**DADO** que o usuário acessa o módulo de inventário  
**E** seleciona a importação de produtos  
**QUANDO** importar um arquivo XML inválido  
**ENTÃO** o sistema deve rejeitar o arquivo, exibir erro, e não gravar nada no banco.

### **Critérios de aceitação**
- Nenhum produto deve ser gerado.  
- O erro deve ser claro e informativo.  
- Banco de dados não deve ser alterado.

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/16nyvMm0DhW-Gcx90TzZgfIA-TUA7HVb4/view?usp=drive_link)

---

## **Caso de Teste CT_RF01_03: Realizar contagem física simulada**

| ID | Descrição |
| :-- | :-- |
| CT_RF01_03 | Simular contagem física de produtos e validar atualização temporária de quantidades. |

### **Pré-condições**
- Produtos devem estar previamente cadastrados no sistema.  
- O usuário deve possuir permissão para registrar contagem.

### **Passos**
**DADO** que o usuário entra na rotina de contagem física  
**QUANDO** registrar a quantidade física dos produtos (ex.: 10 itens contados)  
**ENTÃO** o sistema deve salvar a contagem temporária e exibir resumo da conferência.

### **Critérios de aceitação**
- As quantidades contadas devem ser registradas corretamente.  
- O sistema deve permitir revisar e editar a contagem.  
- Nenhum ajuste deve ser aplicado antes da validação final.

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1e5d1ekhGE6-DO8S6Nf-kVfZ-W5XK1fG3/view?usp=drive_link)

---

## **Caso de Teste CT_RF01_04: Registrar contagem física com valores inconsistentes (negativo)**

| ID | Descrição |
| :-- | :-- |
| CT_RF01_04 | Registrar contagens com valores inconsistentes (ex.: valor negativo, não numérico). |

### **Pré-condições**
- Produtos cadastrados.  
- Usuário com permissão de contagem.

### **Passos**
**DADO** que o usuário acessa a contagem física  
**QUANDO** tentar inserir quantidade inválida (texto, negativo ou acima de limite)  
**ENTÃO** o sistema deve bloquear e exibir mensagem de erro.

### **Critérios de aceitação**
- Campos devem validar entrada.  
- Não deve permitir valores inválidos.  
- Nenhuma alteração temporária deve ser registrada.

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1JIqyRNuynllAU3JFIhjMc7DbM-rQcuwk/view?usp=drive_link)

---

## **Caso de Teste CT_RF01_05: Lançamento final do inventário**

| ID | Descrição |
| :-- | :-- |
| CT_RF01_05 | Registrar o inventário final e atualizar o estoque definitivo. |

### **Pré-condições**
- Contagem física finalizada.  
- Usuário com permissão de validação.

### **Passos**
**DADO** que o usuário acessa a tela de lançamento de inventário  
**QUANDO** confirmar a contagem física consolidada  
**ENTÃO** o sistema deve atualizar os estoques e registrar ajustes (positivos e negativos).

### **Critérios de aceitação**
- Estoque deve ser atualizado conforme contagem.  
- Ajustes devem ser gerados e salvos no histórico.  
- Deve ser exibida mensagem de sucesso.

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1e5d1ekhGE6-DO8S6Nf-kVfZ-W5XK1fG3/view?usp=drive_link)

---

## **Caso de Teste CT_RF01_06: Lançamento de inventário sem contagem (negativo)**

| ID | Descrição |
| :-- | :-- |
| CT_RF01_06 | Tentar lançar inventário sem contagem registrada. |

### **Pré-condições**
- Nenhuma contagem física registrada.

### **Passos**
**DADO** que o usuário abre a rotina de lançamento  
**QUANDO** tentar confirmar o inventário  
**ENTÃO** o sistema deve bloquear e solicitar contagem.

### **Critérios de aceitação**
- O lançamento deve ser impedido.  
- Mensagem deve orientar o usuário a realizar contagem.

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1MJXjtS7d_yMYu1wuW5HREzQ_kVYXEk6-/view?usp=drive_link)

---

## **Caso de Teste CT_RF01_07: Geração de relatório de ajustes**

| ID | Descrição |
| :-- | :-- |
| CT_RF01_07 | Gerar relatório final com diferenças entre estoque físico e estoque do sistema. |

### **Pré-condições**
- Inventário deve ter sido lançado e ajustado.

### **Passos**
**DADO** que o usuário acessa relatórios do inventário  
**QUANDO** gerar relatório de ajustes  
**ENTÃO** o sistema deve exibir divergências, ajustes aplicados e totais consolidados.

### **Critérios de aceitação**
- O relatório deve refletir todas as diferenças.  
- Deve permitir exportação (PDF/Excel).  
- Informações devem bater com o banco de dados.

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1BpAy_FNsF3T7E2fyobkJQW2myXIrAagn/view?usp=drive_link)

---

## **Caso de Teste CT_RF01_08: Validação do Banco de Dados**

| ID | Descrição |
| :-- | :-- |
| CT_RF01_08 | Validar consistência entre saldo contabilizado e saldo ajustado após a finalização do inventário. |

### **Pré-condições**
- Inventário concluído.  
- Ajustes registrados no BD.

### **Passos**
**DADO** que o inventário foi finalizado  
**QUANDO** consultar o banco de dados (tabela produto / estoq_pro)  
**ENTÃO** os saldos devem estar atualizados corretamente com base na contagem.

### **Critérios de aceitação**
- Nenhuma inconsistência entre sistema e BD.  
- Ajustes devem estar gravados e vinculados corretamente.  
- Saldos devem refletir o inventário final.

### **Evidência(s)**
[Vídeo](https://drive.google.com/file/d/1a3AF4AYLiyRpwoVE1tyOMpjHpe_C8Img/view?usp=drive_link)
[Vídeo](https://drive.google.com/file/d/1TIH5EunbX3rRnnylwsy6C-PuzGAUJfve/view?usp=drive_link)
