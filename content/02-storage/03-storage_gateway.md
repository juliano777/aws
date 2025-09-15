# AWS Storage Gateway

O **AWS Storage Gateway** é um serviço híbrido de armazenamento que conecta ambientes locais (on-premises) à AWS, permitindo integrar dados locais com serviços de armazenamento em nuvem.

## Tipos de Gateway

### 1. File Gateway
- Apresenta armazenamento de objetos do Amazon S3 como arquivos em sistemas locais.  
- Compatível com protocolos **NFS** e **SMB**.  
- Útil para backup, arquivamento e acesso a arquivos frequentemente usados.  

### 2. Tape Gateway
- Substitui bibliotecas de fitas físicas por fitas virtuais na AWS.  
- Compatível com softwares de backup já existentes.  
- Os dados são armazenados no **Amazon S3** e podem ser migrados para **Amazon S3 Glacier** ou **S3 Glacier Deep Archive** para arquivamento de longo prazo.  

### 3. Volume Gateway
- Apresenta volumes de armazenamento em blocos para aplicações locais.  
- Modos de operação:  
  - **Stored Volumes** → mantém dados principais localmente e envia cópias assíncronas para o S3.  
  - **Cached Volumes** → mantém em cache os dados mais acessados localmente, enquanto o conjunto de dados completo fica no S3.  
- Compatível com snapshots do **Amazon EBS**.  

