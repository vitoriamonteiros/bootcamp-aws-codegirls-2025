# Desafio: Implementando Infraestrutura Automatizada com AWS CloudFormation

Neste desafio, meu objetivo foi implementar uma infraestrutura automatizada utilizando **AWS CloudFormation**, aplicando conceitos de **Infraestrutura como Código (IaC)**.  

A atividade me permitiu explorar a criação, configuração e gerenciamento de recursos na AWS de forma padronizada e replicável, simulando cenários reais de provisionamento de infraestrutura em nuvem. Trabalhei com **instâncias EC2**, **Security Groups**, **volumes EBS** e scripts de inicialização (UserData) para automatizar a configuração de servidores web.

## Conceitos
- **AWS CloudFormation**: serviço que permite automatizar a criação e gerenciamento de recursos na AWS usando templates em YAML ou JSON.
- **Infraestrutura como Código (IaC)**: prática de descrever a infraestrutura como se fosse código, permitindo replicação, versionamento e automação.
- **EC2 (Elastic Compute Cloud)**: instâncias de servidores na nuvem, que podem ser configuradas e escaladas conforme necessidade.
- **Security Groups**: regras de firewall que controlam o tráfego de entrada e saída das instâncias.
- **EBS (Elastic Block Store)**: volumes de armazenamento persistente para EC2.
- **UserData**: script que roda automaticamente quando a instância EC2 é iniciada, útil para instalar e configurar softwares automaticamente.
- **Stacks**: conjunto de recursos criados e gerenciados juntos através de um template CloudFormation.
- **Templates YAML/JSON**: arquivos que descrevem os recursos e suas configurações para o CloudFormation criar a infraestrutura.

---

## Resumo de como foi feito
- Preparação
  - Configurei o **AWS CLI** e organizei o repositório no GitHub.
  - Planejei os recursos da Stack:
  - Número de instâncias EC2.
  - Configurações de Security Groups.
  - Servidores web a serem configurados via UserData.
 
- Criação do template CloudFormation
  - Desenvolvi o arquivo YAML contendo:
  - Definição das instâncias EC2.
  - Configuração de Security Groups (entrada e saída).
  - Provisionamento de volumes EBS.
  - Scripts de inicialização (UserData) para instalar e configurar o servidor web automaticamente.
  - Validei o template utilizando o **console da AWS** e o **CLI**, garantindo que não houvesse erros.

- Deploy da Stack
  - Criei a Stack pelo CloudFormation.
  - Monitorei o progresso pelo console e logs.
  - Testei o acesso às instâncias EC2 via SSH e verifiquei se o servidor web estava funcionando corretamente.

## Aprendizados
- Compreendi a importância de organizar os recursos e gerenciar dependências no CloudFormation.
- Aprendi a reutilizar templates e aplicar versionamento para facilitar futuras atualizações.
- Percebi como a automação reduz o risco de erros manuais e acelera a replicação de ambientes.

## Referências
- [Documentação AWS CloudFormation](https://docs.aws.amazon.com/cloudformation/index.html)
- [AWS CLI Documentation](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html)
