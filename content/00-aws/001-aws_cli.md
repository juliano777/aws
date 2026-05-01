# Introdução ao AWS CLI

## O que é o AWS CLI?
O **AWS CLI** é uma ferramenta unificada que permite gerenciar e interagir com os serviços da AWS diretamente pelo terminal ou prompt de comando. Em vez de utilizar a interface gráfica (Console Web) para clicar em botões, você envia instruções via texto.

- https://aws.amazon.com/pt/cli/
- https://docs.aws.amazon.com/cli/latest/
- https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html


## Principais Benefícios
- **Velocidade:** Execução rápida de tarefas repetitivas.
- **Automação:** Possibilidade de criar scripts (Bash, PowerShell, Python) para configurar infraestruturas inteiras automaticamente.
- **Controle:** Acesso a recursos e parâmetros que às vezes são mais fáceis de visualizar via linha de comando.

---

## Exemplos Práticos de Comandos

A estrutura básica de um comando é:  
`aws <serviço> <operação> [parâmetros]`

### 1. Amazon S3 (Armazenamento)
- **Listar Buckets:** Ver todas as suas pastas na nuvem.
    ```bash
    aws s3 ls
    ```
- **Fazer Upload:** Copiar um arquivo local para um bucket.
    ```bash
    aws s3 cp documento.pdf s3://nome-do-seu-bucket/
    ```

### 2. Amazon EC2 (Servidores/Máquinas Virtuais)
- **Verificar Instâncias:** Listar os servidores que estão rodando na conta.
    ```bash
    aws ec2 describe-instances
    ```

### 3. IAM (Gestão de Identidade e Acesso)
- **Criar Novo Usuário:** Adicionar um novo integrante à conta de forma rápida.
    ```bash
    aws iam create-user --user-name NovoAluno
    ```

---

## Conclusão
O AWS CLI funciona como um "controle remoto" via texto para a nuvem. Ele é essencial para profissionais que buscam trabalhar com **DevOps** e infraestrutura como código.

---