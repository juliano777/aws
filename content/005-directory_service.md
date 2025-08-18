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


| Serviço                  | O que é                  | Quando usar          |
|---------------------------|--------------------------|----------------------|
| **AWS Managed Microsoft AD** | Active Directory real,   | Quando precisa de um |
|                           | rodando como serviço     | **AD completo** na   |
|                           | gerenciado da AWS.       | nuvem (ex.: apps     |
|                           |                          | corporativos,        |
|                           |                          | integração com       |
|                           |                          | Exchange,            |
|                           |                          | SharePoint, SQL      |
|                           |                          | Server).             |
|                           |                          |                      |
| Vantagens                 | Limitações               |                      |
|---------------------------|--------------------------|----------------------|
| - Total compatibilidade   | Custo mais alto em       |                      |
|   com AD.                 | relação às demais opções.|                      |
| - Multi-AZ para alta      |                          |                      |
|   disponibilidade.        |                          |                      |
| - Pode criar relações de  |                          |                      |
|   confiança com AD local. |                          |                      |
|                           |                          |                      |
| **AD Connector**          | Proxy que redireciona    | Quando já tem um     |
|                           | requisições para o AD    | **AD local** e só    |
|                           | local (não cria diret.). | quer usar credenciais|
|                           |                          | dele em serviços AWS |
|                           |                          | (WorkSpaces,         |
|                           |                          | WorkDocs, WorkMail). |
|                           |                          |                      |
| Vantagens                 | Limitações               |                      |
|---------------------------|--------------------------|----------------------|
| - Não replica dados.      | Depende totalmente do AD |                      |
| - Usuários continuam      | local. Se ele cair, a    |                      |
|   gerenciados no AD local.| autenticação na AWS cai. |                      |
| - Baixo custo.            |                          |                      |
|                           |                          |                      |
| **Simple AD**             | Diretório básico         | Ambientes de teste,  |
|                           | compatível com Samba AD  | pequenos workloads,  |
|                           | (limitado).              | ou quando precisa só |
|                           |                          | de funcionalidades   |
|                           |                          | simples de diretório.|
|                           |                          |                      |
| Vantagens                 | Limitações               |                      |
|---------------------------|--------------------------|----------------------|
| - Mais barato.            | Sem todas as features do |                      |
| - Fácil de configurar.    | AD. Limitado em escala-  |                      |
|                           | bilidade. Não suporta    |                      |
|                           | relações de confiança    |                      |
|                           | com AD local.            |                      |
