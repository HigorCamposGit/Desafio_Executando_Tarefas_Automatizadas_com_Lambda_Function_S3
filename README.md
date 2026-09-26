# Desafio_Executando_Tarefas_Automatizadas_com_Lambda_Function_S3.
# Desafio DIO: Processamento de Arquivos com S3, Lambda e DynamoDB.

---
**Repositório foi criado para entregar o desafio prático de automação na AWS do curso: **Formação AWS Cloud Foundations** da **Digital Innovation One (DIO)**.
** Aulas ministradas pelo Prefessor: `Alexsandro Lechner`. `Arquiteto de Soluções AWS`.

O objetivo do exercício foi colocar a mão na massa e entender na prática como integrar serviços da AWS de forma automatizada.

---
## 
---

## 💡 O que foi feito no projeto?

A ideia central do projeto é criar um fluxo automático sem a necessidade de gerenciar servidores (*Serverless*):

1. **Envio do arquivo:** O usuário faz o upload de um arquivo `.json` no bucket do **Amazon S3**.
2. **Gatilho (Trigger):** Assim que o S3 recebe o arquivo, ele avisa o **AWS Lambda** de forma automática.
3. **Processamento:** O **AWS Lambda** lê as informações que estavam dentro do arquivo.
4. **Banco de dados:** A função grava esses dados em uma tabela do **Amazon DynamoDB**.
5. **Permissões:** O **AWS IAM** cuida para que o Lambda tenha acesso seguro ao S3 e ao DynamoDB.

Para deixar o processo rápido e repetível, utilizei o **AWS CloudFormation** para criar a infraestrutura através de código (IaC).

---

## 🛠️ Tecnologias e Ferramentas Utilizadas

- **Amazon S3:** Para guardar os arquivos enviados.
- **AWS Lambda:** Para rodar o código de processamento automaticamente.
- **Amazon DynamoDB:** Banco de dados para salvar os registros.
- **AWS IAM:** Gerenciamento de acessos e segurança.
- **AWS CloudFormation:** Para subir toda essa estrutura de uma vez só por código.
- **LocalStack:** Ferramenta fantástica para simular o ambiente da AWS no próprio computador e testar tudo sem gastar nada.
- **Draw.io:** Usado nas aulas para desenhar e visualizar o diagrama da arquitetura.

---

## 📁 Estrutura dos Arquivos

- `template.yaml` -> Arquivo do CloudFormation que cria toda a estrutura na AWS.
- `src/index.py` -> Código em Python que a função Lambda executa.
- `README.md` -> Este documento de anotações e explicações.

---

## 🧠 Principais Aprendizados e Insights

- **Entendimento de eventos:** Percebi como os serviços da nuvem conversam entre si. Não preciso de uma máquina ligada 24 horas; o código só roda quando o arquivo chega.
- **Infraestrutura como Código:** Criar os recursos direto no CloudFormation economiza muito tempo e evita erros manuais no painel da AWS.
- **Testes Locais:** Usar o **LocalStack** facilitou muito o aprendizado, pois pude errar e testar os comandos pelo terminal sem medo de gerar custos na conta da AWS.

---
*Projeto desenvolvido para fins de estudo no bootcamp da DIO.*
