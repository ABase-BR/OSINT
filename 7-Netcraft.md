# Netcraft
O **Netcraft** é um ótimo projeto para buscar informações baseadas em OSINT.

Veja o site:
```sh
  www.netcraft.com
```
## Conhecendo a Netcraft
A Netcraft é uma empresa com sede em Bath na Ingraterra , ela é uma empresa que presta serviços
- Anti fraud
- Anti Phishing
- Testes em aplicativos
- Revisão de código
- Pentests

## Buscando informações usando o Netcraft
Podemos buscar informações sobre
- Webserver
- Subdominios


Veja um exemplo buscando informações sobre o Google
![Netcraft](https://i.imgur.com/bTUwhUm.png)


No resultado podemos encontrar diversos subdomínios , sistema operacional usado e até informações sobre o bloco de rede que nesse caso é de responsabilidade da Google.
![Netcraft 2](https://i.imgur.com/DoY1t6P.png)

Podemos testar também através do link a baixo:
```sh
https://searchdns.netcraft.com/
```

### Usando o Toolbar
Ele pode ser utilizado para encontrar subdomínios.

Podemos procurar mais opções do **Netcraft** , mais recomendo usar
```sh
 http://toolbar.netcraft.com/site_report?url=
```

Vou usar como exemplo o Google , ele é interessante pois podemos descobrir o range de IPS da rede , sem interagir com o host , podemos descobrir outros IPS e assim outros servidores importantes na rede.

Podemos ver informações como:
- Titulo do site
- Rank do site
- Descrição
- Palavras chaves
- Linguagem primaria
- Netcraft analise de Risco
- Visto pela primeira vez

Também é possível ver informações de rede como:
- Site
- Domínio
- IP
- IPv6
- Domínio Registrador
- Organização responsável
- Hospedado em qual pais
- Empresa que hospeda
- DNS reverso (DNS lookup é a determinação de um domínio associado a um IP)
- Email do DNS admin
- NameServer

Podemos ver logo a baixo do resultado em **Hosting History** o dono do IP , nesse caso é em **Netblock owner** que é onde encontramos os responsáveis pelo **Bloco de rede**.

Ao fazer um teste com a **google.com** podemos ver que o dono é **Google LLC 1600 Amphitheatre Parkway Mountain View CA US 94043**.

Podemos ver o resultado passando o mouse em cima **https://toolbar.netcraft.com/netblock?q=GOOGLE,172.217.0.0,172.217.255.255** e nesse caso sem fazer uma pesquisa direta podemos ver que o range de rede é
```sh
172.217.0.0
```

Até
```sh
172.217.255.255
```

Além disso podemos ver quais tecnologias são usadas como por exemplo , no servidor e no cliente.
