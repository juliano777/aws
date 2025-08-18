# AWS Identity and Access Management (IAM)

O [AWS Identity and Access Management (IAM)](https://aws.amazon.com/pt/iam) é
o serviço da AWS que gerencia acesso a recursos da nuvem de forma segura. 
Cria usuários e grupos.  
Com ele é possível contralar quem (usuários, grupos, aplicações) pode fazer o
quê (ações) em quais recursos da AWS através de políticas.

## Conceitos principais

| Conceito     | Explicação rápida                                                                 |
|--------------|------------------------------------------------------------------------------------|
| **Usuário**  | Entidade que representa uma pessoa ou aplicação. Tem credenciais (senha/chave).   |
| **Grupo**    | Conjunto de usuários com permissões comuns.                                       |
| **Política** | Documento JSON que define permissões (allow/deny).                                |
| **Role**     | Entidade que pode ser "assumida" para obter permissões temporárias.               |
| **Permissões** | Ações que o IAM permite (ex: `s3:PutObject`, `ec2:StartInstances`).             |

## Políticas

São documentos JSON que definem permissões para usuários, grupos ou roles na AWS.  
Sua estrutura é bem definida dizendo quem, o que pode fazer e sob quias condições.  
As políticas podem ser criadas / alteradas através do editor visual do console
web da AWS ou edição manual.

### Estrutura básica de uma política

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow" | "Deny",
      "Action": "serviço:ação",
      "Resource": "ARN_do_recurso"
    }
  ]
}
```

| Campo        | Descrição                                                                 |
|--------------|---------------------------------------------------------------------------|
| `Version`    | Versão da linguagem de política. Use sempre `"2012-10-17"`.               |
| `Statement`  | Bloco que define a permissão em si (pode haver vários).                   |
| `Effect`     | `"Allow"` ou `"Deny"` – permite ou nega a ação.                          |
| `Action`     | Ação da AWS (ex: `s3:PutObject`, `ec2:StartInstances`).                   |
| `Resource`   | Recurso ao qual a ação se aplica (ex: ARN de um bucket S3).              |
| `Condition`  | (Opcional) Restrições baseadas em hora, IP, tags, etc.                   |


> Obs.: O valor de `Version` não se refere à política específica, mas sim à versão da **linguagem de política** usada para interpretá-la.


**Exemplos**. 

Acesso total ao S3:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:*",
      "Resource": "*"
    }
  ]
}
```

Ler objetos de um bucket específico:

```json
{
  "Effect": "Allow",
  "Action": [
    "s3:GetObject"
  ],
  "Resource": "arn:aws:s3:::meu-bucket/*"
}
```

Permissão para iniciar e parar instâncias EC2 com tag específica:

```json
{
  "Effect": "Allow",
  "Action": [
    "ec2:StartInstances",
    "ec2:StopInstances"
  ],
  "Resource": "*",
  "Condition": {
    "StringEquals": {
      "ec2:ResourceTag/Env": "dev"
    }
  }
}
```

### Tipos de políticas

| Tipo                        | Aplica-se a...                            | Exemplo                          |
|----------------------------|--------------------------------------------|----------------------------------|
| **Gerenciada pela AWS**    | Pré-prontas e mantidas pela AWS           | `AmazonS3ReadOnlyAccess`         |
| **Gerenciada pelo cliente**| Criadas por você e reutilizáveis          | `MinhaPoliticaS3Leitura`         |
| **Inline**                 | Vínculo direto a um único usuário/role    | Não reutilizáveis                |


> **Importante!**: **`Deny`** sempre prevalece
> Se uma política dizz `Allow` e outra diz `Deny` o acesso é negado.
> A exceção se dá quando se usa _[Service Control Policies](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html)_ com exceções (organizações avançadas).

## Roles

É uma entidade que desempenha uma função, um papel que não tem credenciais permanentes, mas pode ser assumida temporariamente por:

- Serviços da AWS;
- Usuários IAM;
- Usuários externos confiáveis (outras contas da AWS, SSO ou federação via SAML).

### Por que usar roles?

São ideais quando necessita de:

- Conceder permissões temporárias;
- Evitar armazenar chaves de acesso;
- Permitir que serviços se comuniquem sentre si com segurança.

### Estrutura de uma role

| Componente               | Explicação                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| **Policy (Permissões)**  | Define o que a role pode fazer (`s3:ListBucket`, `ec2:StartInstances`, etc.)|
| **Trust Policy**         | Define **quem pode assumir a role** (ex: `ec2.amazonaws.com`, um usuário IAM, etc.) |

### Como uma role é assumida?

Quando um serviço ou usuário assume uma role, ele recebe credenciais temporárias via o serviço
[AWS (STS Security Token Service)](https://docs.aws.amazon.com/STS/latest/APIReference/welcome.html).

É possível:

- Assumir roles manualmente via console, AWS CLI ou SDK;
- Atribuir automaticamente a serviços (EC2, Lambda, etc).

### Usuário IAM vs role

| Aspecto               | Usuário IAM                            | Role IAM                              |
|-----------------------|----------------------------------------|----------------------------------------|
| Tem credenciais fixas | ✅ Sim                                 | ❌ Não                                 |
| Pode ser usado por humanos | ✅ Sim                          | ✅ Sim (se permitido na trust policy)  |
| Uso típico             | Acesso humano ou programático direto   | Acesso temporário ou por serviço       |
| Recomendado para...   | Acessos diretos e específicos          | Acesso de serviços, federação, SSO     |


## Usuário root

É o usuário original criado junto com a conta da AWS.  
Esse usuário tem acesso total e irrestrito a todos os serviços e recursos da conta.

Deve ser ter muita cautela com o usuário root, pois ele pode:

- Excluir a conta;
- Fechar serviços;
- Alterar métodos de pagamento;
- Remover todas políticas de roles;
- Desativar MFA, alterar senhas e redefinir acessos

Seu uso ou indevido pode causar sérios danos.

### Boas práticas com o usuário root

| Prática recomendada               | Explicação                                                                 |
|----------------------------------|-----------------------------------------------------------------------------|
| Ativar MFA (autenticação 2FA)    | Protege contra acesso indevido mesmo com senha comprometida                |
| Guardar as credenciais em local seguro | Root não deve ser usado no dia a dia                                   |
| Criar usuários IAM para tarefas diárias | Com permissões específicas e limitadas                                  |
| Monitorar o uso do root          | Verifique no **AWS CloudTrail** se ele foi usado e por quê                 |
| Bloquear acesso de API           | O usuário root não deve ter **chaves de acesso** (access key) ativas       |



## Boas práticas IAM

1. **Princípio de menor privilégio**: dê só as permissões mínimas necessárias;
2. **Roles**: use esse recurso para aplicações e serviços em vez de usuários
IAM com chave;
3. **MFA**: ative a autenticação de dois fatores para usuários humanos;
4. **Usuário root**: evite para tarefas rotineiras;
5. **Auditoria**: utilize o [AWS CloudTrail](https://aws.amazon.com/pt/cloudtrail) e o [IAM Access Analyzer](https://aws.amazon.com/pt/iam/access-analyzer).
