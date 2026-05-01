# Amazon Route 53

É o serviço de DNS (Domain Name System) gerenciado da AWS.  
Foi projetado para ser altamente disponível e escalável, permitindo que se
registre domínios, gerencie o roteamento de tráfego da sua aplicação e
realize _health checks_ para garantir disponibilidade.

## Recursos Principais do Route 53

| Recurso                  | Descrição                                                                 |
|---------------------------|---------------------------------------------------------------------------|
| **Registro de Domínios** | Permite comprar e gerenciar domínios diretamente na AWS.                  |
| **DNS Gerenciado**       | Resolve nomes de domínio em endereços IP com alta disponibilidade.        |
| **Roteamento de Tráfego**| Suporte a múltiplas políticas de roteamento (simples, peso, latência, geográfico e failover). |
| **Health Checks**        | Monitora endpoints e desvia tráfego em caso de falhas.                    |
| **Integração AWS**       | Integra-se facilmente com CloudFront, S3, ELB, API Gateway e outros.      |
| **Baixa Latência**       | Rede global de servidores DNS autoritativos garante rapidez nas respostas.|
| **Escalabilidade**       | Escala automaticamente para atender grandes volumes de requisições.      |
| **Segurança (DNSSEC)**   | Suporte ao DNSSEC para proteger contra ataques de falsificação de DNS.    |


## Benefícios
- Alta disponibilidade e confiabilidade;
- Integração simplificada com serviços da AWS;
- Suporte a políticas de roteamento avançadas;
- Escalabilidade automática sem necessidade de configuração adicional;
- Segurança aprimorada com DNSSEC.
