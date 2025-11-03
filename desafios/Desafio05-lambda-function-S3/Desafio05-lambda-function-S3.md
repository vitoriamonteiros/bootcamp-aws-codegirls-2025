# Projeto: AWS Lambda Function e S3 Automatizados

Neste projeto, apliquei conceitos de automação de infraestrutura na AWS utilizando CloudFormation, Lambda Functions e Amazon S3. O objetivo foi criar e gerenciar recursos em nuvem de forma automatizada, simulando um fluxo real de processamento de arquivos enviados a um bucket S3.

## Serviços Utilizados
- **Bucket S3**: Armazena arquivos enviados pelo usuário.
- **Lambda Function**: Acionada automaticamente quando um objeto é criado no bucket S3.
- **CloudFormation Stack**: Provisiona a infraestrutura completa de forma automatizada, incluindo o bucket S3 e a Lambda Function.
- **IAM Role**: Função com permissões necessárias para a Lambda Function acessar o bucket S3.

## Recursos Criados
- Bucket S3 para armazenamento de arquivos.  
- Lambda Function acionada automaticamente quando um objeto é criado no bucket.  
- CloudFormation Stack que provisiona toda a infraestrutura.  
- IAM Role vinculada à Lambda Function para controle de acesso.

## Objetivo do Projeto
Automatizar tarefas simples de processamento de arquivos, aplicando conceitos de infraestrutura como código (IaC), padronização e segurança na nuvem. Este projeto demonstra como é possível criar fluxos automatizados com Lambda e S3 sem intervenção manual.

## Como Funciona
1. Um arquivo é enviado para o bucket S3.
2. O evento de criação do objeto aciona automaticamente a Lambda Function.
3. A Lambda Function processa o arquivo conforme a lógica definida (ex: renomear, registrar logs, enviar notificação, etc.).
4. Todos os recursos foram provisionados via CloudFormation, garantindo replicabilidade e versionamento da infraestrutura.

## Como Testar
- Criar ou atualizar a stack via CloudFormation utilizando o template `template.yaml` ou `template.json`.
- Enviar um arquivo para o bucket S3.
- Verificar nos logs do CloudWatch se a Lambda Function foi acionada e executou a ação esperada.

## Exemplo de Código da Lambda Function
Abaixo está um exemplo simples em **Python** de uma função Lambda que é acionada sempre que um novo arquivo é enviado ao bucket S3. Ela registra informações sobre o arquivo nos logs do **CloudWatch**:

```python
import json
import boto3

def lambda_handler(event, context):
    s3 = boto3.client('s3')
    
    bucket_name = event['Records'][0]['s3']['bucket']['name']
    file_key = event['Records'][0]['s3']['object']['key']
    
    print(f"Novo arquivo detectado: {file_key} no bucket {bucket_name}")

    response = s3.head_object(Bucket=bucket_name, Key=file_key)
    metadata = response.get('Metadata', {})
    
    print("Metadados do arquivo:", json.dumps(metadata, indent=2))
    
    return {
        'statusCode': 200,
        'body': json.dumps(f"Processamento concluído para o arquivo: {file_key}")
    }
```
### Esse código pode ser adaptado para tarefas mais complexas, como:
- Geração de miniaturas de imagens,
- Movimentação de arquivos para outro bucket,
- Envio de notificações por SNS,
- Processamento de logs ou CSVs.

## Aprendizados
- Criação e gerenciamento de recursos AWS via **CloudFormation**.
- Automação de tarefas usando **AWS Lambda**.
- Integração de eventos **S3 → Lambda** para processamento automático de arquivos.


## Referências
- [AWS CloudFormation Documentation](https://docs.aws.amazon.com/cloudformation/)
- [AWS Lambda Documentation](https://docs.aws.amazon.com/lambda/)
- [Amazon S3 Documentation](https://docs.aws.amazon.com/s3/)
- [AWS Boto3 SDK for Python](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html)
- [Amazon CloudWatch Logs Documentation](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/)

