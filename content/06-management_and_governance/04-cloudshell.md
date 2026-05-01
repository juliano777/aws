# AWS CloudShell

## O que é
O **AWS CloudShell** é um ambiente de linha de comando **baseado em navegador**,
fornecido pela AWS, que permite gerenciar recursos diretamente pelo **AWS CLI**
e outras ferramentas, **sem necessidade de instalação ou configuração local**.

Ele já vem autenticado com as credenciais do usuário logado no Console AWS,
utilizando as permissões definidas no **IAM**.


## Recursos principais

| Recurso | Descrição |
|--------|-----------|
| **Ambiente pré-configurado** | AWS CLI, Python, Node.js, Git e outras ferramentas já instaladas. |
| **Autenticação automática** | Usa as credenciais do usuário do Console AWS (IAM). |
| **Armazenamento persistente** | Diretório `~/` com até 1 GB persistente entre sessões. |
| **Execução via navegador** | Não requer instalação local ou acesso SSH. |
| **Integração com Console** | Executa comandos diretamente no mesmo contexto da conta e região selecionada. |
| **Suporte a scripts** | Permite criar e executar scripts Bash, Python, etc. |


## Benefícios

- **Zero configuração**: pronto para uso imediatamente.
- **Segurança**: sem necessidade de chaves de acesso locais.
- **Portabilidade**: acesso a partir de qualquer navegador.
- **Consistência**: ambiente padronizado para equipes.
- **Ideal para automação leve** e testes rápidos.


## Casos de uso

- Execução rápida de comandos AWS CLI.
- Testes e validações de infraestrutura.
- Troubleshooting sem acesso a um terminal local.
- Demonstrações, treinamentos e laboratórios.
- Automações simples e scripts pontuais.


## Limitações

- **Não indicado para workloads pesados ou long-running**.
- Limite de **1 GB de armazenamento persistente**.
- Tempo de sessão limitado (encerrada automaticamente após inatividade).
- Não substitui ambientes locais ou pipelines de CI/CD.


## Exemplo de uso

```bash
# Listar instâncias EC2
aws ec2 describe-instances

# Ver buckets S3
aws s3 ls

# Criar um bucket
aws s3 mb s3://meu-bucket-exemplo
```
