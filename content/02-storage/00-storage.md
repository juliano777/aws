# Storage na AWS

A AWS oferece diferentes opções de armazenamento, dependendo do tipo de dado,
acesso e workload.

## 📂 File Storage
- **Amazon EFS (Elastic File System)**  
  - Sistema de arquivos elástico e totalmente gerenciado.  
  - Compatível com **NFS**.  
  - Escala automaticamente para milhares de instâncias.  
  - Ideal para aplicações que precisam de compartilhamento de arquivos.  

- **Amazon FSx**  
  - Sistemas de arquivos otimizados para workloads específicos.  
  - Suporta diversos tipos, como:  
    - **FSx for Windows File Server** (SMB, AD integrado).  
    - **FSx for Lustre** (alto desempenho para HPC e ML).  
    - **FSx for NetApp ONTAP**, **FSx for OpenZFS**.  

## 📦 Block Storage
- **Amazon EBS (Elastic Block Store)**  
  - Volumes de blocos persistentes para EC2.  
  - Usado para bancos de dados, sistemas operacionais, aplicações que precisam
    de baixa latência.  
  
  **Tipos**  
    - **Propósitos gerais: `gp2` / `gp3`**  
      Ideal para web servers.  
      Cargas que necessitam de um bom equilíbrio de performance e custo.  

      **`gp2`**  
      - Adequado para discos de boot e aplicações gerais;  
      - Até 16k IOPS por volume;
      - Até 99,9% de durabilidade.
  
      **`gp3`**  
      - Adequado aplicações de alta performance;  
      - Desempenho de referência esperado de 3k IOPS e 125MiB/s, independente
        do tamanho do volume;  
      - Até 99,9% de durabilidade.

    - **SSD com IOPS provisionados: `io1`** / **`io2`**  
      Banco de dados relacional hospedado em EC2 com alta demanda de I/O.  
      Cargas que necessitam de consistência e altos níveis de performance.  

      **`io1`**  
      - Adequado para OLTP e aplicações de latência sensível;  
      - 50 IOPS/GiB e até 64k IOPS por volume;
      - **Mais barato** do que o `io1`;
      - Até 99,9% de durabilidade;
      - Volume de IOPS de última geração.
  
      **`io2`**  
      - Adequado para OLTP e aplicações de latência sensível;  
      - 500 IOPS/GiB e até 64k IOPS por volume;
      - Alta performance e **mais caro**;
      - Até 99,999% de durabilidade.    
    
      > O uso de `io1` em vez de `io2` só faz sentido quando há motivos de
      > aplicações legadas e não é aconselhável para novos projetos.

    - **Magnéticos (HDD): `sc1`** / **`st1`**  
      Arquivamento de dados e backup.  
      Para grandes volumes de dados que não sejam acessados frequentemente que
      precisam ser aramazenados, economicamente viável para retenção de longo
      prazo.

      **`st1`**  
      - Adequado para big data, DWs, ETL;  
      - _Throughput_ máximo é 500 MB/s por volume;
      - Não pode ser usado para _boot_;
      - Até 99,9% de durabilidade.
  
      **`sc2`**  
      - Adequado para dados acessados com pouca frequência;
      - _Throughput_ máximo é 250 MB/s por volume;
      - Não pode ser usado para _boot_;
      - **Menor custo**;
      - Até 99,9% de durabilidade.


## 🪣 Object Storage
- **Amazon S3 (Simple Storage Service)**  
  - Armazenamento de objetos altamente escalável e durável (99.999999999%).  
  - Classes de armazenamento: Standard, IA, Glacier, Deep Archive.  
  - Integração com quase todos os serviços AWS.  
  - Ideal para backup, big data, conteúdo estático, data lakes.  

## 🛠 Serviços de Suporte a Storage

- **AWS Backup**  
  - Serviço centralizado de **backup gerenciado**.  
  - Suporte para EFS, EBS, RDS, DynamoDB, FSx, S3 (em alguns cenários).  
  - Automação com políticas de retenção e compliance.  

- **AWS Storage Gateway**  
  - Integração entre **on-premises** e a AWS.  
  - Modos: File Gateway, Volume Gateway, Tape Gateway.  
  - Facilita migração e extensão de storage para nuvem.  

- **AWS DataSync**  
  - Transferência rápida e segura de grandes volumes de dados.  
  - Entre ambientes on-premises e AWS ou entre serviços AWS.  
  - Automatiza a movimentação recorrente de dados.  

- **AWS Transfer Family**  
  - Serviço gerenciado para transferência de arquivos via protocolos
    tradicionais:  
    - **SFTP**, **FTPS**, **FTP**.  
  - Permite que aplicações legadas continuem funcionando enquanto usam o S3 ou
    EFS como backend.
    
