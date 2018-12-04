## Google

## Onde começou ?
Em 2005 foi iniciado a maior fonte de informações públicas vista até hoje , ela foi fundada por Larry Page e Serget Brin.
O Google faz todo o trabalho buscando rastrear páginas na internet através de páginas conhecidas , links e diversas técnicas para armazenar em seus servidores dados que vão ajudar na busca dos usuários.
Atualmente podemos encontrar desde simples pesquisas , diretórios, arquivos sensíveis , músicas , informações sobre uma pessoa e até informações sensíveis que poderiam ser usadas para a criação de uma conta usando dados públicos de uma pessoa.

## Como funciona ?
Basicamente ele usa palavras chave para auxiliar na busca , além de operadores que podem nos auxiliar no filtro de informações.

O Google Basicamente faz o uso de operadores , ai ele faz uma busca para localizar sequências específicas de texto dentro de resultados de pesquisa.

Podemos usar o Google para buscar por
- Versões específicas vulneráveis
- Localizar todas as páginas que possuem um determinado texto
- Paginas de administração
- Backups de arquivos

E tudo que pode estar sendo indexado pelo Google.

## Operadores
O Google disponibiliza para uso operadores que podem nos ajudar na busca , também ajudam no dia a dia e além disso ele disponibiliza diversas ferramentas.

Vamos conhecer os operadores básicos
### Operações

Adição
```sh
420+30
```

Multiplicação
```sh
4*2
```

Divisão
```sh
50/25
```

Subtrair
```sh
25-5
```

### site
O operador site é usado para determinar uma URL especifica, dessa forma verificar resultados a partir de determinados sites ou domínios.
```sh
site:.gov
site:.edu.br
site:inforeason.com.br
```

### Filetype
Podemos buscar por arquivos usando o operador **filetype** , podemos buscar pelas extensões como pr exemplo o **PDF** e buscar por
- Apresentações
- Livros
- Papers

Exemplo de uso
```sh
filetype: pdf
```

### Intitle
Podemos buscar por informações contidas em títulos de sites , vamos usar o operador **intitle** para isso e usa da seguinte forma:
```sh
intitle:"Bem vindo"
```

### Allintitle
O Allintitle é diferente do **intitle** , ele busca por palavras que devem ser encontradas no title da pagina.
```sh
allintitle:admin
```

### Inurl
Usando o **inurl** podemos buscar por por URLS , no exemplo a baixo ele vai buscar por links que contenham admin.
```sh
inurl:admin
```

### Cache
Podemos usar a opção **cache** para ver como era a pagina quando o google a visitou pela ultima vez.
```sh
cache:facebook.com
```

### Ext
Podemos usar o **ext** para buscar por extensões , por exemplo:
- txt
- pdf
- sql

Buscando por arquivos **sql**.
```sh
ext:sql
```

### Allinurl
O allinurl é semelhante ao **inurl**, só que ele funciona de forma restritiva buscando apenas pelas string passada.

Buscando por paginas de login.
```sh
allinurl: login
```

### Intext
É possível buscar por strings dentro de um texto em uma pagina.
```sh
intext: @gmail
```

### -
Quando você usa um traço antes de uma palavra ou site, ele acaba excluindo o resultado que incluem essa palavra ou site.

Isso pode ser útil para ajudar no filtro de um site , por exemplo:

Queremos buscar por google.com , só que não queremos que retorne nenhum link do **www.google.com**.
Só precisamos usar o **-** na frente do queremos negar na busca.
```sh
google.com -www.google.com
```

### "
Podemos buscar por um conjunto especifico de palavras usando as **aspas** , dessa forma quando é colocado uma palavra ou frase entre aspas, os resultados incluem apenas páginas com as mesmas palavras e na mesma ordem do que está dentro das aspas.

Só podemos usar isso quando buscamos por uma determinada frase , senão acabamos excluindo diversos resultados validos.
```sh
"admin"
"Júlio César" Curriculo
```

## Docks
Agora que já conhecemos alguns dos Operadores podemos conhecer as Dorks , as dorks nada mais são que conjuntos de operadores e palavras chaves juntas e assim nos auxiliando ainda mais em nossa pesquisa.

### Buscando por index of
Podemos buscar por **Index of** em paginas do Governo , nesse exemplo estou usando os seguintes operadores:
- site
- intitle
- palavras chave

```sh
intitle: index of site:.gov.br
```

### Buscando por arquivos SQL
Vamos agora usar os operadores
- site
- ext
- palavras chave

```sh
site:org ext:sql password
ext:pdf site:globo.com -robots.txt
```

### Buscando por paginas de login do governo
É possível procurar por paginas de login usando os operadores
- intitle
- site

```sh
intitle:login site:gov
```

### Buscando por Dumps
Podemos buscar por dumps de banco de dados que estão indexados no google , vamos usar os operadores:
- filetype
- intext
- palavras chave

```sh
mysql dump filetype:sql :.com.br intext:password
```

### Buscando por Remote Desktop
Podemos buscar por ambientes de trabalho remotos que estão indexados no google , o Remote Desktop é usado para administrar servidores de forma remota e vamos usar apenas palavras chaves:
```sh
"Remote Desktop Web Connection"
```

Ou tambem usar o operador **intitle**.
```sh
intitle: "Remote Desktop Web Connection"
```

## Onde posso encontrar Dorks?
Temos alguns sites que compartilham Dorks e os mais conhecidos são os
- Exploit DB


### Exploit DB
Podemos buscar por Dorks no site Exploit DB , nele temos um conjunto de filtros e são eles:
- Tipo (Dos,local, remote e webapps)
- Plataformas (PHP,JSP,ASP e ETC)
- Autor
- Portas
- Tag(Remote, Injeção de código , Wordpress Core e ETC)

Veja o site
```sh
https://www.exploit-db.com/
```
