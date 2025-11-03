# Desafio: AWS Step Functions – Projeto de Estudo

Este projeto tem como objetivo explorar o serviço AWS Step Functions, criando workflows automatizados que integram diferentes serviços da AWS, como Lambda, S3, SNS, SQS e DynamoDB. com foco em aplicar conceitos de orquestração, automação e boas práticas de arquitetura em nuvem.

## Serviços e funções
- **AWS Step Functions**: Orquestração do fluxo de trabalho.  
- **AWS Lambda**: Funções para validar arquivos e processar dados.  
- **Amazon S3**: Armazenamento de arquivos.  
- **Amazon SNS (Simple Notification Service)**: Envio de notificações em caso de erro ou sucesso, sendo enviado via e-mail, SMS ou HTTP.
- **Amazon SQS (Simple Queue Service)**: Garante que as mensagens sejam processads de forma assícrona e confiável, utilizado para orquestrar tarefas de processamento sem perda de dados.
- **Amazon DynamoDB**: Armazenamento ou envio de mensagens processadas (dependendo do fluxo).  

---

## Exemplo de Estrutura do Workflow
- **Validação de arquivo:** Trigger pelo S3 → Lambda valida os arquivos.
- **Processamento de dados:** Lambda processa ou transforma os dados.
- **Mensageria:** SNS envia notificações sobre o status.
- **Fila de tarefas:** SQS garante o processamento confiável.
- **Registro de resultados:** DynamoDB armazena o histórico e status final.


---

## Aprendizados
- Aprendi que o Step Functions facilita a integração de múltiplos serviços sem a necessidade de gerenciar servidores manualmente.  
- Importância de definir triggers e falhas corretamente para que o workflow não pare em caso de erro.  

---
## Referências

- [AWS Step Functions Documentation](https://docs.aws.amazon.com/step-functions/latest/dg/welcome.html)  
- [AWS Lambda Documentation](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)  
- [Amazon S3 Documentation](https://docs.aws.amazon.com/s3/index.html)  
- [Amazon SNS Documentation](https://docs.aws.amazon.com/sns/latest/dg/welcome.html)  
- [Amazon SQS Documentation](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/welcome.html)  
- [Amazon DynamoDB Documentation](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html)
