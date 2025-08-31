# AWS Compute

AWS Compute é um termo que se refere ao conjunto de serviços da AWS cujos
objetivos é o processamento e execução de aplicações, _workloads_ e funções.  
Ou seja, são recursos que fornecem poder computacional sob demanda, podendo
ser instâncias virtuais, contêiners ou funções _serverless_.

## Principais serviços AWS Compute

1. **[Amazon EC2 (Elastic Compute Cloud)](https://aws.amazon.com/pt/ec2)**  
   - Instâncias de máquinas virtuais (VMs) sob demanda ou reservadas;
   - Alta flexibilidade: SO (Linux, FreeBSD, Windows), tipo de CPU, memória e armazenamento;
   - Suporte a _auto scaling_ para ajuste automático de capacidade.
  
   **Casos de uso:**  
   - Hospedar aplicações web;
   - Ambientes de teste / desenvolvimento;
   - Processamento _batch_.
   
2. **[AWS Lambda](https://aws.amazon.com/pt/lambda)**
   - _Serverless computing_: você executa código sem gerenciar servidores;
   - Cobrança por tempo de execuçlão (em ms) e número de invocações;
   - Suporte a diversas linguagens (Python, Node.js, Java, Go).
   
   **Casos de uso:**  
   - Backend de aplicações;
   - Automação baseada em eventos;
   - Processamento de dados em _pipelines_.
   
3. **[Amazon ECS (Elastic Container Service)](https://aws.amazon.com/pt/ecs)**
   - Gerencimento de contêineres Docker sem precisar orquestrar manualmente;
   - Pode rodar em EC2 ou AWS Fargate (_serverless para contêineres_).
   
4. **[Amazon EKS (Elastic Kubernetes Service)](https://aws.amazon.com/pt/eks)**
   - Serviço gerenciado para rodar Kubernetes;
   - Ideal para empresas que já usam Kubernetes _on-premises_ e querem migrar.
   
5. **[AWS Fargate](https://aws.amazon.com/pt/fargate)**
   - Serviço para processamento batch em grande escala;
   - Totalmente _serverless_, pagamento pelo uso de CPU e memória consumidos pelo contêiner.
   
6. **[AWS Batch](https://aws.amazon.com/pt/batch)**
   - Serviço para processamento _batch_ em grande escala;
   - Aloca automaticamente os recursos necessários para executar _jobs_.
   
7. **[AWS Elastic Beanstalk](https://aws.amazon.com/pt/elasticbeanstalk)**  
   - PaaS (_Platform as a Service); o usuário faz o _deploy_ da aplicação e ele cuida da infraestrutura;
   - Suporte a várias linguagens e frameworks.
   
8. **[AWS Lightsail](https://aws.amazon.com/pt/lightsail)**  
   - Simples e barato para VMs pequenas;
   - Ideal para aplicações simples, blogs, pequenos sites.

## Modelos de preço

- **On-demand**: paga pelo tempo de uso e / ou por vezes que foi executado;
- **Reserved instances**: reserva capacidade com desconto;
- **Spot instances**: preço variável, até 90% mais barato (para _workloads_ tolerantes a interrupções);
- **Savings plans**: Compromisso de uso para desconto.