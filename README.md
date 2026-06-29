# php-request-response-https-get-e-post
Maria Rangel, Miguel Roeda, Regina e Rafael Viana (grupo 3)

````
Os métodos HTTP GET e POST são os mais utilizados na comunicação entre clientes (navegadores) e servidores em aplicações web desenvolvidas com PHP. Eles permitem o envio e a recepção de dados por meio do protocolo HTTP, sendo fundamentais para formulários, sistemas de autenticação, pesquisas e integração com APIs. O PHP disponibiliza as superglobais $_GET e $_POST para acessar os dados enviados por esses métodos.

### GET
O método GET envia os dados pela URL, tornando-os visíveis ao usuário. É mais utilizado para consultas, pesquisas e páginas que não alteram informações no servidor. Os dados podem ser acessados no PHP pela superglobal $_GET.
Exemplo:
$nome = $_GET[‘nome’];

### POST
O método POST envia os dados no corpo da requisição, sem exibi-los na URL. É indicado para formulários de cadastro, login e outras operações que envolvem o envio de informações ao servidor. Os dados são acessados pela superglobal $_POST.
Exemplo:
$nome = $_POST[‘nome’];

O método GET é recomendado para consultas e pesquisas, enquanto o POST é mais adequado para envio e processamento de dados. A escolha correta do método contribui para a segurança e eficiência das aplicações web em PHP.

````

## O que é uma URL?
````

URL significa Uniform Resource Locator e é o endereço usado para localizar recursos na internet, como sites, imagens, vídeos e arquivos.

Como funciona?
O usuário digita a URL.
O navegador procura o servidor.
O servidor envia o conteúdo solicitado.
O navegador exibe a página.
Partes de uma URL

Exemplo: https://www.google.com.br

https:// → Protocolo seguro de comunicação.
www → Subdomínio da web.
google → Nome do domínio.
.com.br → Extensão do domínio.
Principais extensões
.com → Comercial/empresas.
.org → Organizações.
.edu → Instituições de ensino.
.gov → Governos.
.net → Redes e tecnologia.
.io → Empresas de tecnologia.
Domínios de países
.br → Brasil
.ar → Argentina
.jp → Japão
.uk → Reino Unido
Exemplos
https://www.google.com → Site comercial.
https://www.harvard.edu → Universidade.
https://www.gov.br → Governo brasileiro.
Conclusão

As URLs funcionam como endereços da internet, permitindo localizar e acessar páginas, arquivos, vídeos e outros conteúdos de forma rápida e organizada.

````

## Request

````
A Request ou requisição traduzindo diretamente para português, é o pedido que um cliente realiza a nosso servidor. Esse pedido contém uma série de dados que são usados para descrever exatamente o que o cliente precisa. Vamos pensar que um cliente precisa cadastrar um novo produto, ele deve passar todos os dados necessários para o cadastro acontecer de maneira correta, inclusive os dados que foram digitados pelo usuário em um formulário, no caso de uma aplicação web. No navegador toda vez que trocamos de página ou apertamos enter na barra de endereço uma nova request é feita. Independente se estamos apenas pedindo a exibição de uma página, cadastrando um novo recurso, atualizando ou excluindo.
Vimos que o cliente envia uma Request (requisição) ao servidor. Essa requisição possui todas as informações acerca do que o cliente espera receber de volta. O servidor web ao receber essas informações precisa enviar uma resposta ao cliente, nesse ponto entra a Response. A Response (resposta) nada mais é do que a resposta que o servidor envia ao cliente. Essa resposta pode conter os dados que realmente o cliente esperava receber ou uma resposta informando que alguma coisa deu errado.
Na prática: quando você clica em um link ou submete (posta) um formulário, uma requisição é enviada ao servidor (HTTP) e uma resposta é esperada pelo navegador, que causa uma atualização (refresh) ao chegar. Vamos supor que você clique ali na opção “Artigos” no menu lateral. O que acontece após o clique? Seu navegador envia uma requisição ao servidor, que retorna o resultado desta e, para o navegador mostrar esse resultado, você nota que a página teve que carregar novamente.

````
## QueryString

````

A QueryString é uma forma de enviar informações pela URL de um site. Ela é muito utilizada em sistemas web para pesquisas, filtros, paginação de páginas e identificação de registros.
Quando acessamos alguns sites, é comum encontrar parâmetros na URL. Esses parâmetros fazem parte da QueryString e servem para enviar dados ao servidor.
O que é QueryString?
A QueryString é a parte da URL que aparece após o símbolo ?.
Ela permite enviar informações para uma página sem a necessidade de formulários.
Exemplo
https://site.com/produto.php?id=10
Nesse exemplo:
•	produto.php é a página acessada.
•	id é o nome do parâmetro.
•	10 é o valor enviado.
O servidor recebe esse valor e pode utilizá-lo para exibir informações específicas.
Estrutura da QueryString
A estrutura básica é:
?parametro=valor
Com mais de um parâmetro:
?parametro1=valor1&parametro2=valor2
Exemplo
https://site.com/aluno.php?nome=Rafael&idade=18
Parâmetros enviados:
•	nome = Rafael
•	idade = 18
O símbolo & é utilizado para separar os parâmetros.
Como Funciona?
Quando o usuário acessa uma URL com QueryString, o navegador envia os parâmetros para o servidor.
Exemplo:
https://site.com/produto.php?id=15
O servidor recebe:
id = 15
Com essa informação, ele pode exibir o produto correspondente ao código 15.
Principais Utilizações
Pesquisas
Os mecanismos de busca utilizam QueryString para enviar o termo pesquisado.
Exemplo:
https://www.google.com/search?q=php
Filtros
Lojas virtuais utilizam QueryString para filtrar produtos.
Exemplo:
https://loja.com/produtos?categoria=tenis
Paginação
Sites utilizam QueryString para mostrar diferentes páginas de conteúdo.
Exemplo:
https://blog.com/artigos?pagina=2
Identificação de Registros
Sistemas utilizam QueryString para localizar informações específicas.
Exemplo:
https://empresa.com/funcionario?id=25
QueryString no PHP
No PHP, os valores enviados pela QueryString são acessados através da variável:
$_GET
Exemplo
URL:
http://localhost/perfil.php?nome=Rafael
Código PHP:
<?php

$nome = $_GET["nome"];

echo "Olá, " . $nome;

?>
Resultado:
Olá, nome
Vantagens
•	Fácil de utilizar.
•	Permite compartilhar links com informações.
•	Funciona bem para pesquisas e filtros.
•	Pode ser salva nos favoritos do navegador.
Desvantagens
•	Os dados ficam visíveis na URL.
•	Não é segura para informações confidenciais.
•	Possui limite de tamanho.
Exemplo inadequado:
https://site.com/login?usuario=rafael&senha=123456
A senha fica exposta para qualquer pessoa visualizar.
Relação com o Método GET
A QueryString funciona junto com o método HTTP GET.
Quando uma URL possui parâmetros, eles são enviados através de uma requisição GET.
Por isso, em PHP os dados são acessados utilizando a variável:
$_GET

Conclusão
A QueryString é uma maneira simples e eficiente de enviar informações através da URL. Ela é muito utilizada em pesquisas, filtros, paginação e identificação de registros.
No PHP, os dados enviados podem ser acessados pela variável **$_GET**. Apesar de ser uma ferramenta muito útil, deve ser utilizada com cuidado, evitando o envio de informações sensíveis pela URL.

````

PHP Manual: https://www.php.net/manual/pt_BR/
MDN Web Docs: https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Methods
GeeksforGeeks: https://www.geeksforgeeks.org/php/http-get-post-methods-php/
https://www.treinaweb.com.br/blog/o-que-e-http-request-get-post-response-200-404
https://imasters.com.br/back-end/requisicoes-assincronas-em-php-usando-ajax-parte-01
https://www.php.net/manual/pt_BR/context.http.php
https://pt.stackoverflow.com/questions/372459/qual-%C3%A9-a-finalidade-dos-objetos-request-e-response-de-um-framework-web
