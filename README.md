<h1 align="center">Cadastro de Ecommerce</h1>
<p align="center">Projeto referente a atividade feita em sala aula de implementação de banco de dados em um código html usando phpmyadmim para criação de um site Ecommerce que pode cadastrar informações no banco de dados.</p>
<p align="center"><code>Usando de base um site pré desenvolvido pelo professor, criamos em sala mais três páginas no mesmo modelo para cadastrar produtos,</code> <code>marca e categoria.</code></p>

* Com ajuda de [Marina Dias](https://github.com/MarshyyUWU) <3


## Funcionalidades

![Como funciona os cadastros de produto no site](gifCad.gif)


### Produtos
``` php
<?php
include_once('controller/conexao.php');
 
$categoria      = $_POST['seleciona_categoria'];
$marca          = $_POST['seleciona_marca'];
$nome_produto   = $_POST['nome'];
$descricao      = $_POST['descricao'];
$estoque        = $_POST['estoque'];
$preco          = $_POST['preco'];
 
$grava_produto = "INSERT INTO produtos(`IDCATEGORIA`, `IDMARCA`, `NOME`,
`DESCRICAO`, `ESTOQUE`, `PRECO`) VALUES
('$categoria','$marca','$nome_produto','$descricao','$estoque','$preco')";
 
$result_gravacao = mysqli_query($mysqli, $grava_produto);
 
    if(mysqli_affected_rows($mysqli) != 0){
        echo "
        <META HTTP-EQUIV=REFRESH CONTENT = 'O;URL=produtos.php'>
        <script type=\"text/javascript\">
        alert('Produto cadastrado com sucesso');
        </script>";
 
        }else{
        echo "
        <META HTTP-EQUIV=REFRESH CONTENT = 'O;URL=produtos.php'>
        <script type=\"text/javascript\">
        alert('Produto não cadastrado');
        </script>";
}
?>
```

### Categoria
```php
<?php
include('controller/conexao.php');

$descricao = $_POST['descricao'];

echo "<h3>Descrição: $descricao </h3></br>";

$cad_categoria = "INSERT INTO categoria(DESCRICAO) VALUES ('$descricao')";

if(mysqli_query($mysqli, $cad_categoria)){
    echo "<h1>Categoria cadastrada com sucesso!</h1></br>";
} else {
    echo "Erro: " . $cad_categoria . "</br>" . mysqli_error($mysqli);
}

mysqli_close($mysqli);

?>
```

### Marca
```php
<?php
include('controller/conexao.php');

$descricao = $_POST['descricao'];

echo "<h3>Descrição: $descricao </h3></br>";

$cad_marca = "INSERT INTO marca(DESCRICAO) VALUES ('$descricao')";

if(mysqli_query($mysqli, $cad_marca)){
    echo "<h1>Marca cadastrada com sucesso!</h1></br>";
} else {
    echo "Erro: " . $cad_marca . "</br>" . mysqli_error($mysqli);
}

mysqli_close($mysqli);

?>
```

## Tecnologias

* ``Php``
* ``CSS3``
* ``Mysql``
* ``HTML5``
* ``Github``
* ``Phpmyadmim``
* ``Javascript``
* ``Bootstrap 5``
* ``Vscode - Version: 1.70.0``

## Contato

Informações de contato para suporte ou perguntas sobre o projeto.

- **Email:** almeidajuliaoliveira00@gmail.com
- **GitHub:** [Julia Oliveira](https://github.com/julia-oliveira00)
