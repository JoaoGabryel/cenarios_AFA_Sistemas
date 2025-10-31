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

## **Caso de Teste CT_RF01_01: Importação de produtos via XML**

| ID | Descrição |
| :-- | :-- |
| CT_RF01_01 | Importar produtos fictícios via arquivo XML e validar o cadastro no sistema. |

| **Pré-condições** |
| :-- |
| - O sistema deve ter o módulo de inventário ativo. <br> - O arquivo XML com produtos fictícios deve estar disponível. <br> - O usuário deve possuir permissão para realizar importações. |

| **Passos** |
| :-- |
| **DADO** que o usuário acessa o módulo de inventário do sistema <br> **E** seleciona a opção de importação de produtos <br> **QUANDO** importar o arquivo XML com 10 produtos fictícios <br> **ENTÃO** os produtos devem ser cadastrados corretamente e o sistema exibe uma mensagem de sucesso. |

| **Critérios de aceitação** |
| :-- |
| - Os produtos devem ser exibidos corretamente no sistema após a importação. <br> - Uma mensagem de sucesso deve confirmar o término do processo. <br> - Os dados devem ser gravados corretamente no banco de dados. |

| **Evidência(s)** |
| :--: |
| [Vídeo](https://drive.google.com/drive/u/0/folders/1Jv_mQUsgrOA1XcYj2tQ4ajIFsI45T-c7) |

---