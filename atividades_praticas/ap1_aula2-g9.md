## Atividade Prática 1 - Grupo 9 - 17/03/2025

**Problema escolhido:** Software para uma geladeira inteligente.

### Requisitos Funcionais

| ID | Descrição |
|:---:|:---|
| RF01 | O usuário deve conseguir visualizar em tempo real as temperaturas atuais de cada compartimento da geladeira (refrigerador e freezer). |
| RF02 | O sistema deve ajustar automaticamente as temperaturas internas da geladeira conforme necessário. |
| RF03 | O usuário deve ser capaz de configurar manualmente as temperaturas desejadas para cada compartimento da geladeira. |
| RF04 | O sistema deve identificar e catalogar os alimentos armazenados na geladeira. |
| RF05 | O sistema deve monitorar o estoque de alimentos e notificar o usuário quando identificar quantidades baixas ou esgotamento de itens específicos. |
| RF06 | O usuário deve ser capaz de cadastrar, gerenciar e visualizar itens de uma lista de compras. |

### Requisitos de Qualidade

| ID | Categoria | Descrição | Relação com Requisitos Funcionais |
|:---:|:---|:---|:---|
| RQ01 | Compatibilidade | O sistema deve ser compatível com smartphones iOS e Android, oferecendo sincronização em tempo real entre a interface da geladeira e o dispositivo móvel. | RF01, RF03, RF04, RF05 e RF06 |
| RQ02 | Implementação | O sistema deve ser desenvolvido em Rust. | RF01, RF02, RF03, RF04, RF05 e RF06 |
| RQ03 | Segurança | O sistema deve implementar mecanismos de proteção de dados em conformidade com a LGPD. | RF04, RF05 e RF06 |
| RQ04 | Usabilidade | O sistema deve permitir que o usuário escute informações (texto para voz) e controle a geladeira através de comandos falados (reconhecimento de voz). | RF01, RF03, RF04, RF05 e RF06 |
| RQ05 | Eficiência | O sistema deve consumir no máximo 1GB de RAM. | RF01, RF02, RF03, RF04, RF05 e RF06 |
| RQ06 | Usabilidade | O sistema deve apresentar as temperaturas em graus Celsius como unidade padrão. | RF01, RF02 e RF03 |
| RQ07 | Integrabilidade | O sistema da geladeira deve se conectar à Internet via WiFi para integração com o aplicativo móvel. | RF01, RF03, RF04, RF05 e RF06 |
| RQ08 | Modificabilidade | O sistema deve implementar uma arquitetura orientada a objetos com alto grau de coesão e baixo acoplamento entre seus componentes. | RF01, RF02, RF03, RF04, RF05 e RF06 |
| RQ09 | Testabilidade | O sistema deve ser desenvolvido seguindo os princípios SOLID da orientação a objetos. | RF01, RF02, RF03, RF04, RF05 e RF06 |
| RQ10 | Sustentabilidade | O sistema da geladeira deve atender aos critérios de eficiência energética classe A conforme a classificação do INMETRO. | RF02, RF03 e RF05 |
| RQ11 | Implantação | O sistema deve utilizar processamento em nuvem para identificar e catalogar os alimentos armazenados na geladeira. | RF04 |
