# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

Data: 23/10/2026  
Empresa: Abstergo Industries  
Responsável: Talita Fanelli Silva

## Introdução
Este relatório apresenta o processo de implementação de ferramentas na empresa Abstergo Industries, realizado por Talita Fanelli Silva. O objetivo do projeto foi elencar 3 serviços AWS, com a finalidade de realizar diminuição de custos imediatos.

## Descrição do Projeto
O projeto de implementação de ferramentas foi dividido em 3 etapas, cada uma com seus objetivos especí­ficos. A seguir, serão descritas as etapas do projeto:

### Etapa 1: 
- **Ferramenta:** Amazon EC2 + Auto Scaling  
É uma solução de infraestrutura em nuvem que permite executar servidores virtuais e ajustar automaticamente a quantidade de servidores conforme a demanda. A cobrança ocorre somente pelo que for efetivamente usufruído. 
- **Caso de uso:** Em uma promoção nacional de medicamentos genéricos, o tráfego triplica. Com EC2 + Auto Scaling, a infraestrutura cresce automaticamente durante a campanha e encolhe ao final  **sem intervenção humana e sem custo extra permanente** solucionando assim umas principais queixas da empresa: lentidão e queda do sistema durante picos de demanda.  
  
### Etapa 2: 
- **Ferramenta:** Amazon DynamoDB  
É um banco de dados NoSQL totalmente gerenciado da AWS, usado para armazenar e acessar dados com altíssima velocidade e escala automática sendo ideal para aplicações que precisam de respostas em milissegundos, grande volume de acessos simultâneos e sem gestão de servidores, como catálogos de produtos, sessões de usuários, preços e estoque em tempo real.
- **Caso de uso:** Durante uma campanha nacional, o número de consultas de preço sobe de 500 para 5.000 por segundo. O DynamoDB absorve o pico automaticamente sem queda e sem custo fixo adicional.  
  
### Etapa 3: 
- **Ferramenta:** Amazon RDS / Aurora  
É um banco de dados relacional totalmente gerenciado da AWS, usado para armazenar e gerenciar dados estruturados com consistência e integridade. Seu objetivo é facilitar operações críticas, como vendas, pedidos, pagamentos e relatórios, oferecendo alta disponibilidade, escalabilidade automática e backup sem necessidade de gerenciar servidores.
- **Caso de uso:** Em uma rede de 100 lojas o Aurora garante que:
  
  a) Cada venda seja registrada sem duplicidade  
  b) Relatórios diários estejam com dados corretos  
  c) Falhas de servidor não afetem operação do PDV  
  
### Etapa 4: 
- **Ferramenta:** AWS Lambda  
É um serviço de computação serverless da AWS que permite executar código sem precisar gerenciar servidores, pagando apenas pelo tempo de execução. Seu objetivo é automatizar tarefas, processar eventos em tempo real e integrar sistemas, escalando automaticamente conforme a demanda.
- **Caso de uso:** Para usar **Aurora/RDS + DynamoDB**, o AWS Lambda (com suporte opcional de SQS ou EventBridge) permite integrar os dois bancos de forma eficiente e escalável, garantindo que os dados críticos fiquem em Aurora e os dados de alto volume e leitura rápida fiquem no DynamoDB, mantendo ambos consistentes. Durante uma promoção nacional, milhares de vendas simultâneas atualizam o estoque em tempo real.  O Lambda dispara as atualizações automaticamente, garantindo que o app e o e-commerce reflitam os dados corretos, sem custo de servidores extras. Segue o exemplo das soluções integradas:
  
  a) **Venda registrada no PDV** → dados salvos no **Aurora/RDS**  
  b) **Evento disparado** → Lambda é acionado  
  c) **Lambda atualiza estoque** no **DynamoDB** e notifica app/e-commerce  
  d) **Estoque e preços refletidos em tempo real** para clientes e lojistas, com escalabilidade automática e sem custo de servidores ociosos.

## Conclusão
A implementação das ferramentas citadas na empresa Abstergo Industries tem como propósito solucionar os gargalos reportados: lentidão e queda do sistema durante picos de demanda além de redução de custos com a infraestrutura de TI aumentando assim a eficiência e a produtividade geral da empresa. Recomenda-se a continuidade da utilização das ferramentas implementadas e a busca por novas tecnologias que possam melhorar ainda mais os processos da empresa.


## Anexos

Fluxograma com a arquitetura da solução proposta ([arquivo: Abstergo_Arquitetura.jpeg](url))

Assinatura da Responsável pelo Projeto:

Talita Fanelli Silva
