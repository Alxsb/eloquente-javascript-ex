### Triângulo com Loop

Escreva um programa que faça sete chamadas a `console.log()` para retornar o seguinte triângulo:

	#
	##
	###
	####
	#####
	######
	#######

Uma maneira interessante para saber o comprimento de uma `string` é escrevendo `.length` após ela.

```javascript
var abc = "abc";
console.log(abc.length);
// → 3
```

A maioria dos exercícios contém um pedaço de código que pode ser utilizada para alterar e resolver o exercício. Lembre-se que você pode clicar em um bloco de código para editá-lo.

```javascript
var hash = '';
var counter = 0;

while (counter < 7) {
    console.log(hash = hash += '#');
    counter = counter + 1;
}
```

**Dicas:**

Você pode começar com um programa que simplesmente imprime os números de 1 a 7, na qual você pode derivar algumas modificações no exemplo de impressão de números dado no início do capítulo aqui, onde o loop foi introduzido.

Agora, considere a equivalência entre números e cadeias em um `hash` de caracteres. Você pode ir de 1 para 2 adicionando 1 (`+ = 1`). Você pode ir de "#" para "##", adicionando um caractere (`+ = "#"`). Assim, a solução pode acompanhar de perto o número, de impressão do programa.

### FizzBuzz

Escreva um programa que imprima usando `console.log()` todos os números de 1 a 100 com duas exceções. Para números divisíveis por 3, imprima `Fizz` ao invés do número, e para números divisíveis por 5 (e não 3), imprima `Buzz`.

Quando o programa estiver funcionando, modifique-o para imprimir `FizzBuzz` para números que são divisíveis ambos por 3 e 5 (e continue imprimindo `Fizz` e `Buzz` para números divisíveis por apenas um deles).

(Isto é na verdade uma pergunta de entrevista usada para eliminar uma porcentagem significativa de candidatos programadores. Então se você resolvê-la, você está autorizado de se sentir bem consigo mesmo).

```javascript
var numbers = 0;
var cnt = 0;

while (cnt < 100) {
    numbers = numbers + 1;
    if (numbers % 3 == 0 && numbers % 5 == 0)
        console.log("FizzBuzz(Divisivel por 3 e 5)");
    else if (numbers % 3 == 0)
        console.log("Fizz(Divisivel somente por 3)");
    else if (numbers % 5 == 0)
        console.log("Buzz(Divisivel somente por 5)");
    else console.log(numbers);
    cnt = cnt + 1;
}
```

**Dica:**

Interar sobre os números é trabalho claro de um loop, e selecionar o que imprimir é uma questão de execução condicional. Lembre-se do truque de usar o operador restante (`%`) para verificar se um número é divisível por outro número (terá zero de resto).

Na primeira versão, existem três resultados possíveis para cada número, então você irá criar uma cadeia de `if/else if/else`.

Na segunda versão o programa tem uma solução simples e uma inteligente. A maneira mais simples é adicionar um outro "ramo" para um teste preciso da condição dada. Para o método inteligente é construir uma sequência de caracteres contendo palavra ou palavras para a saída, que imprima a palavra ou o número, caso não haja palavra, fazendo o uso do operador elegante `||`.

### Tabuleiro de Xadrez

Escreva um programa que cria uma `string` que representa uma grade 8x8, usando novas linhas para separar os caracteres. A cada posição da grade existe um espaço ou um caractere "#". Esses caracteres formam um tabuleiro de xadrez.

Passando esta `string` para o `console.log` deve mostrar algo como isto:
```
  # # # #
   # # # #
  # # # #
   # # # #
  # # # #
   # # # #
  # # # #
   # # # #
```

Quando você tiver o programa que gere este padrão, defina a variável `size = 8` e altere programa para que ele funcione para qualquer `size`, a saída da grade de largura e altura.

```javascript
var hash = "";
var size = 15;
var cnt = 0
var cc = 0;

while (cc < size) {
    while (cnt < size) {
        hash = hash += "\n#"
        cnt = cnt + 1; 
    }
    console.log(hash);
    cc = cc + 1; 
}
```

**Dica:**

A sequência pode ser construída iniciando vazia ("") e repetidamente adicionando caracateres. O caracter para uma nova linha é escrito assim `\n`.

Utilize `console.log` para visualizar a saída do seu programa.

Para trabalhar com duas dimensões, você irá precisar de um loop dentro de outro loop. Coloque entre chaves os "corpos" dos loops para se tornar mais fácil de visualizar quando inicia e quando termina. Tente recuar adequadamente esses "corpos". A ordem dos loops deve seguir a ordem que usamos para construir a string (linha por linha, esquerda para direita, cima para baixo). Então o loop mais externo manipula as linhas e o loop interno manipula os caracteres por linha.

Você vai precisar de duas variáveis para acompanhar seu progresso. Para saber se coloca um espaço ou um "#" em uma determinada posição, você pode testar se a soma dos dois contadores ainda é divisível por (`% 2`).

Encerrando uma linha com um caracter de nova linha acontece após a linha de cima ser construída, faça isso após o loop interno, mas dentro do loop externo.
