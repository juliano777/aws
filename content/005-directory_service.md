# AWS Directory Service 

O [AWS Directory Service](https://aws.amazon.com/pt/directoryservice)é um
serviço que permite configurar e rodar diretórios compatíveis com o
[Microsoft Active Directory (AD)](https://pt.wikipedia.org/wiki/Active_Directory)
ou diretórios simples baseados em nuvem.  
Este serviço serve como uma ponte de autenticação, autorização e gerenciamento
de identidades em aplicações que precisam de integração com AD.

## Principais modos disponíveis

### 1. AWS Managed Microsoft AD
- Active Directory gerenciado pela própria AWS;
- Compatível com aplicações e workloads que exigem um AD completo;
- Possibilita conficar em diretórios _on-premises_.

### 2. AD connector
- Um proxy que conecta a AWS ao AD já existente no ambiente local;
- Evita replicação de diretório; a autenticação e consultas passam para o AD local.

### 3. Simple AD
- Diretório compatível com SAMBA AD;
- Uma opção mais barata, porém com recursos limitados.

## Casos de uso

- Integração com Amazon WorkSpaces, WorkDocs e WorkMail (login único com credenciais AD);
- Gerenciamento centralizado de usuários e permissões para aplicações hospedadas na AWS;
- Autenticação em instâncias EC2 Windows/Linux usando credenciais de domínio;
- Extensão de um AD corporativo para a nuvem (híbrido).

## Benefícios

- Gerenciado pela AWS → menos overhead administrativo;
- Alta disponibilidade nativa em múltiplas zonas de disponibilidade;
- Escalabilidade conforme número de usuários;
- Integração segura com workloads e serviços da AWS.


## Resumo

| Serviço                  | O que é                                | Quando usar                  | Vantagens                                  | Limitações                    |
|---------------------------|----------------------------------------|------------------------------|--------------------------------------------|--------------------------------|
| **AWS Managed Microsoft AD** | Active Directory real, rodando como   | Quando precisa de um **AD     | - Total compatibilidade com AD.             | Custo mais alto em relação às  |
|                           | serviço gerenciado da AWS.             | completo** na nuvem (ex.:     | - Multi-AZ para alta disponibilidade.       | demais opções.                 |
|                           |                                        | apps corporativos, integração | - Pode criar relações de confiança com AD   |                                |
|                           |                                        | com Exchange, SharePoint,     |   local.                                    |                                |
|                           |                                        | SQL Server).                  |                                            |                                |
| **AD Connector**          | Proxy que redireciona requisições      | Quando já tem um **AD local** | - Não replica dados.                        | Depende totalmente do AD local.|
|                           | para o AD local (não cria diretório).  | e só quer usar credenciais    | - Usuários continuam gerenciados no AD      | Se ele cair, a autenticação na |
|                           |                                        | dele em serviços AWS          |   local.                                    | AWS também cai.                 |
|                           |                                        | (WorkSpaces, WorkDocs,        | - Baixo custo.                              |                                |
|                           |                                        | WorkMail).                    |                                            |                                |
| **Simple AD**             | Diretório básico compatível com Samba  | Ambientes de teste, pequenos  | - Mais barato.                              | Sem todas as features do AD.   |
|                           | AD (limitado).                         | workloads, ou quando precisa  | - Fácil de configurar.                      | Limitado em escalabilidade.    |
|                           |                                        | só de funcionalidades simples |                                            | Não suporta relações de confiança|
|                           |                                        | de diretório.                 |                                            | com AD local.                   |