# Amazon CloudFront

É o serviço de CDN (Cloud Delivery Network) da AWS.  
Ele distribui conteúdo (arquivos estáticos, vídeos, sites, APIs) de forma
rápida, segura e com baixa latência, entregando-os a partir de
_edge locations_ espalhadas globalmente.

| Recurso/Característica      | Descrição                                                                 |
|-----------------------------|---------------------------------------------------------------------------|
| **Tipo de serviço**         | CDN (Content Delivery Network)                                            |
| **Entrega global**          | Rede de edge locations em várias regiões do mundo                         |
| **Integração**              | Funciona com S3, EC2, ELB, API Gateway e serviços on-premises             |
| **Caching**                 | Armazena objetos em cache para reduzir latência e custo de transferência  |
| **Segurança**               | Integração com AWS Shield, WAF e suporte a HTTPS/TLS                      |
| **Controle de acesso**      | Suporte a assinaturas, tokens, OAI (Origin Access Identity) e políticas   |
| **Escalabilidade**          | Escala automaticamente conforme a demanda de tráfego                      |
| **Custos**                  | Baseados em dados transferidos + requisições                              |
| **Casos de uso**            | Streaming de vídeo, distribuição de sites, APIs, downloads de arquivos    |