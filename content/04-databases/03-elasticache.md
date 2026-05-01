# ElastiCache

O Amazon ElastiCache é um serviço gerenciado da AWS que fornece _cache_ em
memória para acelerar aplicações, reduzindo a carga no banco de dados e
melhorando a latência.  
É totalmente compatível com [Redis](https://redis.io) e
[Memcached](https://memcached.org), dois mecanismos populares de _cache_.

## Características principais

- Serviço gerenciado: instalação, atualização, _patches_ e monitoramento cuidados pela AWS;
- Compatibilidade: Redis e Memcached;
- Escalabilidade: fácil de escalar horizontalmente e verticalmente;
- Alta disponibilidade: suporte a _failover_ automático e replicação;
- Segurança: integração com VPC, IAM, KMS (criptografia em trânsito e em repouso);
- Monitoramento: integração com CloudWatch.

## Quando usar o ElastiCache?

- Aplicações que precisam responder rapidamente (latência em ms);
- Sessões de usuários (armazenar sessões em _cache_);
- Ranking e contagem em tempo real;
- Caching de resultados de consultas para reduzir chamadas ao banco de dados;
- Filas simples ou sistemas de pub / sub usando o Redis.

## Diferenças entre Redis, Memcached no ElastiCache

| Característica    | Redis                                | Memcached              |
|-------------------|--------------------------------------|------------------------|
| Estrutura de Dados| Strings, Hashes, Lists, Sets         | Apenas chave-valor    |
| Persistência      | Sim (snapshots e AOF)               | Não                    |
| Replicação        | Sim                                  | Não                    |
| Pub/Sub           | Sim                                  | Não                    |
| Cluster           | Sim                                  | Sim                    |



