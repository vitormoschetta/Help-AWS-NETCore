# Publicando uma aplicação .NET Core 3.1 no AWS Elastic Beanstalk

## Gerar App
```
dotnet new mvc
```

## Instalar tools AWS
```
dotnet tool install -g Amazon.ElasticBeanstalk.Tools
```

## Baixar e instalar AWS CLI
<https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html>


## Definir credencias (secret Key) na AWS
<https://console.aws.amazon.com/iam/home?region=us-east-2#/security_credentials>


## Adicionar credenciais no AWS CLI
```
aws configure
```

O console irá requisitar:
```
AWS Access Key ID [None]: ********************
AWS Secret Access Key [None]: ****************************************
Default region name [None]: us-east-1
Default output format [None]: json
```


## Adicionar arquivo de configuração AWS:
```
{
    "region": "us-east-1",
    "application": "aspnetcore-app",
    "environment": "aspnetcore-dev",
    "configuration": "Release"
}
```

Obs: Salvar na raíz da aplicação com o nome _aws-beanstalk-tools-defaults.json_


## Adicionar 'Environment' no appsettings.json
```
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    }
  },
  "AllowedHosts": "*",
  "Environment": "Local"    <--
}
```

## Fazer o deploy / publicar
```
dotnet eb deploy-environment
```


<br>
<br>



### Referências
<https://www.treinaweb.com.br/blog/publicando-uma-aplicacao-net-core-3-0-no-aws-elastic-beanstalk/>
