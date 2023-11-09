# Ponderada_Lambda
Autoestudo ponderado dia 07 de novembro

## Função Lambda:

```import json```

```import boto3```

```def lambda_handler(event, context):  # Renomeando a função para lambda_handler```

```    # Verifica se o token de autenticação é válido```

```    expected_token = "seu_token_aqui"```

 ```   if event.get('token') != expected_token:```
 
  ```      return {```
  
   ```         'statusCode': 401,```
   
   ```         'body': json.dumps('Autenticação falhou')```
   
   ```     }```

  ```  # Envia a mensagem```
  
  ```  sns = boto3.client('sns')```
  
 ```   topic_arn = 'arn:aws:sns:us-east-1:123456789012:seu_topico'```
 
 ```   message = 'Sua mensagem aqui'```

```    sns.publish(```

 ```       TopicArn=topic_arn,```
 
 ```       Message=message```
 
```    )```

 ```   return {```
  ```      'statusCode': 200,```
  ```      'body': json.dumps('Mensagem enviada com sucesso')```
 ```   }```

## Passo a Passo da Função:
Acesse o Console da AWS:

#### 1.

Vá até AWS Console e faça login na sua conta.
Navegue até o AWS Lambda:

#### 2.

No console da AWS, procure e selecione o serviço "Lambda".
Crie uma nova função Lambda:

#### 2.

No painel do Lambda, clique em "Criar função".
Configuração da Função:

#### 3.

Escolha um nome para a função (por exemplo, EnviarMensagemLambda).
Escolha uma política de execução existente ou crie uma nova com permissões para publicar mensagens no SNS.


Clique em "Criar função".
Adicione um gatilho 

#### 4.

Se  deseja acionar a função por meio de um evento, adicione um gatilho correspondente (por exemplo, API Gateway, S3, etc.). Se  quiser testar manualmente, isso não é necessário.

## Testes
``` {
```  "statusCode": 200,```
```  "body": "Mensagem enviada com sucesso"```
```}```


```{```
  ```"other_key": "qualquer_valor"```
```}```
