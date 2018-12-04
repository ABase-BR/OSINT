```sh
https://www.bing.com/
```


Também temos diversas fontes de informações que são válidas como o Bing que é um buscador desenvolvido pela Microsoft que também nos retorna informações que podemos usar. Infelizmente devido ao grande uso do Google as pessoas acabam deixando de usar , o DuckDuckGo ou até nem conhecendo os projetos.

## Operadores

### contains
Usando o operador **contains** podemos manter os resultados em sites que possuem links para os tipos de arquivo especificados.

Por exemplo , podemos procurar por sites que contenham links para arquivos Microsoft Windows Media Áudio (.wma) , veja um exemplo:
```sh
rap contains:wma
```
bing-contains-1.png

Podemos ver o resultado marcado que fica no seguinte link:
```sh
http://www.sapo.salvador.ba.gov.br/paginas/internas_festival_musicas/musicas_rap_meio.htm
```

Analisando essa pagina podemos encontrar o link para o arquivo:
```sh
http://www.sapo.salvador.ba.gov.br/arq/musicas1/03_rap_meio.wma
```

### filetype
Podemos usar o **filetype** para retornar apenas páginas com um tipo de arquivo especificado.

Veja um exemplo para localizar relatórios criados no formato PDF:
```sh
relatorio filetype:pdf
```

Dessa forma podemos encontrar diversos resultado de arquivos PDF.

### url
É possível analisar um determinado domínio , assim verificando se consegue buscar informações e se está indexado ao Bing.

Para verificar se o domínio Microsoft está no índice podemos usar
```sh
url:google.com
```

### site
O operador **site** verifica páginas da Web que pertencem a um site especificado.

Veja um exemplo do uso do operador site , ele retorna diversos subdomínios do diretório usado
```sh
site:google.com
```

Com o uso do site podemos procurar domínios , subdomínios e diretórios com até dois níveis.
