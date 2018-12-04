# Shodan

Conheça o site oficial
```sh
https://www.shodan.io/
```


## Antes de começar
Agora não é só arquivos sensíveis que estão expostos na internet , nossos dispositivos conectados a internet também podem estar expostos e pessoas com má índole pode usar isso para o mal.

## O que é o Shodan
Em 2009 John Matherly lançou na internet um mecanismo chamado Shodan que tem como objetivo não só encontrar sites , IPs , mais também de encontrar dispositivos conectados com a internet.

Podemos retornar diversos dispositivos que estão conectados na rede usando o Shodan , como por exemplo:
- Webcam
- Banco de dados
- Servidores
- Roteadores

## Como funciona
O Shodan usa o mecanismo de pesquisa de banners de serviço , isso tudo nada mais é que metadados que são retornados ao usuário quando inicia a comunicação com um serviço.

Ele nos retorna informações desde mensagens de boas vindas , versões de serviço e outras coisas que pode acontecer quando se está iniciando uma conexão com algum serviço.

Quando falamos de dispositivos conectados com a rede estamos falando de tudo o que está conectado a rede de computadores , desde computadores , celulares , televisores , semáforos e até equipamentos hospitalares.

Além de poupar recursos no uso de informações públicas também tem um serviço muito interessante que ele usa as informações retornadas através dos banners , ele bate essas informações com versões de serviços , se tiver alguma vulnerabilidade naquele serviço ele retorna o Common Vulnerabilities and Exposures (CVE) que é o RG da possível falha e assim já podemos procurar por mais informações referente.

## Iniciando os testes
O Shodan é um serviço semelhante ao Google , a diferença é que com ele podemos encontrar dispositivos conectados a internet. Ele tem servidores em diversos lugares do mundo , dessa forma pode tentar evitar o bloqueio em outros países. Ele usa rastreadores para buscar por dispositivos e para enumerar de serviços. Ele funciona primeiro pegango um IPv4 aleatório , depois ele usa uma porta aleatória para testar usando uma lista de portas que o shodan entende , assim pega o banner da aplicação ,filtrar as informações para salvar no banco de dados e checar podemos usar elas posteriormente.

Além disso ele já automatiza toda a comunicação com o dispositivo e ainda nos retorna se ele está vulnerável ou não a alguma falha.

Podemos realizar buscas usando um IP , dessa forma podemos saber a:
- Localização do servidor  
- Cidade
- Pais
- Organização
- Hostnames
- ASN
- Serviços
- Portas

![Shodan 1](https://i.imgur.com/y2agHa0.png)

O próximo passo é conhecer os **operadores** , só que para isso é necessário criar uma conta , para usar esse tipo de filtro e obter mais informações.

## Lab Shodan
Crie uma conta no site do Shodan , não custa nada e para realizar esse estudo é o necessário.
> Caso tenha um email educacional da sua faculdade , podemos ter uma conta com mais privilégios e com limite maior de busca.

## Shodan e seus operadores
Podemos usar os operadores do Shodan para realizar buscar , sejam elas:
- country
- city
- OS
- port
- IP
- NET
- hostname
- Server

### Filtrando por País (country)
Podemos filtrar por hosts em um determinado pais usando o operador **country**.
```sh
country:br
```

### Filtrando por cidade (city)
É possível também filtrar por cidade , basta usar o operador **city**.
```sh
city:Bauru
```

### Filtrando por sistema operacional (OS)
Podemos filtrar por sistemas operacionais , isso pode ser muito valido quando sai uma nova vulnerabilidade em um terminado sistema operacional e especialistas com o operador **OS** podemos realizar esse filtro.

Buscando por sistemas operacionais Windows:
```sh
os:"Windows"
```
![Shodan 5](https://i.imgur.com/RaIBoCF.png)

Podemos buscar por sistemas operacionais Linux:
```sh
os:"Linux"
```
![Shodan 6](https://i.imgur.com/InbLWyC.png)

### Filtrando por determinada porta (port)
Podemos buscar por informações sobre um grupo que usa a mesma porta , por exemplo uma buscar por **portas 3306** que são por padrão usadas por banco de dados:
```sh
 port:3386
```
![Shodan 7](https://i.imgur.com/MORvfSx.png)

### Trazendo informações de um IP (IP)
Podemos buscar por um determinado IP da seguinte forma.
```sh
ip:37.59.174.225
```
![Shodan 8](https://i.imgur.com/Nwc2E2N.png)

Podemos ver informações detalhadas clicando em **details**:
![Shodan 9](https://i.imgur.com/6x055Gy.png)

### Trazendo informações de uma rede (NET)
Podemos buscar informações de uma determinada rede , podemos usar o **operador**:
```sh
net:
```

Veja um exemplo com diversos endereços , se lembra do **ASN CIDR** ?

Vamos usar o **CIDR** da globo para buscar por servidores desssa rede:
```sh
net:186.192.80.0/20
```

![Shodan 2](https://i.imgur.com/paxL1WY.png)

### Trazendo informações de um host (hostname)
Podemos pesquisar por HOSTS , podemos usar o domínio para realizar esse teste e ter informações como por exemplo:
- Top paises(Brasil,India)
- Top serviços(HTTPS,HTTP,FTP,MYSQL)
- Top Organizações(Facebook, Digital ocean)
- Top sistemas operacionais(Windows server 2012, Windows 7 ,Windows 8 e Linux)
- Top produtos (apache, nginx,mysql,openssh e Exim smtp)

Veja um exemplo usando o facebook:
```sh
hostname:facebook.com
```
![Shodan 3](https://i.imgur.com/vZp9qir.png)

Podemos realizar outro exemplo usando o site da Globo.com
```sh
hostname:globo.com
```

![Shodan 4](https://i.imgur.com/BZZEyUS.png)
### Buscando por dispositivos usando o (Server)
Com o uso do **Server** podemos obter informações sobre câmeras , sistemas e até webcam.
```sh
Server: SQ-WEBCAM
```

Podemos ver que temos 99 resultado , veja uma imagem:
![Shodan 10](https://i.imgur.com/JGpMzP4.png)

Veja outro modelo de câmera
```Sh
Server: U S Software Web Server
```
![Shodan 11](https://i.imgur.com/LOFz20G.png)

## Palavras chave
Podemos buscando por caixas ATM no Brasil , tudo o que precisamos é usar a palavra **atm**.

Veja a união de uma palavra chave junto de um operador que filtra pais:
```sh
 atm country:br
```
![Shodan 12](https://i.imgur.com/yMuDOzd.png)

## Começando a usar Dorks
Podemos unir o uso de **operadores** , palavras chaves e criar Dorks complexas para filtrar as nossas buscas

### Buscando por câmeras no Brasil e em Bauru
Dessa forma podemos buscar por câmeras que estejam localizadas no Brasil e na cidade de Bauru
```sh
camera country:br city:Bauru
```
![Shodan 13](https://i.imgur.com/gkEDZW2.png)

### Pesquisando sistemas operacionais
Até o momento apenas 21 servidores windows foram identificados , isso não significa que só temos 21 servidores Windows funcionando na cidade e sim que apenas 21 foram indexados.
```sh
os:"Windows" country:br city:Bauru
```
![Shodan 14](https://i.imgur.com/TXBjH9E.png)

## Shodan via linha de comando (CLI)
> Esses exemplo foram testados em um sistema Linux - Debian Stretch.

### Instalando Shodan
Para instalar o **shodan** temos diversas formas , no site oficial eles recomendam o uso de **easy_install** e é possivel usar tambem o **pip**.

### Instalação via easy_install
```sh
easy_install shodan
```

Caso queira instalar a versão mais antiga da biblioteca podemos usar
```sh
easy_install -U shodan
```

### Instalando via PIP e PIP3 (Python Package Index)
Podemos usar o **PIP** para o python e o **PIP3** para o python3.

#### Usando PIP
Caso queira instalar o **pip** ,usando apt.
```sh
apt-get install python-pip
```

Podemos instalar agora o pip
```sh
pip install shodan
```

#### Usando PIP3
Eu uso o **pip3** para as minhas instalações , mais todos são iguais.
```sh
apt-get install python3-pip
```

Agora podemos instalar o shodan usando o PIP3.
```sh
pip install shodan
```

## Obtendo Key
Podemos ir até o site do shodan e logar na sua conta como já foi explicado.

```sh
https://account.shodan.io
```

Lá no subdominio **account** vamos obter a nossa **API KEY** para nossos testes.

## Usando sua chave
Devemos inserir a nossa chave para usar o shodan sem problemas.
```sh
shodan init "RPyjZUBjabK1Yld5iKjc8vuPwjPQJDqh"
```

Essa é a minha Key e você deve inserir a sua , ela pode ser reiniciada caso precise.

Se tudo ocorreu bem vamos receber a mensagem **Successfully initialized**.

## Comaçando a explorar com Shodan CLI
Podemos usar o **Shodan** depois de inicializar ele usando **init**.

Vamos ver as opções que temos , podemos usar **--help** ou até **-h**.
```sh
shodan --help
```

E toda opção como por exemplo o **search** , pode ter uma outra opção de **help**.
```sh
shodan search --help
```

## Buscando informações de um determinado host
Podemos buscar informações de um determinado alvo usando o **host** , ele pode trazer informações importantes na hora de um reconhecimento baseado em **OSINT**.

Podemos ver informações como onde ele está localizado , portas abertas e qual é a organização que possui o IP.
Podemos usar a opção **host** seguido do endereço **IP**.
```sh
shodan host 104.18.55.48
```

## Qual o meu IP
Podemos usar a opção **myip** para nos retornar nosso endereço **IP**.
```sh
shodan myip
```

## Analisando numero de alvos (count)
Vamos imaginar o cenario em que temos em mãos um **exploit** ou até o **zero-day** do **Apache 2.4**.

Podemos ter uma ideia de quantos possíveis alvos estarão disponíveis , podemos usar a opção **count**.

```sh
shodan count Apache 2.4
```

Nesse caso foi retornado **70147** hosts usando o **Apache 2.4**.

## Salvando alvos (download)
Podemos criar um arquivo e salvar os alvos para analisar futuros host vulneráveis.

Vamos usar a opção **download**.

Vamos salvar o arquivo como nome de **apache-2.4**.

E vamos pesquisar por hosts usando **Apache 2.4**.
```sh
shodan download apache-2.4 Apache 2.4
```

Podemos ver a saida com **70147** possíveis alvos.
```sh

Search query:            Apache 2.4
Total number of results:    70147
Query credits left:        0
Output file:            apache-2.4.json.gz
  []  100%             
Notice: fewer results were saved than requested
Saved 100 results into file apache-2.4.json.gz
```

Devido a nossa conta ser uma conta **free** vamos ter apenas **100 resultados** salvos em nosso arquivo de saída.

O nosso arquivo de saida é o **apache-2.4.json.gz**.

## Filtrando arquivo usando (parser)
Podemos usar a opção **parser** para filtrar os dados obtidos em nossa pesquisa usando o **download** anteriormente.

Ele nos permite filtrar campos , filtrar o arquivo **JSON** em um **CSV** e é amigável para usar com outros programas.

O exemplo abaixo filtra o **IP** , **porta** e a **organização**.

Não podemos esquecer que o arquivo **apache-2.4.json.gz** foi criado usado a opção **download**.
```sh
shodan parse --fields ip_str,port,org --separator , apache-2.4.json.gz
```

A saída vai ser algo como
```sh
50.57.241.67,80,Liquid Web, L.L.C,
61.128.111.161,80,CNINFONET Xingjiang,
50.57.255.220,80,Liquid Web, L.L.C,
217.26.52.21,80,Hostpoint AG, Switzerland,
122.144.130.4,80,China Unicom Shanghai network
```

## Apenas buscando por alvos (search)
Podemos usar a opção **search** para buscar por alvos.

Por padrão ele vai exibir o **IP**, **Porta** , **nomes de host** e **dados do host**.

Podemos usar a opção **fields** para nos auxiliar a filtrar , no exemplo abaixo vai ser retornado **IP**,**porta**,**organização** e **hostnames** de possíveisralvos usando **Apache 2.4**.
```sh
shodan search --fields ip_str,port,org,hostnames Apache 2.4
```


A saída vai ser algo como
```sh
87.216.162.99   80      Jazz Telecom S.A.       99.162.216.87.static.jazztel.es
2a00:d70:0:b:2002:0:d91a:35a5   80              sl173.web.hostpoint.ch  
50.56.151.158   80      Liquid Web, L.L.C               
184.106.55.63   80      Rackspace Ltd.  lb1-n01.wc1.lan3.stabletransit.com      
217.26.52.127   80      Hostpoint AG, Switzerland       www.airbornescan.com    
159.135.21.159  80      Liquid Web, L.L.C               
77.20.51.99     80      Vodafone Kabel Deutschland      ip4d143363.dynamic.kabel-deutschland.de
202.104.180.155 3749    China Telecom Guangdong province Dongguan MAN netw
```



## Usando shodan com Python

Documentação Oficial
https://shodan.readthedocs.io/

Primeiro exemplo
https://shodan.readthedocs.io/en/latest/examples/basic-search.html
