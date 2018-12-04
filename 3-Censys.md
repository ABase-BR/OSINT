## O que é o Censys
Censys que foi criado em 2015 na universidade de Michigan , ele nos auxilia na busca de dispositivos , redes e infraestruturas.

![Censys 1](https://i.imgur.com/4OHE97L.png)

**45 das Fortune 500 usa dados do Censys**.
> Fortune 500 é uma revista que lista as 500 maiores corporações em todo o mundo.

![Censys 2](https://i.imgur.com/adbIJGo.png)

## Como podemos usar o Censys
Agora com a ajuda desse mecanismo de busca podemos encontrar facilmente informações como
- Latitude
- Longitude
- País
- Rota
- Portas abertas e protocolos
- Podemos ver o tipo de servidor usado
- Status do teste
- Titulo do IP usado
- Nome da rede  de sites e IPS.
- Identifica

![Censys 3](https://i.imgur.com/tmahhSn.png)

E podemos obter essas informações sem estar logado no censys , podemos criar uma conta free e já começar a usar.

## Já logado no sistema
Logado no sistema podemos já realizar consultas de **whois** , podemos obter informações nos formatos:
- Table
- JSON
- Raw WHOIS

Exemplo usando o site da globo.com:
```sh
https://censys.io/ipv4/186.192.90.5/whois
```

Além disso podemos encontrar:
- Informações básicas do domínio
- Informações de contato
- Informações sobre a rede
- Informações técnicas
- Informações administrativas
- Contato para relatar algum abuso

O que podemos fazer com essas informações ?
- Obter emails
- Obter range de rede e descobrir outros servidores
- CIDR , podemos encontrar outros servidores na mesma rede

## Buscando informações sobre sites
Podemos usar a opção de site que fica disponível em:
```sh
https://censys.io/domain?q=globo.com
```

Ao pesquisar temos vários resultados de sites , o primeiro foi o que nos buscamos e além disso temos as seguintes informações:
- Protocolos
- Tags
- Resultados
- Report
- Documentação

![Censys 4](https://i.imgur.com/YIk4W6s.png)

Ao selecionar o nosso site temos informações como
- Alexa rank
- Protocolos disponível
- Informações sobre as portas que estão abertas
- Qual o servidor usado
- Titilo do site
- Informações sobre certificados do HTTPS
- Banner do serviço
- Configurações de DNS

Veja usando como exemplo o site da globo.com
![Censys 5](https://i.imgur.com/yGrwWOl.png)

Além disso essas informações podem ser nos formatos
- JSON
- Tabelas

## Buscando informações sobre certificados
Podemos ver informações sobre certificados usando o seguinte link
```sh
https://censys.io/certificates?q=globo.com
```

![Censys 6](https://i.imgur.com/LmMFHLl.png)
