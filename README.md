# Lógica de programação II: pratique com desenhos, animações e um jogo

Curso da Alura sobre lógica de programação com HTML e Javascript.

URL do Curso -> [Lógica de programação II: pratique com desenhos, animações e um jogo](https://www.alura.com.br/curso-online-logica-programacao-pratica-com-desenho-animacoes-em-jogo)
![Lógica de programação II: pratique com desenhos, animações e um jogo](https://www.alura.com.br/assets/api/share/curso-logica-programacao-pratica-com-desenho-animacoes-em-jogo.png)
***
## Links Úteis
* [Notepad++](https://notepad-plus-plus.org/) - Editor de texto alternativo.
* [Sublime](https://www.sublimetext.com/) - Editor de texto com texto colorido.
* [Google Chrome](https://www.google.com/intl/pt-BR/chrome/) - Navegador recomendado para depuração de código no browser.

## Siglas
* API - *Application Programming Interface* - Interface de Programação de Aplicativos.

## 01 - Desenhando Gráficos com Canvas
* A *tag* **`<canvas></canvas>`** serve para podermos desenhar com o pincel em uma área em branco.
* Para definir a *largura* e a *altura* de um elemento, digitamos o *atributo* `width` e `height` dentro de uma tag, (`<canvas width="600" height="400"></canvas>`).
* A função **`getContext()`**, recebe como parâmetro o tipo do pincel que será utilizado para pintar a tela, já que podemos ter vários gráficos em 2d, 3d, etc.
* A função **`fillRect()`** desenha um retângulo na tela, informando o ponto *X* e *Y* no *plano cartesiano* em que começará o desenho (Na tela de um computador, o *eixo X* começa do canto superior esquerdo até o canto superior direito, e o *eixo Y* começa do canto superior esquerdo até o canto inferior esquerdo), e a *largura* e a *altura* do retângulo que desejamos desenhar.
* Para indicar a cor do pincel que queremos desenhar, utilizamos o **`fillStyle`** e informamos a cor que queremos utilizar.
* Uma **propriedade** é diferente de uma **função**, pois ela equivale à uma variável, mas aplicada em um elemento.
* Para fazer um **comentário de bloco** em JavaScript, utilizamos o `/*` e um `*/` para delimitar o bloco de comentário.
* A função **`beginPath()`** indica para o pincel que ele deve iniciar um caminho.
* A função **`moveTo()`** indica o ponto inicial do desenho que será feito.
* A função **`lineTo()`** indica que ele deve iniciar uma linha até a posição específicada pelo *eixo X* e *eixo Y*.
* A função **`fill()`** preenche a forma que foi desenhada.
* A função **`arc()`** traça uma esfera, informando o *posicionamento* da esfera, no eixo *X* e *Y*, o *raio* da esfera, e o *ângulo inicial* e o *ângulo final*, em *radianos* (multiplicado por 3,14).

## 02 - Extraindo Funções
* A propriedade **`strokeStyle`** recebe uma cor, que será a cor da borda.
* A função **`strokeRect()`** desenha uma borda em volta dos parâmetros específicados, como na função **`fillRect()`**.
* A *propriedade* **`pincel.font`** define uma *fonte de texto* para o pincel.
* A função **`fillText`** escreve um texto no painel, passando como parâmetro o texto que irá aparecer, e as coordenadas *X* e *Y*.
* A propriedade **`onclick`**, assim como outras, é ativada pelo próprio navegador executando a *função* que foi atrelada à ela, ao inserir um parâmetro na *função* em que irá executar, o navegador cria um objeto contendo várias informações sobre o **evento** em que aconteceu a *função*.

## 03 - Interagindo com o Usuário
* A propriedade **`oncontextmenu`** recebe uma *função* que será ativada toda vez que o usuário clicar com o botão direito do mouse no objeto em que ela foi atribuida.
* Uma **função anônima** é uma função que não possui um nome.
* Uma **função anônima** pode ser atrelada a uma propriedade que requer uma função para ser executada, exemplo:
```
tela.onmousemove = function(evento) {
    if(desenha) {
        var x = evento.pageX - tela.offsetLeft;
        var y = evento.pageY - tela.offsetTop;

        pincel.fillStyle = 'blue';
        pincel.beginPath();
        pincel.arc(x, y, 10, 0, 2 * 3.14);
        pincel.fill();
    }

    console.log(x + ',' + y);
}

tela.onmousedown = function() {
    desenha = true;
}

tela.onmouseup = function() {
    desenha = false;
}
```
* Um **`<input type="color">`** exibe uma paleta de cores no navegador. Quando o usuário confirmar a cor, ela é armazenada na variável `input`, com o valor da cor escolhida.

## 04 - Movendo Elementos, Animações Simples
* A função **`clearRect()`** limpa a tela informando a posição *X* e *Y* de inicio e as dimensões de *largura* e *altura*.
* A função **`setInterval()`** chama uma função a cada intervalo de tempo, recebendo como *parâmetros* a função que irá chamar e o tempo em *milisegundos* entre os intervalos da chamada.
* Uma variável pode ter um **escopo de *função***, ou seja, só dentro da função ou ter um **escopo chamado de *escopo global***, em que ela é declarada fora de um *função*.