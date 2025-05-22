# Documento de Arquitetura de Software

## 1. Visão Geral do Sistema
- **Nome do sistema**: Aplicativo de Sustentabilidade Pessoal.
- **Objetivo**: Ajudar os usuários a adotarem práticas sustentáveis no dia a dia, incentivando hábitos conscientes e responsáveis com o meio ambiente.
- **Escopo**: O sistema consiste em um aplicativo mobile para dispositivos Android e iOS, que oferece funcionalidades como o envio de notificações diárias com dicas sustentáveis, definição de metas de consumo consciente, configuração de lembretes para ações sustentáveis, localização de pontos de coleta e acesso a um guia interativo sobre o descarte correto de resíduos.

## 2. Requisitos

### 2.1 Requisitos Funcionais

Para a 1ª iteração do sistema em questão, foram selecionados os seguintes requisitos funcionais:

| ID | Requisito |
|----|------------|
| RF02 | O aplicativo deve enviar notificações diárias aos usuários contendo dicas de práticas sustentáveis que possam ser aplicadas no cotidiano. |
| RF03 | O aplicativo deve permitir que o usuário localize ecopontos, pontos de coleta de eletrônicos e outros locais relacionados à sustentabilidade com base em sua localização geográfica. |
| RF04 | O aplicativo deve disponibilizar um guia interativo que auxilie o usuário na separação correta de diferentes tipos de resíduos (orgânicos, recicláveis, eletrônicos), adaptado às práticas de descarte da localidade do usuário. Além disso, deve oferecer uma seção, semelhante a um manual, com dicas, ideias de ações e sugestões de práticas sustentáveis que o usuário pode adotar no seu dia a dia. |
| RF08 | O aplicativo deve permitir que o usuário defina metas de consumo sustentável e acompanhe seu progresso ao longo do tempo. |
| RF10 | O aplicativo deve permitir que o usuário configure lembretes diários para hábitos sustentáveis que ele deseja adotar de forma rotineira. Esses lembretes serão exibidos como notificações no dispositivo do usuário. |

### 2.2 Requisitos de Qualidade

Considerando os requisitos funcionais escolhidos no tópico anterior, foram identificados os requisitos de qualidade abaixo:

| ID | Categoria | Requisito |
|----|-----------|-----------|
| RQ01 | Compatibilidade | O aplicativo deve ser compatível com smartphones iOS e Android. |
| RQ02 | Segurança | O aplicativo deve implementar mecanismos de proteção de dados em conformidade com a LGPD, especialmente em relação a dados sensíveis como localização e hábitos pessoais. |
| RQ03 | Segurança | O aplicativo deve solicitar, de forma explícita, apenas as permissões estritamente necessárias para seu funcionamento, garantindo que o usuário compreenda claramente o motivo de cada solicitação antes de acessar dados sensíveis, como a localização. |
| RQ04 | Eficiência Energética | O consumo de bateria pelo aplicativo deve ser otimizado, especialmente ao utilizar recursos como GPS. |
| RQ05 | Confiabilidade | O sistema de localização deve oferecer alternativas quando o GPS não estiver disponível, como a busca por CEP ou endereço. |
| RQ06 | Confiabilidade | O aplicativo deve garantir que nenhuma informação do usuário seja perdida ou corrompida durante atualizações do aplicativo. |
| RQ07 | Confiabilidade | O aplicativo deve exibir uma mensagem clara quando ocorrer algum erro, como falha de conexão ou problema ao salvar uma meta. |
| RQ08 | Usabilidade | O aplicativo deve apresentar uma interface intuitiva que permita ao usuário configurar metas de consumo e lembretes em, no máximo, 3 cliques a partir da tela principal. |
| RQ09 | Usabilidade | As informações no guia interativo e na seção de práticas sustentáveis devem ser apresentadas em linguagem simples e com elementos visuais intuitivos. |
| RQ10 | Usabilidade | O aplicativo deve oferecer exemplos de metas de consumo sustentável a fim de facilitar a configuração destas por novos usuários. |
| RQ11 | Usabilidade | Ao sair de uma tela de configuração sem salvar alterações, o aplicativo deve perguntar se o usuário deseja salvá-las ou descartá-las. |
| RQ12 | Usabilidade | O aplicativo deve se adaptar automaticamente ao tema escuro do sistema operacional, respeitando a preferência do usuário. |
| RQ13 | Manutenibilidade | O código-fonte do aplicativo deve seguir padrões de organização que facilitem a adição de novos tipos de ações sustentáveis sem a necessidade de modificar a estrutura principal. |
| RQ14 | Integrabilidade | O aplicativo deve ser capaz de consumir APIs disponibilizadas por sistemas municipais, a fim de obter informações relacionadas a pontos de coleta. |
| RQ15 | Integrabilidade | O aplicativo deve ser capaz de integrar-se com APIs de mapas, como Google Maps, para fornecer recursos de geolocalização e exibição de pontos de coleta no mapa. |
| RQ16 | Portabilidade | O aplicativo deve possuir um design responsivo, adaptando sua interface a diferentes tamanhos de tela. |
| RQ17 | Acessibilidade | O aplicativo deve ser compatível com leitores de tela como TalkBack (Android) e VoiceOver (iOS), permitindo que os elementos sejam lidos em voz alta. |
| RQ18 | Acessibilidade | Todas as imagens utilizadas no aplicativo devem ter descrições (alt-text) para que possam ser interpretadas por leitores de tela. |
| RQ19 | Manutenibilidade | A arquitetura do aplicativo deve ser intrinsecamente modular, com funcionalidades distintas encapsuladas em unidades independentes, de forma a facilitar sua manutenção e teste. |
| RQ20 | Manutenibilidade | A arquitetura do aplicativo deve ser projetada para facilitar a manutenção corretiva, adaptativa e evolutiva. |
| RQ21 | Testabilidade | A arquitetura do aplicativo deve ser inerentemente testável em todos os seus níveis (unitário, integração e ponta a ponta). |
| RQ22 | Escalabilidade | A hospedagem da aplicação em um ambiente de nuvem fornecerá a infraestrutura necessária para escalar os recursos de computação. |
| RQ23 | Integrabilidade | O aplicativo deverá integrar-se com um sistema de monitoramento para que este possa acompanhar continuamente a disponibilidade e o desempenho de todos os componentes da arquitetura. |
| RQ24 | Portabilidade | Funcionalidades básicas (como visualização de metas e leitura do guia interativo) devem estar acessíveis mesmo sem conexão, sincronizando dados automaticamente quando o dispositivo voltar a ficar online. |
| RQ25 | Usabilidade | Novos usuários devem ser capazes de completar a configuração inicial do aplicativo em até 5 minutos, com tutoriais contextuais. |

## 3. Arquitetura

Com base nos requisitos de qualidade levantados, o padrão arquitetural escolhido para o desenvolvimento do aplicativo foi o **MVC (Model-View-Controller)**. Optou-se por esse padrão por proporcionar uma clara separação de responsabilidades entre a interface do usuário, a lógica de negócios e os dados, facilitando a manutenção e a evolução do sistema. Além disso, ele permite a implementação de uma interface intuitiva e adaptável a múltiplas plataformas, alinhando-se diretamente às necessidades do aplicativo.

Para representar o modelo arquitetural adotado, optamos pelo uso do **Modelo C4**, devido à sua capacidade de apresentar a arquitetura do sistema em múltiplos níveis de abstração de maneira bem simples. Ademais, trata-se de um método visual para descrever e documentar a arquitetura de software, o que possibilita uma comunicação clara e eficaz entre os diferentes stakeholders envolvidos no projeto.

O Modelo C4 estrutura a arquitetura do sistema em quatro níveis: Contexto, Contêiner, Componente e Código. Cada um desses níveis será apresentado com mais detalhes nas subseções seguintes deste documento, por meio de diagramas.

### 3.1 Contexto

Traz a aplicação de uma perspectiva macro. Isto é, representa a solução na sua forma mais abstrata possível: o sistema de software. Além disso, mostra os usuários que utilizam esse sistema e outros sistemas de software (externos) já existentes com os quais ele interage. 

### 3.2 Container

Descreve com mais detalhes o sistema de software, mostrando os containers que o compõem e como eles se comunicam entre si. Ou seja, representa uma parte implantável do sistema. As decisões de tecnologia são uma parte fundamental desse diagrama. 

### 3.3 Componente

Amplia cada container individualmente, apresentando os diversos componentes (partes) dentro dele. Um componente é um agrupamento de código com funcionalidades relacionadas, encapsuladas atrás de uma interface muito bem definida.

### 3.4 Código

Expande um componente individual para mostrar como ele é implementado, refletindo diretamente o código.
