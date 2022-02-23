# Difference!
Nesse pequeno exemplo, vemos ver diferença de se utilizar React e JavaScript Puro, o exemplo consiste em criar um carrinho de compra, onde quando o usuário clica em comprar adicionara mais um no total e calculará o novo preço com base no total, vamos utilizar um valor fixo de 250 reais. 

## Primeiro vamos analisar o código JavaScript Puro
Primeiramente vamos criar as tags do HTML que vamos manipular com o javascript. Para isso vamos criar as tags

    <p>Total<span id="total"><>/span</p>
    <p>Preço<span id="preco"><>/span</p>
    <button id="compra">Comprar</button>
O código acima, vamos mostrar na tela  **Total** e **Preço**  as informações de quantidade vamos adicionar dinamicamente através dos da tag span usando o *id* **total** e **preco** já a tag button vamos utilizar o *id* **compra** Cada vez que o usuario clicar no botão, vamos criar uma função que adicionará mais um no total e atualizará o preço com base nesse total.

    const  total  =  document.getElementById("total");
    const  preco  =  document.getElementById("preco");
    const  compra  =  document.getElementById("compra");
O codigo acima vamos criar as variaveis com base no *id* que declaramos no HTML, isso é importe pois agora vamos utilizar as variaveis.

    let contador = 1;
Também é importante criarmos uma variavel chamada **contador** para termos um inicio e controle ao longo do codigo

Podemos começar pegando o click do button, para isso usamos a variavel **compra** e usamos o metodo do js chamado *addEventListener*, fazemos isso como mostra o codigo abaixo

    compra.addEventListener('click', lidarComClick);
Pegamos o objeto **compra** e acessamos o metodo dentro dos parênteses passamos o 'click' e em seguida passamos a função que vamos criar agora.

    function lidarComClick(){
	    contador ++;
	    atualizarValor(contador + 1);
    }
Na função acima pegamos a variável **contador** e acrescentamos mais 1 a cada click, podemos notar que aparece uma função chamada **atualizarValor** devemos criar essa função para adicionar o total no valor, para que assim a cada click o total irá atualizar o valor

    function atualizarValor(contador){
	    total.innerText = contador;
	    preco.innerText = contador * 250;
    }	
    atualizarValor(contador)
A função **atualizarValor** recebe o argumento **contador** pegamos o objeto **total** e acessamos a propriedade innerText que representa o conteudo textual "renderizado" e atribuimos ao contador. Fazemos a mesma coisa com o objeto **preco** porém multiplicamos por 250, que é o valor do item no carrinho. E no final chamamos essa função e passamos o argumento **contator**

## Agora vamos analisar o codigo utilizando o react