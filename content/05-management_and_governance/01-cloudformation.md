# AWS CloudFormation

## O que é
O **AWS CloudFormation** é um serviço da AWS que permite **provisionar e gerenciar recursos de forma automatizada** usando templates de infraestrutura como código (IaC). Ele transforma arquivos de configuração em recursos reais na AWS, garantindo consistência e reprodutibilidade.

---

## Principais Conceitos

- **Stack**: Conjunto de recursos AWS criados e gerenciados como uma unidade. Ex.: EC2, S3, RDS juntos em uma stack.
- **Template**: Arquivo JSON ou YAML que define os recursos, parâmetros e outputs da stack.
- **Change Set**: Permite revisar alterações antes de atualizar a stack.
- **Resource**: Qualquer serviço AWS que você deseja criar ou gerenciar.
- **Parameter**: Entrada fornecida no momento da criação da stack para tornar o template mais flexível.
- **Output**: Valores retornados após a criação da stack, ex.: URL de um bucket ou endpoint de um RDS.

---

## Vantagens

- **Automação**: Criação e atualização de recursos sem intervenção manual.
- **Consistência**: Todos os ambientes podem ser reproduzidos exatamente iguais.
- **Versionamento**: Templates podem ser versionados e reutilizados.
- **Segurança**: Controle de permissões via IAM para criação e alteração de stacks.

---

## Estrutura Básica de um Template YAML

```yaml
AWSTemplateFormatVersion: '2010-09-09'
Description: Exemplo simples de CloudFormation

Parameters:
  InstanceType:
    Type: String
    Default: t2.micro
    Description: Tipo da instância EC2

Resources:
  MyEC2Instance:
    Type: AWS::EC2::Instance
    Properties:
      InstanceType: !Ref InstanceType
      ImageId: ami-0abcdef1234567890

Outputs:
  InstanceId:
    Description: ID da instância criada
    Value: !Ref MyEC2Instance
```

## Boas Práticas

- Usar templates modulares e dividir recursos em múltiplos arquivos se necessário;
- Versionar templates com Git;
- Usar Change Sets antes de aplicar alterações em stacks em produção;
- Evitar hardcode de valores sensíveis; usar Secrets Manager ou SSM Parameter Store.

