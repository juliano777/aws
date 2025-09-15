# Amazon EFS - Elastic File System

O **Amazon Elastic File System (EFS)** é um serviço de
**armazenamento de arquivos totalmente gerenciado** e escalável da AWS.  
Ele fornece um sistema de arquivos compartilhado que pode ser acessado
simultaneamente por múltiplas instâncias do Amazon EC2 e outros serviços,
usando o protocolo **NFS (Network File System)**.  

## Características principais
- **Escalabilidade automática**: o armazenamento cresce ou diminui conforme os arquivos são adicionados ou removidos, sem necessidade de provisionamento manual.
- **Acesso compartilhado**: múltiplas instâncias podem acessar o mesmo sistema de arquivos de forma concorrente.
- **Compatibilidade com NFSv4.1 e NFSv4.0**: facilita integração com aplicações já existentes.
- **Alta disponibilidade e durabilidade**: dados replicados automaticamente em várias zonas de disponibilidade (AZs).
- **Gerenciado pela AWS**: sem necessidade de configurar ou manter servidores de arquivos.

## Classes de armazenamento
- **EFS Standard**: armazenamento padrão, ideal para workloads de uso frequente.
- **EFS Standard-IA (Infrequent Access)**: otimizado para dados acessados com pouca frequência, com custo mais baixo de armazenamento.
- **EFS One Zone**: armazena dados em apenas uma zona de disponibilidade, com menor custo.
- **EFS One Zone-IA**: versão de baixo custo e acesso infrequente em uma única AZ.

## Casos de uso
- Ambientes de **desenvolvimento e teste** que precisam de compartilhamento de arquivos.
- **Aplicações web e CMS** (ex.: WordPress, Drupal).
- **Big Data e análise** que requerem múltiplos nós acessando os mesmos dados.
- **Containers e Kubernetes** para armazenamento persistente compartilhado.
- **Backups e diretórios de usuários**.

## Benefícios
- **Pagamento por uso**: cobra apenas pelo espaço realmente utilizado.
- **Baixa latência** para acesso a arquivos.
- **Integração com outros serviços AWS**, como EC2, ECS, EKS e Lambda (via EFS Access Points).
- **Segurança**: integração com IAM, VPC, Security Groups e encriptação em repouso e em trânsito.

