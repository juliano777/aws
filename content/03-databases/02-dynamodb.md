# DynamoDB

O Amazon DynamoDB é um serviço de banco de dados NoSQL totalmente gerenciado
pela AWS, projetado para aplicações que exigem alta performance, baixa
latência e escalabilidade horizontal.  
Ele é baseado em um modelo de tabelas, itens e atributos (sem esquema fixo) e
oferece recursos integrados de segurança, backup, restauração e replicação
global.

## Principais características

- NoSQL / não relacional: usa chave-valor e documentos;
- Escalabilidade automática: ajusta a capacidade de leitura / escrita conforme a demanda;
- Alta disponibilidade: replicação automática entre várias zonas de disponibilidade;
- Desempenho previsível: milissegundos em qualquer escala;
- Replicação global: através de _global tables_, sincronizando dados entre regiões para aplicativos globais;
- Gerenciado pela AWS: sem necessidade de administrar servidores;

### Modos de capacidade
- _On-demand_
  Pagamento por solicitação (ideal para cargas imprevisíveis);
- Provisionado
  Define capacidade de leitura / escrita e pode usar auto scaling.

## Componentes principais

- Tabelas: contêm os dados;
- Itens: cada registro dentro da tabela (semelhante a uma linha);
- Atributos: campos do item (semelhante a colunas);
- Chave primária: pode ser chave simples (_partition key_) ou chave composta (_partition key_ + _sort key_);
- Índices secundários: LSI (_Local Secondary Index_) ou GSI (_Global Secondary Index_).

## Recursos de segurança

- IAM: controle de acesso;
- Criptografia: em repouso ou em trânsito;
- Backup e restore: pontos no tempo (PITR - _Point In-Time Recovery_).

## Casos de uso

- Aplicações web e mobile de alta escala;
- Jogos _online_;
- IoT (Internet das coisas);
- Sessões de usuário;
- Catálogo de produtos.
