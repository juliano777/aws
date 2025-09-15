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
  - Tipos: SSD (io1/io2, gp3) e HDD (st1, sc1).  
  - Usado para bancos de dados, sistemas operacionais, aplicações que precisam
    de baixa latência.  

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
    
