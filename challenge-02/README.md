# Desafio da semana #2

Nesse exercício, você está livre para escolher os nomes para suas variáveis e funções! :smile:

```js
// Crie uma função que receba dois argumentos e retorne a soma dos mesmos.
function soma(x,y) {
    return x + y;
}
soma(10,5);

// Declare uma variável que receba a invocação da função criada acima, passando dois números quaisquer por argumento, e somando `5` ao resultado retornado da função.
var resultado = soma(10,5) + 5;

// Qual o valor atualizado dessa variável?
20

// Declare uma nova variável, sem valor.
var semValor;

/*
Crie uma função que adicione um valor à variável criada acima, e retorne a string:
O valor da variável agora é VALOR.
Onde VALOR é o novo valor da variável.
*/
function valor(){
    semValor = 30;
    return "O valor da variável agora é " + semValor;
}

// Invoque a função criada acima.
valor()

// Qual o retorno da função? (Use comentários de bloco).
/*O valor da variável agora é 30*/

/*
Crie uma função com as seguintes características:
1. A função deve receber 3 argumentos;
2. Se qualquer um dos três argumentos não estiverem preenchidos, a função deve retornar a string:
Preencha todos os valores corretamente!
3. O retorno da função deve ser a multiplicação dos 3 argumentos, somando `2` ao resultado da multiplicação.
*/
function tresArgumentos(x,y,z) {
    if (x == null || y == null || z == null) { //realizei o exercicio com null porém o correto é undefined pois no JS para um argumento ser null, o null precisa ser passado para ele e nesse caso não passamos nada, logo o argumento é undefined e sempre use ===
        return "Preencha todos os valores corretamente!"
    } else {
        return x*y*z + 2;
    }
}

//*correção do exercicio* outra maneira de fazer sem o else pois o returnsó funciona dentro da função e se o if for falso, a função automaticamente ignora no if e retorna o return
function tresArgumentos(x,y,z) {
    if (x === undefined || y === undefined || z === undefined) {
        return "Preencha todos os valores corretamente!"
    }
    return (x*y*z) + 2;
}

// Invoque a função criada acima, passando só dois números como argumento.
tresArgumentos(1,2);

// Qual o resultado da invocação acima? (Use comentários para mostrar o valor retornado).
/*Preencha todos os valores corretamente!*/

// Agora invoque novamente a função criada acima, mas passando todos os três argumentos necessários.
tresArgumentos(1,2,5);

// Qual o resultado da invocação acima? (Use comentários para mostrar o valor retornado).
/* 12 */

/*
Crie uma função com as seguintes características:
1. A função deve receber 3 argumentos.
2. Se somente um argumento for passado, retorne o valor do argumento.
3. Se dois argumentos forem passados, retorne a soma dos dois argumentos.
4. Se todos os argumentos forem passados, retorne a soma do primeiro com o segundo, e o resultado, dividido pelo terceiro.
5. Se nenhum argumento for passado, retorne o valor booleano `false`.
6. E ainda, se nenhuma das condições acima forem atendidas, retorne `null`.
*/
function umDoisTres(x,y,z) {
    var x
    var y
    var z
    if ((x !== undefined) && (y == undefined) && (z == undefined) || (x == undefined) && (y !== undefined) && (z == undefined) || (x == undefined) && (y == undefined) && (z !== undefined)) { //não precisava fazer todas essas comparações, pois ao passar um só argumento ele automaricamente é o x, logo não precisa verificar se o y e z são diferentes de undefined
        return x || y || z;
    }
    else if ((x !== undefined) && (y !== undefined) && (z == undefined) || (x == undefined) && (y !== undefined) && (z !== undefined) || (x !== undefined) && (y == undefined) && (z !== undefined)) { //mesmo problema do if acima
        return x + y || y + z || x + z;
    }
    else if ((x != undefined) && (y != undefined) && (z != undefined)){
        return (x+y)/z;
    }
    else if ((x == undefined) && (y == undefined) && (z == undefined)) { //ficou faltando um sinal de = deveria ser === e não apenas ==
        return "false"; //não precisava das aspas
    }
    else {
        return "null"; //não precisava das aspas
    }
}

//correção do exercicio
function umDoisTres(x,y,z) {
    if ((x !== undefined) && (y === undefined) && (z === undefined)) {
        return x || y || z;
    }
    else if ((x !== undefined) && (y !== undefined) && (z === undefined)) {
        return x + y || y + z || x + z;
    }
    else if ((x !== undefined) && (y !== undefined) && (z !== undefined)){
        return (x+y)/z;
    }
    else if ((x === undefined) && (y === undefined) && (z === undefined)) {
        return false;
    }
    else {
        return null;
    }
}

// Invoque a função acima utilizando todas as possibilidades (com nenhum argumento, com um, com dois e com três.) Coloque um comentário de linha ao lado da função com o resultado de cada invocação.
umDoisTres() //false
umDoisTres(1) //1
umDoisTres(1,5) //6
umDoisTres(1,5,2) //3

```
