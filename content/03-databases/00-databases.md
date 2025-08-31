# Databases

Os serviços de banco de dados da AWS abrangem tanto opções gerenciadas quanto
autogerenciadas, para diferentes casos de uso.

## Serviços de banco de dados da AWS

| Serviço               | Tipo                  | Descrição                                                                 |
|-----------------------|----------------------|---------------------------------------------------------------------------|
| **Amazon RDS**        | Relacional (SQL)    | Serviço gerenciado para MySQL, PostgreSQL, MariaDB, Oracle e SQL Server.|
| **Amazon Aurora**     | Relacional (SQL)    | Compatível com MySQL e PostgreSQL, alta performance e escalabilidade.    |
| **Amazon Redshift**   | Data Warehouse       | Banco analítico para BI e análise de grandes volumes de dados.           |
| **Amazon DynamoDB**   | NoSQL (Chave-valor) | Gerenciado, rápido, escalável para aplicações serverless e baixa latência.|
| **Amazon DocumentDB** | NoSQL (Documentos)   | Compatível com MongoDB, usado para documentos JSON.                      |
| **Amazon ElastiCache**| Cache em memória     | Suporte a Redis e Memcached, para aplicações de alta performance.        |
| **Amazon Keyspaces**  | NoSQL (Wide Column)  | Compatível com Cassandra, para aplicações distribuídas.                  |
| **Amazon Neptune**    | Banco de Grafos      | Suporte a RDF e Gremlin para relacionamentos complexos.                  |
| **Amazon QLDB**       | Ledger (Livro Razão) | Banco imutável para rastreabilidade e auditoria.                         |
| **Amazon Timestream** | Séries Temporais     | Para IoT, métricas e monitoramento em tempo real.                        |

### Comparativo entre serviços de bancos de dados da AWS

| Serviço        | Tipo de Banco    | Modelo de Dados       | Caso de Uso Principal                   | Escalabilidade         | Cobrança |
|---------------|------------------|------------------------|-----------------------------------------|------------------------|----------|
| **Amazon RDS** | Relacional (SQL) | MySQL, PostgreSQL, Oracle, SQL Server, MariaDB | Aplicações transacionais (OLTP)       | Vertical e limitada horizontalmente | Por instância e armazenamento |
| **Amazon Aurora** | Relacional (SQL) | Compatível com MySQL e PostgreSQL | Alta performance e disponibilidade para apps críticos | Horizontal e automática | Por instância e I/O |
| **Amazon DynamoDB** | NoSQL          | Chave-valor e documento | Aplicações serverless, alta escala, baixa latência | Totalmente gerenciado, escalável automaticamente | Por leitura/escrita e armazenamento |
| **Amazon Redshift** | Data Warehouse | Colunar (OLAP)       | Análise de grandes volumes de dados (BI) | Escala em clusters     | Por nó e armazenamento |


## Opções autogerenciadas

O usuário pode rodar seus próprios bancos de dados em EC2 ou em contêineres
(ECS, EKS), mas sem os benefícios do gerenciamento automatizado.
