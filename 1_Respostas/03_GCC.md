Para todas as questões, compile-as com o gcc e execute-as via terminal.

1. Crie um "Olá mundo!" em C.
```c
#include<stdio.h>

int main(){
        printf("Olá Mundo!\n");
        return 0;
}

```
2. Crie um código em C que pergunta ao usuário o seu nome, e imprime no terminal "Ola " e o nome do usuário. Por exemplo, considerando que o código criado recebeu o nome de 'ola_usuario_1':

```bash
$ ./ola_usuario_1
$ Digite o seu nome: Eu
$ Ola Eu
```
```c
#include<stdio.h>

int main(){
        char nome[20];
        printf("Digite o seu nome:");
        scanf("%s", nome);
        printf("Olá %s \n", nome);
        return 0;
}
        /* Pode-se usar a função gets(); que considera até espaços
        char nome[60]
        printf("Digite o seu nome:");
        gets(nome);
        printf("Olá %s \n", nome);
        return 0;
        */
```

3. Apresente os comportamentos do código anterior nos seguintes casos:

(a) Se o usuário insere mais de um nome.
```bash
$ ./ola_usuario_1
$ Digite o seu nome: Eu Mesmo
```
```
Usando a função scanf():
A função scanf armazena apenas a string antes do caractere espaço,portanto retorna "Eu"
```

(b) Se o usuário insere mais de um nome entre aspas duplas. Por exemplo:
```bash
$ ./ola_usuario_1
$ Digite o seu nome: "Eu Mesmo"
```
```
Usando a função scanf():
A função scanf armazena apenas a string antes do caractere espaço,portanto retorna ""Eu"
```
(c) Se é usado um pipe. Por exemplo:
```bash
$ echo Eu | ./ola_usuario_1
```
```
É escrito no terminal sem requisitar entrada com nome: "Digite o seu nome:Olá Eu"
```
(d) Se é usado um pipe com mais de um nome. Por exemplo:
```bash
$ echo Eu Mesmo | ./ola_usuario_1
```
```
É escrito no terminal sem requisitar entrada com nome: "Digite o seu nome:Olá Eu"
```

(e) Se é usado um pipe com mais de um nome entre aspas duplas. Por exemplo:
```bash
$ echo "Eu Mesmo" | ./ola_usuario_1
```
```
É escrito no terminal sem requisitar entrada com nome: "Digite o seu nome:Olá Eu"
```

(f) Se é usado o redirecionamento de arquivo. Por exemplo:
```bash
$ echo Ola mundo cruel! > ola.txt
$ ./ola_usuario_1 < ola.txt
```
```
É escrito no terminal sem requisitar entrada com nome: "Digite o seu nome:Olá Ola"
```
4. Crie um código em C que recebe o nome do usuário como um argumento de entrada (usando as variáveis argc e  `*argv[])`, e imprime no terminal "Ola " e o nome do usuário. Por exemplo, considerando que o código criado recebeu o nome de 'ola_usuario_2':

```bash
$ ./ola_usuario_2 Eu
$ Ola Eu
```
```c
#include<stdio.h>

int main( int argc, char *argv[] )
{
        printf("Olá %s \n", argv[1]);
        return 0;
}
```

5. Apresente os comportamentos do código anterior nos seguintes casos:

(a) Se o usuário insere mais de um nome.
```bash
$ ./ola_usuario_2 Eu Mesmo
```
```
Imprime na tela apenas o argumento 'Eu', o argumento 'mesmo' é um segundo argumento portanto não é impresso.
```

(b) Se o usuário insere mais de um nome entre aspas duplas. Por exemplo:
```bash
$ ./ola_usuario_2 "Eu Mesmo"
```
```
É impresso na tela 'Olá Eu mesmo', porque o que está dentro das aspas duplas é considerado um só argumento, portanto 'Eu mesmo' é a string do argv[1].
```

(c) Se é usado um pipe. Por exemplo:
```bash
$ echo Eu | ./ola_usuario_2
```
```
Imprime na tela apenas o argumento 'Eu', o argumento 'mesmo' é um segundo argumento portanto não é impresso.
```

(d) Se é usado um pipe com mais de um nome. Por exemplo:
```bash
$ echo Eu Mesmo | ./ola_usuario_2
```
```
É impresso na tela ' Olá (null) ', isso deve-se por causa que não foi passado nenhum argumento além de ./ola_usuario2 na chamada da função.
```

(e) Se é usado um pipe com mais de um nome entre aspas duplas. Por exemplo:
```bash
$ echo "Eu Mesmo" | ./ola_usuario_2
```
```
É impresso na tela ' Olá (null) ', isso deve-se por causa que não foi passado nenhum argumento além de ./ola_usuario2 na chamada da função.
```

(f) Se é usado o redirecionamento de arquivo. Por exemplo:
```bash
$ echo Ola mundo cruel! > ola.txt
$ ./ola_usuario_2 < ola.txt
```
```
É impresso na tela ' Olá (null) ', isso deve-se por causa que não foi passado nenhum argumento além de ./ola_usuario2 na chamada da função.
```

6. Crie um código em C que faz o mesmo que o código da questão 4, e em seguida imprime no terminal quantos valores de entrada foram fornecidos pelo usuário. Por exemplo, considerando que o código criado recebeu o nome de 'ola_usuario_3':

```bash
$ ./ola_usuario_3 Eu
$ Ola Eu
$ Numero de entradas = 2
```
```c
#include<stdio.h>

int main( int argc, char *argv[] )
{
        printf("Olá %s \n", argv[1]);
        printf("Número de entradas = %d \n", argc);
        return 0;
}
```

7. Crie um código em C que imprime todos os argumentos de entrada fornecidos pelo usuário. Por exemplo, considerando que o código criado recebeu o nome de 'ola_argumentos':

```bash
$ ./ola_argumentos Eu Mesmo e Minha Pessoa
$ Argumentos: Eu Mesmo e Minha Pessoa
```
```c
#include<stdio.h>

int main( int argc, char *argv[] )
{
        printf("Argumentos: ");
        int i;
        for (i=1; i < argc; i++){
                printf("%s ", argv[i]);
        }
        printf("\n");
        return 0;
}

```

8. Crie uma função que retorna a quantidade de caracteres em uma string, usando o seguinte protótipo:
`int Num_Caracs(char *string);` Salve-a em um arquivo separado chamado 'num_caracs.c'. Salve o protótipo em um arquivo chamado 'num_caracs.h'. Compile 'num_caracs.c' para gerar o objeto 'num_caracs.o'.
```
num_caracs.c
```
```c
#include<stdio.h>
#include<string.h>
#include"num_caracs.h"

//Esta função também contabiliza os caracteres de espaço.
int Num_Caracs(char *string)
{
	int num_caracteres;
	num_caracteres = strlen(string);
	return num_caracteres;
}

```
```
num_caracs.h
```
```c
int Num_Caracs(char *string);

```
```
comando para gerar arquivo objeto num_caracs.o:
```
```bash
gcc -c num_caracs.c

```

9. Re-utilize o objeto criado na questão 8 para criar um código que imprime cada argumento de entrada e a quantidade de caracteres de cada um desses argumentos. Por exemplo, considerando que o código criado recebeu o nome de 'ola_num_caracs_1':

```bash
$ ./ola_num_caracs_1 Eu Mesmo
$ Argumento: ./ola_num_caracs_1 / Numero de caracteres: 18
$ Argumento: Eu / Numero de caracteres: 2
$ Argumento: Mesmo / Numero de caracteres: 5
```
```
código ola_num_caracs_1.c
```
```c
#include<stdio.h>
#include"num_caracs.h"

int main( int argc, char *argv[] )
{
        int i;
        for (i=1; i < argc; i++){
                printf("Argumento: %s / Número de caracteres: %d \n", argv[i], Num_Caracs(argv[i]));
        }
        printf("\n");
        return 0;
}

```
```
compilando e eecutando programa utilizando o num_caracs.o
```
```bash
$ gcc -o ola_num_caracs_1 num_caracs.o ola_num_caracs_1.c
$ ./ola_num_caracs_1 Eu mesmo

Argumento: ./ola_num_caracs_1 / Número de caracteres: 18
Argumento: Eu / Número de caracteres: 2
Argumento: mesmo / Número de caracteres: 5

```
10. Crie um Makefile para a questão anterior.

Makefile:
```
num_caracs: ola_num_caracs_1.o num_caracs.o
	gcc $(CFLAGS) -o num_caracs ola_num_caracs_1.o num_caracs.o
ola_num_caracs_1.o: ola_num_caracs_1.c num_caracs.h
	gcc $(CFLAGS) -c ola_num_caracs_1.c
num_caracs.o: num_caracs.c num_caracs.h
	gcc $(CFLAGS) -c num_caracs.c
clean:
	rm -f *.o num_caracs

```
Comandos para rodar make file:
```bash
$ make
$ ./num_caracs Eu mesmo

Argumento: ./num_caracs / Número de caracteres: 12
Argumento: Eu / Número de caracteres: 2
Argumento: mesmo / Número de caracteres: 5
```

11. Re-utilize o objeto criado na questão 8 para criar um código que imprime o total de caracteres nos argumentos de entrada. Por exemplo, considerando que o código criado recebeu o nome de 'ola_num_caracs_2':

```bash
$ ./ola_num_caracs_2 Eu Mesmo
$ Total de caracteres de entrada: 25
```
Código ola_num_caracs_2
```c
#include<stdio.h>
#include"num_caracs.h"

int main( int argc, char *argv[] )
{
        int i;
        int num_total=0;
        for (i=0; i < argc; i++){
                num_total = num_total + Num_Caracs(argv[i]);
        }
        printf("Total de caracteres de entrada: %d \n", num_total);

        return 0;
}
```
compilando e eecutando programa utilizando o num_caracs.o
```bash
$ gcc -o ola_num_caracs_2 num_caracs.o ola_num_caracs_2.c
$ ./ola_num_caracs_2 Eu mesmo

Saída:
Total de caracteres de entrada: 25
```

12. Crie um Makefile para a questão anterior.

Makefile:
```
num_caracs: ola_num_caracs_2.o num_caracs.o
	gcc $(CFLAGS) -o num_caracs ola_num_caracs_2.o num_caracs.o
ola_num_caracs_2.o: ola_num_caracs_2.c num_caracs.h
	gcc $(CFLAGS) -c ola_num_caracs_2.c
num_caracs.o: num_caracs.c num_caracs.h
	gcc $(CFLAGS) -c num_caracs.c
clean:
	rm -f *.o num_caracs
```
Comandos para rodar make file e executar prorama criado:
```bash
$ make
$ ./num_caracs Eu mesmo

Saída:
Total de caracteres de entrada: 19
```
