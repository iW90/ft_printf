# 42 Cursus - ft_printf

<img src="https://game.42sp.org.br/static/assets/achievements/ft_printfm.png" alt="completion-with-bonus-badge" align="left">

Neste projeto é recriada parte da famosa função **printf** da biblioteca **stdio.h**. A **ft_printf** deve ser capaz de formatar e imprimir na tela diferentes tipos de dados como strings, caracteres, inteiros, hexadecimais e ponteiros. Aqui a lição é sobre `variadic arguments`, que nos permite variar a quantidade de parâmetros que podem ser passadas para uma função. O bônus aborda as flags que podemos utilizar para formatar as saídas do **printf**. Assim como os dois projetos anteriores, a **ft_prinft** poderá ser utilizada em projetos futuros.

## Especificadores e Flag implementadas <img src="https://img.shields.io/badge/GRADE-102%2F100-green" align="right">

### Format Specifiers

| Specifiers | Descrição |
|:---:|:---|
|——————|——————————————————————————————————————————|
| `%%` | Imprime '%' na tela. |
| `%c` | Imprime um caractere. |
| `%s` | Imprime uma string. |
| `%p` | Imprime um endereço de ponteiro. |
| `%i` | Imprime um inteiro (positivo ou negativo). |
| `%d` | Imprime um decimal (idêntico a `%i`). |
| `%u` | Imprime um inteiro (somente positivo). |
| `%x` | Imprime um hexadecimal (minúsculo). |
| `%X` | Imprime um hexadecimal (maiúsculo). |

### Bonus Flags

| Flag | Descrição |
|:---:|:---|
|——————|——————————————————————————————————————————|
| `#` | \[**Bônus**]: Imprime '**0x**' ou '**0X**' na frente do hexadecimal quando usado com `%x` ou  `%X`, respectivamente. |

## Compilação e Execução

No terminal, digite:

```
make
```

Caso queira executar a versão com bônus, digite:

```
make bonus
```

Será necessário criar uma main.c com o cabeçalho `#include "ft_printf.h"` e depois compilar com a libftprintf.a:

```
cc -Wall -Wextra -Werror main.c libftprintf.a && ./a.out
```

## Bônus *(não implementado)*: Format Specifiers

O bônus da ft_printf contempla a implementação de vários especificadores de formato, descritos abaixo.

Estes são opcionais, por isso não foram implementados, mas segue uma explicação breve sobre suas combinações e implementações:

- Formatação:

	```
	%[flags][width][.precision]specifier
	```

### Flags

| Flag | Descrição |
|:---:|:---|
|——————|——————————————————————————————————————————|
| `-` | Justifica o resultado à esquerda dentro do campo (é justificado à direita por padrão). |
| `+` | Força a preceder o resultado com um sinal de mais ou menos (+ ou -), mesmo para números positivos (normalmente apenas números negativos são precedidos por um sinal). |
| ` ` | Se não houver sinal, um espaço é anexado ao início do resultado. |
| `#` | Usado com especificadores x ou X, o valor é precedido por 0x ou 0X, respectivamente, para valores diferentes de zero. |
| `0` | Preenche com zeros à esquerda de números ao invés de espaços. |

### Width

| Width | Descrição |
|:---:|:---|
|——————|——————————————————————————————————————————|
| *\<number>* | Número mínimo de caracteres a serem impressos. Se o valor a ser impresso for menor que esse número, o resultado será preenchido com espaços em branco. O valor não é truncado mesmo se o resultado for maior. |
| `*` | A largura não é especificada como formato na string, mas como um argumento de valor inteiro adicional precedendo o argumento que deve ser formatado. |

### Precision

| Precision | Descrição |
|:---:|:---|
|——————|——————————————————————————————————————————|
| `.`*\<number>* | Para especificadores inteiros (`d`, `i`, `u`, `x`, `X`), a precisão especifica o número mínimo de dígitos a serem escritos. Se o valor a ser escrito for menor que esse número, o resultado será preenchido com zeros à esquerda. O valor não é truncado, mesmo que o resultado seja mais longo. Uma precisão de 0 significa que nenhum caractere é escrito para o valor 0. Para `s`, este é o número máximo de caracteres a serem impressos (por padrão, todos os caracteres são impressos até que o caractere nulo final seja encontrado). Para o tipo `c`, não tem efeito. Quando nenhuma precisão é especificada, o padrão é 1. Se o período for especificado sem um valor explícito para precisão, 0 será assumido. |
| `.(*)` | A precisão não é especificada como formato na string, mas como um argumento de valor inteiro adicional precedendo o argumento que deve ser formatado. |

## Testers Utilizados

- [Tripoulli](https://github.com/Tripouille/printfTester)
- [Paulo Santana Tester](https://github.com/paulo-santana/ft_printf_tester)
