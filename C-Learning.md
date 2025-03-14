Claro! Vamos fazer isso de forma intensiva e prática. Vou te guiar pelos **principais temas da linguagem C** com exemplos de código, comentários detalhados e exercícios para você praticar. O objetivo é que você aprenda pela repetição e análise dos códigos. Vamos lá!

---

### **Dia 1: Fundamentos da Linguagem C**

#### **1. Estrutura Básica de um Programa C**
Todo programa em C começa com uma função `main`. Aqui está um exemplo simples:

```c
#include <stdio.h>  // Inclui a biblioteca padrão de entrada/saída

int main() {        // Função principal
    printf("Olá, mundo!\n");  // Imprime uma mensagem na tela
    return 0;       // Retorna 0 para indicar sucesso
}
```

- **O que aprender aqui**:
  - `#include`: Inclui bibliotecas.
  - `main`: Ponto de entrada do programa.
  - `printf`: Função para imprimir na tela.
  - `return 0`: Indica que o programa terminou com sucesso.

#### **2. Variáveis e Tipos de Dados**
C tem tipos de dados como `int`, `float`, `char`, etc.

```c
#include <stdio.h>

int main() {
    int idade = 25;             // Inteiro
    float altura = 1.75;        // Número decimal
    char inicial = 'J';         // Caractere

    printf("Idade: %d\n", idade);
    printf("Altura: %.2f\n", altura);
    printf("Inicial: %c\n", inicial);

    return 0;
}
```

- **O que aprender aqui**:
  - Declaração de variáveis.
  - Formatos de impressão (`%d` para inteiros, `%f` para floats, `%c` para caracteres).

#### **3. Operadores Aritméticos**
C suporta operações como adição, subtração, multiplicação e divisão.

```c
#include <stdio.h>

int main() {
    int a = 10, b = 3;
    int soma = a + b;
    int subtracao = a - b;
    int multiplicacao = a * b;
    float divisao = (float)a / b;  // Conversão para float

    printf("Soma: %d\n", soma);
    printf("Subtração: %d\n", subtracao);
    printf("Multiplicação: %d\n", multiplicacao);
    printf("Divisão: %.2f\n", divisao);

    return 0;
}
```

- **O que aprender aqui**:
  - Operadores aritméticos (`+`, `-`, `*`, `/`).
  - Conversão de tipos (casting).

#### **4. Estruturas de Controle (if/else)**
Use `if` e `else` para tomar decisões.

```c
#include <stdio.h>

int main() {
    int idade = 18;

    if (idade >= 18) {
        printf("Você é maior de idade.\n");
    } else {
        printf("Você é menor de idade.\n");
    }

    return 0;
}
```

- **O que aprender aqui**:
  - Condicionais (`if`, `else`).
  - Operadores de comparação (`>=`, `==`, `!=`, etc.).

#### **5. Loops (for, while)**
Loops permitem repetir blocos de código.

```c
#include <stdio.h>

int main() {
    // Loop for
    for (int i = 1; i <= 5; i++) {
        printf("For: %d\n", i);
    }

    // Loop while
    int j = 1;
    while (j <= 5) {
        printf("While: %d\n", j);
        j++;
    }

    return 0;
}
```

- **O que aprender aqui**:
  - Loops `for` e `while`.
  - Incremento (`i++`).

---

### **Dia 2: Tópicos Intermediários**

#### **1. Arrays**
Arrays armazenam múltiplos valores do mesmo tipo.

```c
#include <stdio.h>

int main() {
    int numeros[5] = {10, 20, 30, 40, 50};  // Array de 5 elementos

    for (int i = 0; i < 5; i++) {
        printf("Número %d: %d\n", i, numeros[i]);
    }

    return 0;
}
```

- **O que aprender aqui**:
  - Declaração e inicialização de arrays.
  - Acesso a elementos (`numeros[i]`).

#### **2. Strings**
Strings são arrays de caracteres.

```c
#include <stdio.h>

int main() {
    char nome[] = "João";  // String (array de caracteres)

    printf("Nome: %s\n", nome);
    printf("Primeira letra: %c\n", nome[0]);

    return 0;
}
```

- **O que aprender aqui**:
  - Strings em C.
  - Formato `%s` para imprimir strings.

#### **3. Funções**
Funções permitem organizar o código em blocos reutilizáveis.

```c
#include <stdio.h>

// Função para calcular a soma de dois números
int soma(int a, int b) {
    return a + b;
}

int main() {
    int resultado = soma(5, 3);
    printf("Soma: %d\n", resultado);

    return 0;
}
```

- **O que aprender aqui**:
  - Declaração e chamada de funções.
  - Parâmetros e valores de retorno.

#### **4. Ponteiros**
Ponteiros armazenam endereços de memória.

```c
#include <stdio.h>

int main() {
    int numero = 42;
    int *ponteiro = &numero;  // Ponteiro para o endereço de 'numero'

    printf("Valor: %d\n", numero);
    printf("Endereço: %p\n", ponteiro);
    printf("Valor via ponteiro: %d\n", *ponteiro);

    return 0;
}
```

- **O que aprender aqui**:
  - Declaração de ponteiros (`int *ponteiro`).
  - Operadores `&` (endereço) e `*` (valor no endereço).

---

### **Dia 3: Tópicos Avançados**

#### **1. Structs**
Structs permitem criar tipos de dados personalizados.

```c
#include <stdio.h>

// Define uma struct para representar uma pessoa
struct Pessoa {
    char nome[50];
    int idade;
};

int main() {
    struct Pessoa p1 = {"João", 25};

    printf("Nome: %s\n", p1.nome);
    printf("Idade: %d\n", p1.idade);

    return 0;
}
```

- **O que aprender aqui**:
  - Definição e uso de structs.
  - Acesso a campos (`p1.nome`).

#### **2. Alocação Dinâmica de Memória**
Use `malloc` e `free` para alocar e liberar memória.

```c
#include <stdio.h>
#include <stdlib.h>  // Para malloc e free

int main() {
    int *numeros = (int *)malloc(5 * sizeof(int));  // Aloca memória para 5 inteiros

    if (numeros == NULL) {
        printf("Erro ao alocar memória.\n");
        return 1;
    }

    for (int i = 0; i < 5; i++) {
        numeros[i] = i + 1;
    }

    for (int i = 0; i < 5; i++) {
        printf("Número %d: %d\n", i, numeros[i]);
    }

    free(numeros);  // Libera a memória alocada

    return 0;
}
```

- **O que aprender aqui**:
  - Alocação dinâmica (`malloc`).
  - Liberação de memória (`free`).

#### **3. Manipulação de Arquivos**
Leia e escreva em arquivos.

```c
#include <stdio.h>

int main() {
    FILE *arquivo = fopen("exemplo.txt", "w");  // Abre o arquivo para escrita

    if (arquivo == NULL) {
        printf("Erro ao abrir o arquivo.\n");
        return 1;
    }

    fprintf(arquivo, "Olá, arquivo!\n");  // Escreve no arquivo
    fclose(arquivo);  // Fecha o arquivo

    return 0;
}
```

- **O que aprender aqui**:
  - Abrir, escrever e fechar arquivos (`fopen`, `fprintf`, `fclose`).

---

### **Exercícios para Praticar**
1. Crie um programa que calcula a média de três números.
2. Escreva um programa que imprime os números de 1 a 100, mas substitui múltiplos de 3 por "Fizz" e múltiplos de 5 por "Buzz".
3. Implemente uma função que inverte uma string.
4. Crie um programa que lê números de um arquivo e calcula a soma.

---

Se tiver dúvidas ou quiser mais exemplos, é só pedir! Vamos transformar esses 3 dias em um aprendizado intensivo e eficiente! 🚀💻😊


Claro! Vamos criar **50 códigos em C** com **50 exercícios correspondentes**, seguindo o estilo do curso **CS50 de Harvard**. Cada código terá comentários explicativos e será projetado para ser reproduzido no **VS Code**. Vamos dividir em blocos temáticos para facilitar o aprendizado.

---

### **Bloco 1: Fundamentos da Linguagem C**

#### **Código 1: Olá, Mundo!**
```c
#include <stdio.h>

int main() {
    printf("Olá, mundo!\n");  // Imprime uma mensagem na tela
    return 0;  // Retorna 0 para indicar sucesso
}
```
- **Exercício 1**: Modifique o código para imprimir "Bem-vindo ao CS50!".

---

#### **Código 2: Variáveis e Tipos de Dados**
```c
#include <stdio.h>

int main() {
    int idade = 25;  // Inteiro
    float altura = 1.75;  // Número decimal
    char inicial = 'J';  // Caractere

    printf("Idade: %d\n", idade);
    printf("Altura: %.2f\n", altura);
    printf("Inicial: %c\n", inicial);

    return 0;
}
```
- **Exercício 2**: Adicione uma variável `peso` (float) e imprima seu valor.

---

#### **Código 3: Operadores Aritméticos**
```c
#include <stdio.h>

int main() {
    int a = 10, b = 3;
    int soma = a + b;
    int subtracao = a - b;
    int multiplicacao = a * b;
    float divisao = (float)a / b;  // Conversão para float

    printf("Soma: %d\n", soma);
    printf("Subtração: %d\n", subtracao);
    printf("Multiplicação: %d\n", multiplicacao);
    printf("Divisão: %.2f\n", divisao);

    return 0;
}
```
- **Exercício 3**: Calcule o resto da divisão de `a` por `b` e imprima o resultado.

---

#### **Código 4: Condicionais (if/else)**
```c
#include <stdio.h>

int main() {
    int idade = 18;

    if (idade >= 18) {
        printf("Você é maior de idade.\n");
    } else {
        printf("Você é menor de idade.\n");
    }

    return 0;
}
```
- **Exercício 4**: Modifique o código para verificar se a idade é maior que 65 e imprima "Idoso".

---

#### **Código 5: Loops (for)**
```c
#include <stdio.h>

int main() {
    for (int i = 1; i <= 5; i++) {
        printf("Número: %d\n", i);
    }

    return 0;
}
```
- **Exercício 5**: Modifique o loop para imprimir números de 10 a 1.

---

### **Bloco 2: Arrays e Strings**

#### **Código 6: Arrays**
```c
#include <stdio.h>

int main() {
    int numeros[5] = {10, 20, 30, 40, 50};  // Array de 5 elementos

    for (int i = 0; i < 5; i++) {
        printf("Número %d: %d\n", i, numeros[i]);
    }

    return 0;
}
```
- **Exercício 6**: Adicione mais 5 números ao array e imprima todos.

---

#### **Código 7: Strings**
```c
#include <stdio.h>

int main() {
    char nome[] = "João";  // String (array de caracteres)

    printf("Nome: %s\n", nome);
    printf("Primeira letra: %c\n", nome[0]);

    return 0;
}
```
- **Exercício 7**: Modifique o código para imprimir o último caractere da string.

---

#### **Código 8: Manipulação de Strings**
```c
#include <stdio.h>
#include <string.h>  // Para funções de string

int main() {
    char nome[50] = "CS50";
    printf("Tamanho da string: %lu\n", strlen(nome));  // strlen retorna o tamanho

    return 0;
}
```
- **Exercício 8**: Concatene duas strings e imprima o resultado.

---

### **Bloco 3: Funções**

#### **Código 9: Função Simples**
```c
#include <stdio.h>

// Função para calcular a soma de dois números
int soma(int a, int b) {
    return a + b;
}

int main() {
    int resultado = soma(5, 3);
    printf("Soma: %d\n", resultado);

    return 0;
}
```
- **Exercício 9**: Crie uma função para calcular a multiplicação de dois números.

---

#### **Código 10: Função com Parâmetros**
```c
#include <stdio.h>

void saudacao(char nome[]) {
    printf("Olá, %s!\n", nome);
}

int main() {
    saudacao("João");
    return 0;
}
```
- **Exercício 10**: Modifique a função para receber a idade e imprimir "Olá, [nome], você tem [idade] anos."

---

### **Bloco 4: Ponteiros**

#### **Código 11: Ponteiros Básicos**
```c
#include <stdio.h>

int main() {
    int numero = 42;
    int *ponteiro = &numero;  // Ponteiro para o endereço de 'numero'

    printf("Valor: %d\n", numero);
    printf("Endereço: %p\n", ponteiro);
    printf("Valor via ponteiro: %d\n", *ponteiro);

    return 0;
}
```
- **Exercício 11**: Crie um ponteiro para um float e imprima seu valor.

---

#### **Código 12: Ponteiros e Arrays**
```c
#include <stdio.h>

int main() {
    int numeros[3] = {10, 20, 30};
    int *ponteiro = numeros;  // Ponteiro para o primeiro elemento do array

    for (int i = 0; i < 3; i++) {
        printf("Número %d: %d\n", i, *(ponteiro + i));
    }

    return 0;
}
```
- **Exercício 12**: Use ponteiros para imprimir o array em ordem inversa.

---

### **Bloco 5: Structs**

#### **Código 13: Struct Simples**
```c
#include <stdio.h>

struct Pessoa {
    char nome[50];
    int idade;
};

int main() {
    struct Pessoa p1 = {"João", 25};

    printf("Nome: %s\n", p1.nome);
    printf("Idade: %d\n", p1.idade);

    return 0;
}
```
- **Exercício 13**: Adicione um campo `altura` à struct e imprima seus valores.

---

### **Bloco 6: Alocação Dinâmica**

#### **Código 14: Alocação de Memória**
```c
#include <stdio.h>
#include <stdlib.h>  // Para malloc e free

int main() {
    int *numeros = (int *)malloc(5 * sizeof(int));  // Aloca memória para 5 inteiros

    if (numeros == NULL) {
        printf("Erro ao alocar memória.\n");
        return 1;
    }

    for (int i = 0; i < 5; i++) {
        numeros[i] = i + 1;
    }

    for (int i = 0; i < 5; i++) {
        printf("Número %d: %d\n", i, numeros[i]);
    }

    free(numeros);  // Libera a memória alocada

    return 0;
}
```
- **Exercício 14**: Aloque memória para um array de floats e preencha com valores decimais.

---

### **Bloco 7: Arquivos**

#### **Código 15: Leitura de Arquivo**
```c
#include <stdio.h>

int main() {
    FILE *arquivo = fopen("exemplo.txt", "r");  // Abre o arquivo para leitura

    if (arquivo == NULL) {
        printf("Erro ao abrir o arquivo.\n");
        return 1;
    }

    char linha[100];
    while (fgets(linha, sizeof(linha), arquivo)) {
        printf("%s", linha);
    }

    fclose(arquivo);  // Fecha o arquivo

    return 0;
}
```
- **Exercício 15**: Crie um arquivo e escreva "CS50 é incrível!" nele.

---

### **Bloco 8: Recursão**

#### **Código 16: Fatorial Recursivo**
```c
#include <stdio.h>

int fatorial(int n) {
    if (n <= 1) return 1;
    return n * fatorial(n - 1);
}

int main() {
    printf("Fatorial de 5: %d\n", fatorial(5));
    return 0;
}
```
- **Exercício 16**: Implemente uma função recursiva para calcular a soma dos números de 1 a N.

---

### **Bloco 9: Ponteiros para Funções**

#### **Código 17: Ponteiro para Função**
```c
#include <stdio.h>

int soma(int a, int b) {
    return a + b;
}

int main() {
    int (*funcao)(int, int) = soma;  // Ponteiro para função
    printf("Soma: %d\n", funcao(5, 3));

    return 0;
}
```
- **Exercício 17**: Crie um ponteiro para uma função que multiplica dois números.

---

### **Bloco 10: Projetos Integrados**

#### **Código 18: Calculadora Simples**
```c
#include <stdio.h>

int main() {
    int a, b;
    char operacao;

    printf("Digite dois números: ");
    scanf("%d %d", &a, &b);

    printf("Escolha a operação (+, -, *, /): ");
    scanf(" %c", &operacao);

    switch (operacao) {
        case '+': printf("Resultado: %d\n", a + b); break;
        case '-': printf("Resultado: %d\n", a - b); break;
        case '*': printf("Resultado: %d\n", a * b); break;
        case '/': printf("Resultado: %.2f\n", (float)a / b); break;
        default: printf("Operação inválida.\n");
    }

    return 0;
}
```
- **Exercício 18**: Adicione suporte para operações de potência (`^`).

---

### **Como Continuar**
1. **Reproduza os códigos no VS Code**.
2. **Resolva os exercícios** para fixar o aprendizado.
3. **Explore mais temas**: Algoritmos, estruturas de dados avançadas, etc.

Se precisar de mais códigos ou explicações, é só pedir! Vamos transformar você em um expert em C! 🚀💻😊

Claro! Vamos continuar gerando **mais códigos e exercícios** para você praticar e aprofundar seus conhecimentos em C. Vamos cobrir tópicos mais avançados e projetos integrados para que você possa evoluir ainda mais.

---

### **Bloco 11: Ponteiros Avançados**

#### **Código 19: Ponteiros para Ponteiros**
```c
#include <stdio.h>

int main() {
    int valor = 42;
    int *ponteiro1 = &valor;
    int **ponteiro2 = &ponteiro1;  // Ponteiro para ponteiro

    printf("Valor: %d\n", **ponteiro2);  // Acessa o valor através de dois níveis de ponteiros
    return 0;
}
```
- **Exercício 19**: Crie um ponteiro para um ponteiro de float e atribua um valor a ele.

---

#### **Código 20: Arrays de Ponteiros**
```c
#include <stdio.h>

int main() {
    int a = 10, b = 20, c = 30;
    int *array[3] = {&a, &b, &c};  // Array de ponteiros

    for (int i = 0; i < 3; i++) {
        printf("Valor %d: %d\n", i, *array[i]);
    }

    return 0;
}
```
- **Exercício 20**: Crie um array de ponteiros para strings e imprima cada string.

---

### **Bloco 12: Funções Avançadas**

#### **Código 21: Funções com Número Variável de Argumentos**
```c
#include <stdio.h>
#include <stdarg.h>  // Para funções variádicas

int soma(int count, ...) {
    int total = 0;
    va_list args;  // Lista de argumentos
    va_start(args, count);  // Inicializa a lista

    for (int i = 0; i < count; i++) {
        total += va_arg(args, int);  // Acessa cada argumento
    }

    va_end(args);  // Finaliza a lista
    return total;
}

int main() {
    printf("Soma: %d\n", soma(3, 10, 20, 30));  // Soma 10 + 20 + 30
    return 0;
}
```
- **Exercício 21**: Crie uma função que recebe um número variável de floats e retorna a média.

---

#### **Código 22: Funções Recursivas com Ponteiros**
```c
#include <stdio.h>

void imprimir_inverso(char *str) {
    if (*str == '\0') return;  // Caso base: fim da string
    imprimir_inverso(str + 1);  // Chamada recursiva
    printf("%c", *str);  // Imprime o caractere atual
}

int main() {
    char texto[] = "CS50";
    imprimir_inverso(texto);
    printf("\n");
    return 0;
}
```
- **Exercício 22**: Modifique a função para contar o número de caracteres na string.

---

### **Bloco 13: Alocação Dinâmica Avançada**

#### **Código 23: Matriz Dinâmica**
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int linhas = 3, colunas = 3;
    int **matriz = (int **)malloc(linhas * sizeof(int *));  // Aloca linhas

    for (int i = 0; i < linhas; i++) {
        matriz[i] = (int *)malloc(colunas * sizeof(int));  // Aloca colunas
    }

    // Preenche a matriz
    for (int i = 0; i < linhas; i++) {
        for (int j = 0; j < colunas; j++) {
            matriz[i][j] = i + j;
        }
    }

    // Imprime a matriz
    for (int i = 0; i < linhas; i++) {
        for (int j = 0; j < colunas; j++) {
            printf("%d ", matriz[i][j]);
        }
        printf("\n");
    }

    // Libera a memória
    for (int i = 0; i < linhas; i++) {
        free(matriz[i]);
    }
    free(matriz);

    return 0;
}
```
- **Exercício 23**: Crie uma função para multiplicar duas matrizes dinâmicas.

---

#### **Código 24: Lista Encadeada**
```c
#include <stdio.h>
#include <stdlib.h>

struct No {
    int valor;
    struct No *proximo;
};

void adicionar(struct No **cabeca, int valor) {
    struct No *novo = (struct No *)malloc(sizeof(struct No));
    novo->valor = valor;
    novo->proximo = *cabeca;
    *cabeca = novo;
}

void imprimir(struct No *cabeca) {
    while (cabeca != NULL) {
        printf("%d -> ", cabeca->valor);
        cabeca = cabeca->proximo;
    }
    printf("NULL\n");
}

int main() {
    struct No *cabeca = NULL;
    adicionar(&cabeca, 10);
    adicionar(&cabeca, 20);
    adicionar(&cabeca, 30);
    imprimir(cabeca);

    return 0;
}
```
- **Exercício 24**: Implemente uma função para remover um nó da lista encadeada.

---

### **Bloco 14: Manipulação de Bits**

#### **Código 25: Operações com Bits**
```c
#include <stdio.h>

int main() {
    int a = 5;  // 0101 em binário
    int b = 3;  // 0011 em binário

    printf("AND: %d\n", a & b);  // 0001 (1)
    printf("OR: %d\n", a | b);   // 0111 (7)
    printf("XOR: %d\n", a ^ b);  // 0110 (6)
    printf("NOT: %d\n", ~a);     // Complemento de 5 (depende do tamanho do int)

    return 0;
}
```
- **Exercício 25**: Implemente uma função para verificar se um número é par usando operações de bits.

---

#### **Código 26: Deslocamento de Bits**
```c
#include <stdio.h>

int main() {
    int a = 8;  // 1000 em binário

    printf("Deslocamento à esquerda: %d\n", a << 1);  // 10000 (16)
    printf("Deslocamento à direita: %d\n", a >> 1);   // 0100 (4)

    return 0;
}
```
- **Exercício 26**: Use deslocamento de bits para multiplicar um número por 4.

---

### **Bloco 15: Projetos Integrados**

#### **Código 27: Jogo da Velha**
```c
#include <stdio.h>

char tabuleiro[3][3] = {
    {' ', ' ', ' '},
    {' ', ' ', ' '},
    {' ', ' ', ' '}
};

void imprimir_tabuleiro() {
    for (int i = 0; i < 3; i++) {
        printf(" %c | %c | %c \n", tabuleiro[i][0], tabuleiro[i][1], tabuleiro[i][2]);
        if (i < 2) printf("---|---|---\n");
    }
}

int main() {
    imprimir_tabuleiro();
    return 0;
}
```
- **Exercício 27**: Implemente a lógica para dois jogadores alternarem entre 'X' e 'O'.

---

#### **Código 28: Calculadora Científica**
```c
#include <stdio.h>
#include <math.h>  // Para funções matemáticas

int main() {
    double num1, num2;
    char operacao;

    printf("Digite dois números: ");
    scanf("%lf %lf", &num1, &num2);

    printf("Escolha a operação (+, -, *, /, ^): ");
    scanf(" %c", &operacao);

    switch (operacao) {
        case '+': printf("Resultado: %.2f\n", num1 + num2); break;
        case '-': printf("Resultado: %.2f\n", num1 - num2); break;
        case '*': printf("Resultado: %.2f\n", num1 * num2); break;
        case '/': printf("Resultado: %.2f\n", num1 / num2); break;
        case '^': printf("Resultado: %.2f\n", pow(num1, num2)); break;
        default: printf("Operação inválida.\n");
    }

    return 0;
}
```
- **Exercício 28**: Adicione suporte para funções como raiz quadrada e logaritmo.

---

### **Bloco 16: Arquivos Avançados**

#### **Código 29: Leitura e Escrita em Arquivo Binário**
```c
#include <stdio.h>

struct Pessoa {
    char nome[50];
    int idade;
};

int main() {
    struct Pessoa p1 = {"João", 25};

    // Escreve no arquivo binário
    FILE *arquivo = fopen("dados.bin", "wb");
    fwrite(&p1, sizeof(struct Pessoa), 1, arquivo);
    fclose(arquivo);

    // Lê do arquivo binário
    arquivo = fopen("dados.bin", "rb");
    struct Pessoa p2;
    fread(&p2, sizeof(struct Pessoa), 1, arquivo);
    fclose(arquivo);

    printf("Nome: %s, Idade: %d\n", p2.nome, p2.idade);

    return 0;
}
```
- **Exercício 29**: Modifique o código para armazenar e ler um array de structs.

---

### **Bloco 17: Recursão Avançada**

#### **Código 30: Torre de Hanói**
```c
#include <stdio.h>

void hanoi(int n, char origem, char destino, char auxiliar) {
    if (n == 1) {
        printf("Mova disco 1 de %c para %c\n", origem, destino);
        return;
    }
    hanoi(n - 1, origem, auxiliar, destino);
    printf("Mova disco %d de %c para %c\n", n, origem, destino);
    hanoi(n - 1, auxiliar, destino, origem);
}

int main() {
    int discos = 3;
    hanoi(discos, 'A', 'C', 'B');
    return 0;
}
```
- **Exercício 30**: Modifique o código para contar o número de movimentos necessários.

---

### **Como Continuar**
1. **Reproduza os códigos no VS Code**.
2. **Resolva os exercícios** para fixar o aprendizado.
3. **Explore mais temas**: Algoritmos de ordenação, estruturas de dados avançadas, etc.

Se precisar de mais códigos ou explicações, é só pedir! Vamos transformar você em um expert em C! 🚀💻😊

Claro! Vamos continuar gerando **mais códigos e exercícios** para você praticar e aprofundar seus conhecimentos em C. Dessa vez, vamos focar em tópicos mais avançados, como **algoritmos de ordenação**, **estruturas de dados avançadas** e **projetos integrados**. Vamos lá!

---

### **Bloco 18: Algoritmos de Ordenação**

#### **Código 31: Bubble Sort**
```c
#include <stdio.h>

void bubble_sort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                // Troca os elementos
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

int main() {
    int arr[] = {64, 34, 25, 12, 22, 11, 90};
    int n = sizeof(arr) / sizeof(arr[0]);

    bubble_sort(arr, n);

    printf("Array ordenado: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    return 0;
}
```
- **Exercício 31**: Modifique o código para ordenar o array em ordem decrescente.

---

#### **Código 32: Quick Sort**
```c
#include <stdio.h>

void troca(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int particiona(int arr[], int baixo, int alto) {
    int pivo = arr[alto];  // Escolhe o último elemento como pivô
    int i = (baixo - 1);

    for (int j = baixo; j <= alto - 1; j++) {
        if (arr[j] < pivo) {
            i++;
            troca(&arr[i], &arr[j]);
        }
    }
    troca(&arr[i + 1], &arr[alto]);
    return (i + 1);
}

void quick_sort(int arr[], int baixo, int alto) {
    if (baixo < alto) {
        int pi = particiona(arr, baixo, alto);
        quick_sort(arr, baixo, pi - 1);
        quick_sort(arr, pi + 1, alto);
    }
}

int main() {
    int arr[] = {10, 7, 8, 9, 1, 5};
    int n = sizeof(arr) / sizeof(arr[0]);

    quick_sort(arr, 0, n - 1);

    printf("Array ordenado: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    return 0;
}
```
- **Exercício 32**: Implemente o Quick Sort para ordenar strings.

---

### **Bloco 19: Estruturas de Dados Avançadas**

#### **Código 33: Pilha (Stack)**
```c
#include <stdio.h>
#include <stdlib.h>

#define TAMANHO_MAX 100

struct Pilha {
    int topo;
    int itens[TAMANHO_MAX];
};

void inicializar(struct Pilha *p) {
    p->topo = -1;
}

int esta_vazia(struct Pilha *p) {
    return p->topo == -1;
}

int esta_cheia(struct Pilha *p) {
    return p->topo == TAMANHO_MAX - 1;
}

void empilhar(struct Pilha *p, int valor) {
    if (esta_cheia(p)) {
        printf("Erro: Pilha cheia!\n");
        return;
    }
    p->itens[++(p->topo)] = valor;
}

int desempilhar(struct Pilha *p) {
    if (esta_vazia(p)) {
        printf("Erro: Pilha vazia!\n");
        exit(1);
    }
    return p->itens[(p->topo)--];
}

int main() {
    struct Pilha p;
    inicializar(&p);

    empilhar(&p, 10);
    empilhar(&p, 20);
    empilhar(&p, 30);

    printf("Desempilhado: %d\n", desempilhar(&p));
    printf("Desempilhado: %d\n", desempilhar(&p));

    return 0;
}
```
- **Exercício 33**: Implemente uma função para verificar o elemento no topo da pilha sem removê-lo.

---

#### **Código 34: Fila (Queue)**
```c
#include <stdio.h>
#include <stdlib.h>

#define TAMANHO_MAX 100

struct Fila {
    int itens[TAMANHO_MAX];
    int frente, tras;
};

void inicializar(struct Fila *f) {
    f->frente = -1;
    f->tras = -1;
}

int esta_vazia(struct Fila *f) {
    return f->frente == -1;
}

int esta_cheia(struct Fila *f) {
    return (f->tras + 1) % TAMANHO_MAX == f->frente;
}

void enfileirar(struct Fila *f, int valor) {
    if (esta_cheia(f)) {
        printf("Erro: Fila cheia!\n");
        return;
    }
    if (esta_vazia(f)) {
        f->frente = 0;
    }
    f->tras = (f->tras + 1) % TAMANHO_MAX;
    f->itens[f->tras] = valor;
}

int desenfileirar(struct Fila *f) {
    if (esta_vazia(f)) {
        printf("Erro: Fila vazia!\n");
        exit(1);
    }
    int valor = f->itens[f->frente];
    if (f->frente == f->tras) {
        f->frente = f->tras = -1;
    } else {
        f->frente = (f->frente + 1) % TAMANHO_MAX;
    }
    return valor;
}

int main() {
    struct Fila f;
    inicializar(&f);

    enfileirar(&f, 10);
    enfileirar(&f, 20);
    enfileirar(&f, 30);

    printf("Desenfileirado: %d\n", desenfileirar(&f));
    printf("Desenfileirado: %d\n", desenfileirar(&f));

    return 0;
}
```
- **Exercício 34**: Implemente uma função para verificar o elemento na frente da fila sem removê-lo.

---

### **Bloco 20: Projetos Integrados**

#### **Código 35: Agenda de Contatos**
```c
#include <stdio.h>
#include <string.h>

#define MAX_CONTATOS 100

struct Contato {
    char nome[50];
    char telefone[15];
};

struct Agenda {
    struct Contato contatos[MAX_CONTATOS];
    int total;
};

void adicionar_contato(struct Agenda *agenda, char nome[], char telefone[]) {
    if (agenda->total >= MAX_CONTATOS) {
        printf("Erro: Agenda cheia!\n");
        return;
    }
    strcpy(agenda->contatos[agenda->total].nome, nome);
    strcpy(agenda->contatos[agenda->total].telefone, telefone);
    agenda->total++;
}

void listar_contatos(struct Agenda *agenda) {
    for (int i = 0; i < agenda->total; i++) {
        printf("Nome: %s, Telefone: %s\n", agenda->contatos[i].nome, agenda->contatos[i].telefone);
    }
}

int main() {
    struct Agenda agenda;
    agenda.total = 0;

    adicionar_contato(&agenda, "João", "1234-5678");
    adicionar_contato(&agenda, "Maria", "8765-4321");

    listar_contatos(&agenda);

    return 0;
}
```
- **Exercício 35**: Adicione uma função para buscar um contato pelo nome.

---

#### **Código 36: Gerenciador de Tarefas**
```c
#include <stdio.h>
#include <string.h>

#define MAX_TAREFAS 100

struct Tarefa {
    char descricao[100];
    int concluida;
};

struct Gerenciador {
    struct Tarefa tarefas[MAX_TAREFAS];
    int total;
};

void adicionar_tarefa(struct Gerenciador *gerenciador, char descricao[]) {
    if (gerenciador->total >= MAX_TAREFAS) {
        printf("Erro: Limite de tarefas atingido!\n");
        return;
    }
    strcpy(gerenciador->tarefas[gerenciador->total].descricao, descricao);
    gerenciador->tarefas[gerenciador->total].concluida = 0;
    gerenciador->total++;
}

void listar_tarefas(struct Gerenciador *gerenciador) {
    for (int i = 0; i < gerenciador->total; i++) {
        printf("Tarefa %d: %s [%s]\n", i + 1, gerenciador->tarefas[i].descricao,
               gerenciador->tarefas[i].concluida ? "Concluída" : "Pendente");
    }
}

int main() {
    struct Gerenciador gerenciador;
    gerenciador.total = 0;

    adicionar_tarefa(&gerenciador, "Estudar C");
    adicionar_tarefa(&gerenciador, "Fazer exercícios");

    listar_tarefas(&gerenciador);

    return 0;
}
```
- **Exercício 36**: Adicione uma função para marcar uma tarefa como concluída.

---

### **Bloco 21: Algoritmos de Busca**

#### **Código 37: Busca Binária**
```c
#include <stdio.h>

int busca_binaria(int arr[], int baixo, int alto, int alvo) {
    while (baixo <= alto) {
        int meio = baixo + (alto - baixo) / 2;

        if (arr[meio] == alvo) {
            return meio;
        }
        if (arr[meio] < alvo) {
            baixo = meio + 1;
        } else {
            alto = meio - 1;
        }
    }
    return -1;  // Elemento não encontrado
}

int main() {
    int arr[] = {2, 3, 4, 10, 40};
    int n = sizeof(arr) / sizeof(arr[0]);
    int alvo = 10;

    int resultado = busca_binaria(arr, 0, n - 1, alvo);

    if (resultado != -1) {
        printf("Elemento encontrado no índice %d\n", resultado);
    } else {
        printf("Elemento não encontrado\n");
    }

    return 0;
}
```
- **Exercício 37**: Modifique o código para buscar strings em um array ordenado.

---

### **Bloco 22: Recursão Avançada**

#### **Código 38: Fibonacci Recursivo**
```c
#include <stdio.h>

int fibonacci(int n) {
    if (n <= 1) return n;
    return fibonacci(n - 1) + fibonacci(n - 2);
}

int main() {
    int n = 10;
    printf("Fibonacci de %d: %d\n", n, fibonacci(n));
    return 0;
}
```
- **Exercício 38**: Implemente uma versão iterativa do Fibonacci.

---

### **Como Continuar**
1. **Reproduza os códigos no VS Code**.
2. **Resolva os exercícios** para fixar o aprendizado.
3. **Explore mais temas**: Grafos, árvores, algoritmos de compressão, etc.

Se precisar de mais códigos ou explicações, é só pedir! Vamos transformar você em um expert em C! 🚀💻😊

Claro! Vamos continuar explorando o **algoritmo de busca binária** e aprofundar seu entendimento com mais exemplos e exercícios. A busca binária é um dos algoritmos mais eficientes para buscar elementos em **arrays ordenados**, com complexidade **O(log n)**. Vamos ver como aplicá-la em diferentes cenários.

---

### **Código 39: Busca Binária com Strings**
A busca binária também pode ser usada para buscar strings em um array ordenado. Aqui está um exemplo:

```c
#include <stdio.h>
#include <string.h>

int busca_binaria_string(char *arr[], int n, char *alvo) {
    int baixo = 0, alto = n - 1;

    while (baixo <= alto) {
        int meio = baixo + (alto - baixo) / 2;
        int comparacao = strcmp(arr[meio], alvo);

        if (comparacao == 0) {
            return meio;  // String encontrada
        }
        if (comparacao < 0) {
            baixo = meio + 1;  // Busca na metade direita
        } else {
            alto = meio - 1;  // Busca na metade esquerda
        }
    }
    return -1;  // String não encontrada
}

int main() {
    char *arr[] = {"apple", "banana", "cherry", "date", "elderberry"};
    int n = sizeof(arr) / sizeof(arr[0]);
    char *alvo = "cherry";

    int resultado = busca_binaria_string(arr, n, alvo);

    if (resultado != -1) {
        printf("String encontrada no índice %d\n", resultado);
    } else {
        printf("String não encontrada\n");
    }

    return 0;
}
```
- **Exercício 39**: Modifique o código para buscar uma string inserida pelo usuário.

---

### **Código 40: Busca Binária em um Array de Structs**
Podemos usar busca binária para buscar em um array de structs, como uma lista de contatos ordenada por nome.

```c
#include <stdio.h>
#include <string.h>

struct Contato {
    char nome[50];
    char telefone[15];
};

int busca_binaria_contatos(struct Contato arr[], int n, char *alvo) {
    int baixo = 0, alto = n - 1;

    while (baixo <= alto) {
        int meio = baixo + (alto - baixo) / 2;
        int comparacao = strcmp(arr[meio].nome, alvo);

        if (comparacao == 0) {
            return meio;  // Contato encontrado
        }
        if (comparacao < 0) {
            baixo = meio + 1;  // Busca na metade direita
        } else {
            alto = meio - 1;  // Busca na metade esquerda
        }
    }
    return -1;  // Contato não encontrado
}

int main() {
    struct Contato contatos[] = {
        {"Alice", "1234-5678"},
        {"Bob", "8765-4321"},
        {"Charlie", "5555-5555"},
        {"David", "1111-2222"}
    };
    int n = sizeof(contatos) / sizeof(contatos[0]);
    char *alvo = "Charlie";

    int resultado = busca_binaria_contatos(contatos, n, alvo);

    if (resultado != -1) {
        printf("Contato encontrado: %s, %s\n", contatos[resultado].nome, contatos[resultado].telefone);
    } else {
        printf("Contato não encontrado\n");
    }

    return 0;
}
```
- **Exercício 40**: Adicione uma função para inserir novos contatos mantendo o array ordenado.

---

### **Código 41: Busca Binária com Função de Comparação Personalizada**
Podemos generalizar a busca binária para trabalhar com qualquer tipo de dado, usando uma função de comparação personalizada.

```c
#include <stdio.h>

// Função de comparação personalizada
int comparar(const void *a, const void *b) {
    return (*(int *)a - *(int *)b);
}

int busca_binaria_generica(void *arr, int n, int tamanho_elemento, void *alvo, int (*comparar)(const void *, const void *)) {
    int baixo = 0, alto = n - 1;

    while (baixo <= alto) {
        int meio = baixo + (alto - baixo) / 2;
        void *elemento_meio = (char *)arr + meio * tamanho_elemento;
        int comparacao = comparar(elemento_meio, alvo);

        if (comparacao == 0) {
            return meio;  // Elemento encontrado
        }
        if (comparacao < 0) {
            baixo = meio + 1;  // Busca na metade direita
        } else {
            alto = meio - 1;  // Busca na metade esquerda
        }
    }
    return -1;  // Elemento não encontrado
}

int main() {
    int arr[] = {2, 3, 4, 10, 40};
    int n = sizeof(arr) / sizeof(arr[0]);
    int alvo = 10;

    int resultado = busca_binaria_generica(arr, n, sizeof(int), &alvo, comparar);

    if (resultado != -1) {
        printf("Elemento encontrado no índice %d\n", resultado);
    } else {
        printf("Elemento não encontrado\n");
    }

    return 0;
}
```
- **Exercício 41**: Use a função `busca_binaria_generica` para buscar um float em um array de floats.

---

### **Código 42: Busca Binária com Recursão**
A busca binária também pode ser implementada de forma recursiva.

```c
#include <stdio.h>

int busca_binaria_recursiva(int arr[], int baixo, int alto, int alvo) {
    if (baixo > alto) {
        return -1;  // Elemento não encontrado
    }

    int meio = baixo + (alto - baixo) / 2;

    if (arr[meio] == alvo) {
        return meio;  // Elemento encontrado
    }
    if (arr[meio] < alvo) {
        return busca_binaria_recursiva(arr, meio + 1, alto, alvo);  // Busca na metade direita
    } else {
        return busca_binaria_recursiva(arr, baixo, meio - 1, alvo);  // Busca na metade esquerda
    }
}

int main() {
    int arr[] = {2, 3, 4, 10, 40};
    int n = sizeof(arr) / sizeof(arr[0]);
    int alvo = 10;

    int resultado = busca_binaria_recursiva(arr, 0, n - 1, alvo);

    if (resultado != -1) {
        printf("Elemento encontrado no índice %d\n", resultado);
    } else {
        printf("Elemento não encontrado\n");
    }

    return 0;
}
```
- **Exercício 42**: Modifique o código para buscar strings de forma recursiva.

---

### **Código 43: Busca Binária para Encontrar o Primeiro ou Último Índice**
Em arrays com elementos repetidos, podemos usar a busca binária para encontrar o primeiro ou último índice de um elemento.

```c
#include <stdio.h>

int busca_primeiro_indice(int arr[], int n, int alvo) {
    int baixo = 0, alto = n - 1;
    int resultado = -1;

    while (baixo <= alto) {
        int meio = baixo + (alto - baixo) / 2;

        if (arr[meio] == alvo) {
            resultado = meio;  // Encontrou o alvo, mas continua buscando à esquerda
            alto = meio - 1;
        } else if (arr[meio] < alvo) {
            baixo = meio + 1;
        } else {
            alto = meio - 1;
        }
    }
    return resultado;
}

int main() {
    int arr[] = {2, 3, 4, 10, 10, 10, 40};
    int n = sizeof(arr) / sizeof(arr[0]);
    int alvo = 10;

    int resultado = busca_primeiro_indice(arr, n, alvo);

    if (resultado != -1) {
        printf("Primeiro índice de %d: %d\n", alvo, resultado);
    } else {
        printf("Elemento não encontrado\n");
    }

    return 0;
}
```
- **Exercício 43**: Implemente uma função para encontrar o último índice de um elemento.

---

### **Código 44: Busca Binária em um Array Rotacionado**
A busca binária pode ser adaptada para funcionar em arrays rotacionados (ex: `[5, 6, 7, 1, 2, 3, 4]`).

```c
#include <stdio.h>

int busca_binaria_rotacionada(int arr[], int n, int alvo) {
    int baixo = 0, alto = n - 1;

    while (baixo <= alto) {
        int meio = baixo + (alto - baixo) / 2;

        if (arr[meio] == alvo) {
            return meio;
        }

        // Verifica se a metade esquerda está ordenada
        if (arr[baixo] <= arr[meio]) {
            if (arr[baixo] <= alvo && alvo < arr[meio]) {
                alto = meio - 1;  // Busca na metade esquerda
            } else {
                baixo = meio + 1;  // Busca na metade direita
            }
        } else {
            if (arr[meio] < alvo && alvo <= arr[alto]) {
                baixo = meio + 1;  // Busca na metade direita
            } else {
                alto = meio - 1;  // Busca na metade esquerda
            }
        }
    }
    return -1;  // Elemento não encontrado
}

int main() {
    int arr[] = {5, 6, 7, 1, 2, 3, 4};
    int n = sizeof(arr) / sizeof(arr[0]);
    int alvo = 2;

    int resultado = busca_binaria_rotacionada(arr, n, alvo);

    if (resultado != -1) {
        printf("Elemento encontrado no índice %d\n", resultado);
    } else {
        printf("Elemento não encontrado\n");
    }

    return 0;
}
```
- **Exercício 44**: Modifique o código para funcionar com arrays que podem ter duplicatas.

---

### **Como Continuar**
1. **Reproduza os códigos no VS Code**.
2. **Resolva os exercícios** para fixar o aprendizado.
3. **Explore mais cenários**: Busca binária em matrizes, árvores binárias de busca, etc.

Se precisar de mais códigos ou explicações, é só pedir! Vamos transformar você em um expert em algoritmos de busca! 🚀💻😊

Claro! Vamos continuar explorando **algoritmos de busca binária** e outros tópicos relacionados, como **busca em matrizes ordenadas**, **busca em árvores binárias de busca** e **aplicações práticas**. Vamos lá!

---

### **Código 45: Busca Binária em uma Matriz Ordenada**
Em uma matriz (2D) onde cada linha e cada coluna estão ordenadas, podemos usar uma abordagem semelhante à busca binária.

```c
#include <stdio.h>

int busca_matriz_ordenada(int matriz[][4], int linhas, int colunas, int alvo) {
    int linha = 0, coluna = colunas - 1;  // Começa no canto superior direito

    while (linha < linhas && coluna >= 0) {
        if (matriz[linha][coluna] == alvo) {
            return 1;  // Elemento encontrado
        }
        if (matriz[linha][coluna] > alvo) {
            coluna--;  // Move para a esquerda
        } else {
            linha++;  // Move para baixo
        }
    }
    return 0;  // Elemento não encontrado
}

int main() {
    int matriz[3][4] = {
        {1, 4, 7, 11},
        {2, 5, 8, 12},
        {3, 6, 9, 16}
    };
    int alvo = 5;

    if (busca_matriz_ordenada(matriz, 3, 4, alvo)) {
        printf("Elemento encontrado!\n");
    } else {
        printf("Elemento não encontrado.\n");
    }

    return 0;
}
```
- **Exercício 45**: Modifique o código para retornar a posição (linha, coluna) do elemento encontrado.

---

### **Código 46: Busca Binária em uma Árvore Binária de Busca (BST)**
A busca binária é a base para operações em árvores binárias de busca (BST). Aqui está um exemplo de busca em uma BST.

```c
#include <stdio.h>
#include <stdlib.h>

struct No {
    int valor;
    struct No *esquerda;
    struct No *direita;
};

struct No *criar_no(int valor) {
    struct No *novo = (struct No *)malloc(sizeof(struct No));
    novo->valor = valor;
    novo->esquerda = novo->direita = NULL;
    return novo;
}

int buscar_bst(struct No *raiz, int alvo) {
    if (raiz == NULL) {
        return 0;  // Elemento não encontrado
    }
    if (raiz->valor == alvo) {
        return 1;  // Elemento encontrado
    }
    if (alvo < raiz->valor) {
        return buscar_bst(raiz->esquerda, alvo);  // Busca na subárvore esquerda
    } else {
        return buscar_bst(raiz->direita, alvo);  // Busca na subárvore direita
    }
}

int main() {
    // Construindo uma BST simples
    struct No *raiz = criar_no(10);
    raiz->esquerda = criar_no(5);
    raiz->direita = criar_no(15);
    raiz->esquerda->esquerda = criar_no(2);
    raiz->esquerda->direita = criar_no(7);
    raiz->direita->esquerda = criar_no(12);
    raiz->direita->direita = criar_no(20);

    int alvo = 7;

    if (buscar_bst(raiz, alvo)) {
        printf("Elemento encontrado na BST!\n");
    } else {
        printf("Elemento não encontrado.\n");
    }

    return 0;
}
```
- **Exercício 46**: Implemente uma função para inserir um novo nó na BST.

---

### **Código 47: Busca Binária para Encontrar o Piso e o Teto**
O **piso** de um número é o maior elemento menor ou igual a ele, e o **teto** é o menor elemento maior ou igual a ele.

```c
#include <stdio.h>

int piso(int arr[], int n, int alvo) {
    int baixo = 0, alto = n - 1;
    int resultado = -1;

    while (baixo <= alto) {
        int meio = baixo + (alto - baixo) / 2;

        if (arr[meio] <= alvo) {
            resultado = arr[meio];  // Atualiza o piso
            baixo = meio + 1;  // Busca na metade direita
        } else {
            alto = meio - 1;  // Busca na metade esquerda
        }
    }
    return resultado;
}

int teto(int arr[], int n, int alvo) {
    int baixo = 0, alto = n - 1;
    int resultado = -1;

    while (baixo <= alto) {
        int meio = baixo + (alto - baixo) / 2;

        if (arr[meio] >= alvo) {
            resultado = arr[meio];  // Atualiza o teto
            alto = meio - 1;  // Busca na metade esquerda
        } else {
            baixo = meio + 1;  // Busca na metade direita
        }
    }
    return resultado;
}

int main() {
    int arr[] = {1, 2, 8, 10, 10, 12, 19};
    int n = sizeof(arr) / sizeof(arr[0]);
    int alvo = 5;

    printf("Piso de %d: %d\n", alvo, piso(arr, n, alvo));
    printf("Teto de %d: %d\n", alvo, teto(arr, n, alvo));

    return 0;
}
```
- **Exercício 47**: Modifique o código para retornar os índices do piso e do teto.

---

### **Código 48: Busca Binária para Encontrar a Raiz Quadrada**
Podemos usar busca binária para encontrar a raiz quadrada de um número com precisão.

```c
#include <stdio.h>

float raiz_quadrada(int numero, int precisao) {
    int baixo = 0, alto = numero;
    float resultado = -1;

    while (baixo <= alto) {
        int meio = baixo + (alto - baixo) / 2;

        if (meio * meio == numero) {
            return meio;  // Raiz exata encontrada
        }
        if (meio * meio < numero) {
            baixo = meio + 1;
            resultado = meio;  // Atualiza o resultado
        } else {
            alto = meio - 1;
        }
    }

    // Refina o resultado para a precisão desejada
    float incremento = 0.1;
    for (int i = 0; i < precisao; i++) {
        while (resultado * resultado <= numero) {
            resultado += incremento;
        }
        resultado -= incremento;
        incremento /= 10;
    }
    return resultado;
}

int main() {
    int numero = 10;
    int precisao = 3;

    printf("Raiz quadrada de %d: %.3f\n", numero, raiz_quadrada(numero, precisao));

    return 0;
}
```
- **Exercício 48**: Modifique o código para calcular a raiz cúbica de um número.

---

### **Código 49: Busca Binária para Encontrar o Menor Índice com Condição**
Podemos usar busca binária para encontrar o menor índice onde uma condição é verdadeira.

```c
#include <stdio.h>

int menor_indice_condicao(int arr[], int n, int alvo) {
    int baixo = 0, alto = n - 1;
    int resultado = n;  // Inicializa com um valor inválido

    while (baixo <= alto) {
        int meio = baixo + (alto - baixo) / 2;

        if (arr[meio] >= alvo) {
            resultado = meio;  // Atualiza o resultado
            alto = meio - 1;  // Busca na metade esquerda
        } else {
            baixo = meio + 1;  // Busca na metade direita
        }
    }
    return resultado;
}

int main() {
    int arr[] = {1, 2, 4, 4, 4, 5, 6};
    int n = sizeof(arr) / sizeof(arr[0]);
    int alvo = 4;

    printf("Menor índice onde arr[i] >= %d: %d\n", alvo, menor_indice_condicao(arr, n, alvo));

    return 0;
}
```
- **Exercício 49**: Modifique o código para encontrar o maior índice onde uma condição é verdadeira.

---

### **Código 50: Busca Binária para Encontrar o Pico em um Array**
Um pico em um array é um elemento maior que seus vizinhos. Podemos usar busca binária para encontrar um pico.

```c
#include <stdio.h>

int encontrar_pico(int arr[], int n) {
    int baixo = 0, alto = n - 1;

    while (baixo < alto) {
        int meio = baixo + (alto - baixo) / 2;

        if (arr[meio] < arr[meio + 1]) {
            baixo = meio + 1;  // Pico está à direita
        } else {
            alto = meio;  // Pico está à esquerda ou no meio
        }
    }
    return baixo;  // Retorna o índice do pico
}

int main() {
    int arr[] = {1, 3, 20, 4, 1, 0};
    int n = sizeof(arr) / sizeof(arr[0]);

    int pico = encontrar_pico(arr, n);
    printf("Pico encontrado no índice %d: %d\n", pico, arr[pico]);

    return 0;
}
```
- **Exercício 50**: Modifique o código para encontrar todos os picos no array.

---

### **Como Continuar**
1. **Reproduza os códigos no VS Code**.
2. **Resolva os exercícios** para fixar o aprendizado.
3. **Explore mais cenários**: Busca binária em grafos, algoritmos de ordenação, etc.

Se precisar de mais códigos ou explicações, é só pedir! Vamos transformar você em um expert em algoritmos de busca! 🚀💻😊

Claro! Vamos concluir o **Código 50**, que busca encontrar **todos os picos** em um array. Um pico é um elemento que é maior ou igual aos seus vizinhos. Vamos implementar uma função que retorna todos os índices dos picos no array.

---

### **Código 50: Encontrar Todos os Picos em um Array**

#### **Implementação Completa**
Aqui está o código completo para encontrar todos os picos em um array:

```c
#include <stdio.h>

// Função para encontrar todos os picos em um array
void encontrar_picos(int arr[], int n) {
    printf("Picos encontrados nos índices: ");

    // Verifica o primeiro elemento
    if (n == 1 || arr[0] >= arr[1]) {
        printf("0 ");
    }

    // Verifica os elementos do meio
    for (int i = 1; i < n - 1; i++) {
        if (arr[i] >= arr[i - 1] && arr[i] >= arr[i + 1]) {
            printf("%d ", i);
        }
    }

    // Verifica o último elemento
    if (n > 1 && arr[n - 1] >= arr[n - 2]) {
        printf("%d ", n - 1);
    }

    printf("\n");
}

int main() {
    int arr[] = {1, 3, 20, 4, 1, 0, 5, 2};
    int n = sizeof(arr) / sizeof(arr[0]);

    encontrar_picos(arr, n);

    return 0;
}
```

#### **Explicação do Código**
1. **Primeiro Elemento**:
   - Se o array tem apenas um elemento (`n == 1`), ele é automaticamente um pico.
   - Se o primeiro elemento é maior ou igual ao segundo (`arr[0] >= arr[1]`), ele é um pico.

2. **Elementos do Meio**:
   - Para cada elemento do meio, verificamos se ele é maior ou igual aos seus vizinhos (`arr[i] >= arr[i - 1] && arr[i] >= arr[i + 1]`).

3. **Último Elemento**:
   - Se o último elemento é maior ou igual ao penúltimo (`arr[n - 1] >= arr[n - 2]`), ele é um pico.

#### **Saída Esperada**
Para o array `{1, 3, 20, 4, 1, 0, 5, 2}`, a saída será:
```
Picos encontrados nos índices: 2 6 
```
- O índice `2` corresponde ao valor `20`.
- O índice `6` corresponde ao valor `5`.

---

### **Exercício 50: Modificações e Desafios**
Agora que você tem o código básico, aqui estão alguns desafios para praticar:

1. **Modificação 1**:
   - Altere o código para armazenar os índices dos picos em um array e retorná-los.

2. **Modificação 2**:
   - Implemente uma função que retorna os valores dos picos em vez dos índices.

3. **Desafio**:
   - Modifique o código para encontrar **vales** (elementos menores ou iguais aos seus vizinhos).

---

### **Exemplo de Modificação 1: Armazenar Índices dos Picos**
Aqui está como você pode modificar o código para armazenar os índices dos picos em um array:

```c
#include <stdio.h>

void encontrar_picos(int arr[], int n, int picos[], int *tamanho_picos) {
    *tamanho_picos = 0;  // Inicializa o tamanho do array de picos

    // Verifica o primeiro elemento
    if (n == 1 || arr[0] >= arr[1]) {
        picos[(*tamanho_picos)++] = 0;
    }

    // Verifica os elementos do meio
    for (int i = 1; i < n - 1; i++) {
        if (arr[i] >= arr[i - 1] && arr[i] >= arr[i + 1]) {
            picos[(*tamanho_picos)++] = i;
        }
    }

    // Verifica o último elemento
    if (n > 1 && arr[n - 1] >= arr[n - 2]) {
        picos[(*tamanho_picos)++] = n - 1;
    }
}

int main() {
    int arr[] = {1, 3, 20, 4, 1, 0, 5, 2};
    int n = sizeof(arr) / sizeof(arr[0]);
    int picos[n];  // Array para armazenar os índices dos picos
    int tamanho_picos;

    encontrar_picos(arr, n, picos, &tamanho_picos);

    printf("Picos encontrados nos índices: ");
    for (int i = 0; i < tamanho_picos; i++) {
        printf("%d ", picos[i]);
    }
    printf("\n");

    return 0;
}
```

#### **Saída Esperada**
Para o mesmo array `{1, 3, 20, 4, 1, 0, 5, 2}`, a saída será:
```
Picos encontrados nos índices: 2 6 
```

---

### **Exemplo de Modificação 2: Retornar Valores dos Picos**
Aqui está como você pode modificar o código para retornar os valores dos picos:

```c
#include <stdio.h>

void encontrar_picos(int arr[], int n, int picos[], int *tamanho_picos) {
    *tamanho_picos = 0;  // Inicializa o tamanho do array de picos

    // Verifica o primeiro elemento
    if (n == 1 || arr[0] >= arr[1]) {
        picos[(*tamanho_picos)++] = arr[0];
    }

    // Verifica os elementos do meio
    for (int i = 1; i < n - 1; i++) {
        if (arr[i] >= arr[i - 1] && arr[i] >= arr[i + 1]) {
            picos[(*tamanho_picos)++] = arr[i];
        }
    }

    // Verifica o último elemento
    if (n > 1 && arr[n - 1] >= arr[n - 2]) {
        picos[(*tamanho_picos)++] = arr[n - 1];
    }
}

int main() {
    int arr[] = {1, 3, 20, 4, 1, 0, 5, 2};
    int n = sizeof(arr) / sizeof(arr[0]);
    int picos[n];  // Array para armazenar os valores dos picos
    int tamanho_picos;

    encontrar_picos(arr, n, picos, &tamanho_picos);

    printf("Valores dos picos: ");
    for (int i = 0; i < tamanho_picos; i++) {
        printf("%d ", picos[i]);
    }
    printf("\n");

    return 0;
}
```

#### **Saída Esperada**
Para o mesmo array `{1, 3, 20, 4, 1, 0, 5, 2}`, a saída será:
```
Valores dos picos: 20 5 
```

---

### **Desafio: Encontrar Vales**
Um vale é um elemento menor ou igual aos seus vizinhos. Aqui está como você pode modificar o código para encontrar vales:

```c
#include <stdio.h>

void encontrar_vales(int arr[], int n, int vales[], int *tamanho_vales) {
    *tamanho_vales = 0;  // Inicializa o tamanho do array de vales

    // Verifica o primeiro elemento
    if (n == 1 || arr[0] <= arr[1]) {
        vales[(*tamanho_vales)++] = 0;
    }

    // Verifica os elementos do meio
    for (int i = 1; i < n - 1; i++) {
        if (arr[i] <= arr[i - 1] && arr[i] <= arr[i + 1]) {
            vales[(*tamanho_vales)++] = i;
        }
    }

    // Verifica o último elemento
    if (n > 1 && arr[n - 1] <= arr[n - 2]) {
        vales[(*tamanho_vales)++] = n - 1;
    }
}

int main() {
    int arr[] = {1, 3, 20, 4, 1, 0, 5, 2};
    int n = sizeof(arr) / sizeof(arr[0]);
    int vales[n];  // Array para armazenar os índices dos vales
    int tamanho_vales;

    encontrar_vales(arr, n, vales, &tamanho_vales);

    printf("Vales encontrados nos índices: ");
    for (int i = 0; i < tamanho_vales; i++) {
        printf("%d ", vales[i]);
    }
    printf("\n");

    return 0;
}
```

#### **Saída Esperada**
Para o array `{1, 3, 20, 4, 1, 0, 5, 2}`, a saída será:
```
Vales encontrados nos índices: 0 4 5 
```

---

### **Conclusão**
Agora você tem um código completo para encontrar **picos** e **vales** em um array, além de desafios para praticar. Se precisar de mais exemplos ou explicações, é só pedir! Vamos transformar você em um expert em algoritmos de busca! 🚀💻😊