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

### AWS Managed Microsoft AD

Active Directory real, rodando como serviço gerenciado da AWS.

**Quando usar**: Quando precisa de um **AD completo** na nuvem (ex.: apps
corporativos, integração com Exchange, SharePoint, PostgreSQL).  

**Vantagens**: 

 - Total compatibilidade com AD;  
 - Multi-AZ para alta disponibilidade;  
 - Pode criar relações de confiança com AD local.

**Limitações**: 

Custo mais alto em relação às demais opções.

### AD connector

Proxy que redireciona requisições para o AD local (não cria diretório).

**Quando usar**: Quando já tem um AD local e só quer usar credenciais dele em
serviços AWS (WorkSpaces, WorkDocs, WorkMail).

**Vantagens**: 

 - Não replica dados;
 - Usuários continuam gerenciados no AD local;
 - Baixo custo.

**Limitações**: Depende totalmente do AD local. Se ele cair, a autenticação na
AWS também cai.

### Simple AD

Diretório básico compatível com SAMBA AD (limitado).

**Quando usar**: Ambientes de teste, pequenos workloads, ou quando precisa só de
funcionalidades simples de diretório.

**Vantagens**: 
 - Mais barato;
 - Fácil de configurar.

**Limitações**:
 - Sem todas as features do AD;
 - Limitado em escalabilidade;
 - Não suporta relações de confiança com AD local.