# AWS Lambda

É o serviço _serverless_ da AWS que permite executar código sem gerenciar
servidores.  
Ele segue o modelo **FaaS** (_Function as a Service_), em que o usuário
implementa apenas o código da função e define eventos que fará com que ela
seja disparada.  

## Principais características

A execução é feita sob demanda, a qual é paga pelo tempo de execução (ms) e
pela quantidade de requisições.  
Tem escalabilidade automática para lidar com mais requisições.  
Não há gerenciamento de servidores, isso é feito de forma transparente pela
infraestrutura da AWS.  
Funciona com eventos como gatilhos, que podem ser acionados por eventos de S3,
DynamoDB, API Gateway, CloudWatch, SNS, SQS, entre outros.  
Tem suporte a várias linguagens: Python, Node.js, Java, Go, .NET, Ruby e até
_custom runtimes_.

## Como funciona

1. Criar uma função Lambda e subir o código (zip) ou use _container image_;
2. Definir um gatilho: por exemplo; _upload_ em S3 ou chamada HTTP via API Gateway;
3. A AWS executa a função em um ambiente isolado e escala conforme necessário;
4. Pagamento pelo uso: baseado em número de invocações e tempo (GB-segundos).

## Casos de uso mais comuns

- **Processamento de arquivos**: processamento de imagens enviadas para S3, por exemplo;
- **APIs serverless**: Usando API Gateway + Lambda;
- **Automação de tarefas**: scripts disparados por CloudWatch Events;
- **Integração entre serviços AWS**: reagir a eventos de DynamoDB, SNS, etc;