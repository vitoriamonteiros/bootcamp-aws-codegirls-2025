# Desafio: Implementando primeira stack com AWS CloudFormation

## Sobre o AWS CloudFormation
- É um serviço da AWS que permite automatizar a criação e gerenciamento de recursos na nuvem.
- Funciona com templates em JSON ou YAML, onde você define o que quer criar (EC2, S3, Security Groups, etc.).
- Permite aplicar **Infraestrutura como Código (IaC)**: infraestrutura como se fosse código, tornando fácil replicar, versionar e automatizar ambientes.

## Conceitos
- **EC2**: instâncias de servidores na nuvem.
- **Security Groups(Grupos de Segurança)**: tipo firewall que define quem pode acessar suas instâncias.
- **UserData**: script que roda automaticamente quando a EC2 inicia.
- **Stacks**: conjunto de recursos que você cria e gerencia com um template.

---
  
## Sobre o projeto
Neste desafio, meu objetivo foi implementar minha primeira Stack usando AWS CloudFormation. A ideia foi colocar em prática tudo que aprendi sobre Infraestrutura como Código (IaC), criando recursos na AWS de forma automatizada e organizada.

Durante a atividade, trabalhei com **instâncias EC2**, configurei **servidores web**, ajustei **Security Groups** e testei a inicialização das instâncias usando **UserData**. Tudo isso me ajudou a entender melhor como provisionar infraestrutura de forma repetível e confiável.

## Resumo de como foi feito
1. Configurei o **AWS CLI** para usar a AWS no terminal.
2. Planejei a Stack:
   - Quantas EC2 criar.
   - Regras de Security Group.
   - Qual servidor web instalar.
3. Criei o template YAML:
   - Defini EC2, Security Groups e volumes EBS.
   - Coloquei script no UserData para instalar Apache e criar página.
4. Validei o template antes do deploy para evitar erros.
5. Fiz o deploy da Stack pelo CloudFormation:
   - Acompanhei a criação pelo console.
   - Testei SSH e acesso ao servidor web.

## 4. Aprendizados
- CloudFormation facilita replicar ambientes e acelerar a criação de infraestrutura de forma segura e esclável.
- Como os recursos dependem uns dos outros dentro de um template, facilitando a reutilização posterior.

## Referências
- [AWS CloudFormation Documentation](https://docs.aws.amazon.com/cloudformation/index.html)