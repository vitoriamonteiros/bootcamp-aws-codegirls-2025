# Desafio: Infraestrutura básica com EC2

Este repositório é para documentar a prática realizada para o gerenciamento de instâncias EC2 na AWS, com objetivo é consolidar os conceitos aprendidos no curso, aplicando-os de forma prática e documentar. Diagrama criado no **draw.io** (app.diagrams.net/).

## Objetivos  
- Criar e gerenciar uma **instância EC2**.  
- Criar e utilizar **AMIs**.  
- Criar **Snapshots EBS** para backup.  

---

## Diagrama da Arquitetura  

![Diagrama EC2 AWS](/diagrama-ec2.jpg)  

 
- **Cliente:** é o usuário que acessa o console da AWS para criar e gerenciar os recursos.  
- **AWS Cloud:** representa a nuvem da Amazon, onde os serviços estão hospedados.  
- **VPC (Virtual Private Cloud):** é a rede virtual onde ficam suas instâncias e outros recursos.  
- **EC2 Instance:** é a máquina virtual criada dentro da VPC.  
- **EBS Volume:** é o disco de armazenamento conectado à instância EC2.  
- **Snapshot:** é uma cópia de segurança do volume EBS, usada para restaurar dados.  
- **AMI (Amazon Machine Image):** é uma imagem da instância EC2, que pode ser usada para criar novas instâncias iguais.
  
---

## 📚 Referência  
- [AWS EC2 Documentation](https://docs.aws.amazon.com/pt_br/ec2/index.html)
