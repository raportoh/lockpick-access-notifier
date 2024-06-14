# Lockpick-Notificador-de-Acesso

Este repositório contém os recursos necessários para criar um sistema de notificação de acesso utilizando AWS
CloudFormation, API Gateway, AWS Lambda e SNS. O objetivo é enviar notificações de acesso de forma eficiente e segura.

## Visão Geral

O projeto "Lockpick-Notificador-de-Acesso" é composto por dois principais componentes:

1. **Template CloudFormation**: Define a infraestrutura na AWS, incluindo API Gateway, Lambda Function e SNS Topic.
2. **Código do ESP8266**: Código para um dispositivo ESP8266 que envia notificações de acesso para a API Gateway
   configurada.

## Recursos

### CloudFormation Template

Este template cria os seguintes recursos na AWS:

- **SNS Topic**: Um tópico SNS para publicar mensagens de notificação de acesso.
- **Lambda Function**: Uma função Lambda que publica mensagens no tópico SNS.
- **API Gateway**: Um API Gateway que expõe um endpoint para receber notificações de acesso e invoca a função Lambda.

### Código do ESP8266

Código para um dispositivo ESP8266 que se conecta a uma rede WiFi e envia mensagens de notificação de acesso para a API
Gateway configurada.

## Como Usar

### Pré-requisitos

- Uma conta na AWS com permissões para criar recursos via CloudFormation.
- Um dispositivo ESP8266 configurado com o Arduino IDE.

### Passo a Passo

1. **Criar a Stack na AWS**:
    - Faça login no console da AWS.
    - Navegue até CloudFormation e crie uma nova stack usando o template fornecido.
    - Execute o seguinte comando para subir o template AWS:
      ```sh
      aws cloudformation create-stack --stack-name AccessNotificationStack --template-body file://template.yaml --capabilities CAPABILITY_NAMED_IAM
      ```
    - Aguarde até que a stack seja criada com sucesso.

2. **Configurar o ESP8266**:
    - Abra o Arduino IDE.
    - Copie e cole o código fornecido para o ESP8266.
    - Atualize as credenciais WiFi e a URL da API Gateway.
    - Faça o upload do código para o ESP8266.

3. **Enviar Notificações**:
    - Conecte o ESP8266 a uma rede WiFi.
    - Use o monitor serial para enviar mensagens de notificação de acesso.
    - Verifique se as mensagens são enviadas para o SNS Topic configurado.
