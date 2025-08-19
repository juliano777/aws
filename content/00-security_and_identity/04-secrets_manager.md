# AWS Secrets Management

O [AWS Secrets Manager](https://aws.amazon.com/pt/secrets-manager) é um
serviço cujo objetivo é de forma armazenar de forma segura, rotacionar e
gerenciar segredos.  
Segredos podem ser senhas, chaves de API, credenciais de bancos de dados ou
tokens.  
Com isso não há mais a necessidade de armazenar essas informações sensíveis de
forma insegura em código (_hardcoded_) ou em arquivos de configuração.

## Principais recursos

- **Armazenamento seguro**. 
  - Os segredos são criptografados através do [KMS (Key Management Service)](https://aws.amazon.com/pt/kms);
  - Apenas usuários / serviços autorizados via [AWS Identity and Access Management (IAM)](https://aws.amazon.com/pt/iam) podem acessá-los.

- **Rotação automática**. 
  - É possível configurar a rotação automática de credenciais (e. g.: bancods de dados [RDS](https://aws.amazon.com/pt/rds);
  - Para sincronizar e atualizar as credenciais de forma transparente usa funções Lambda.

- **Auditoria e monitoramento**. 
  - Para fazer rastreamento de quem acessou e / ou modificou secredos há integração com o [CloudTrail](https://aws.amazon.com/pt/cloudtrail).

## Onde utilizar (exemplos)

- Armazenamento de credenciais de bancos de dados;
- Armazenar chaves de API de terceiros (Github, por exemplo);
- Rotacionar automaticamente credenciais em ambientes de produção;
- Manter tokens de integrações internas.
