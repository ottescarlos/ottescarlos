# 🌡️ Sistema de Monitoramento de Temperaturas

## 1. Identificação

**Nome do aluno:** [SEU NOME]
**Disciplina:** [NOME DA DISCIPLINA]
**Professora:** Profa. Karla Sartin
**Título do projeto:** Sistema de Monitoramento de Temperaturas

---

## 2. Objetivo

O objetivo deste projeto é desenvolver um sistema em linguagem C capaz de realizar o monitoramento de temperaturas informadas pelo usuário.

O programa permite definir um limite de temperatura, registrar diversas leituras, identificar temperaturas acima do limite e verificar quando ocorrem três temperaturas consecutivas acima desse limite.

Ao final do monitoramento, o programa apresenta um relatório contendo a quantidade de temperaturas registradas, a média, a maior temperatura, a menor temperatura, a quantidade de temperaturas acima do limite e o percentual de leituras acima do limite.

---

## 3. Funcionamento do programa

### Definição do limite

Inicialmente, o programa solicita ao usuário um limite de temperatura.

O limite deve estar entre -100 °C e 100 °C. Caso o usuário informe um valor inválido ou um dado que não seja numérico, o programa solicita uma nova entrada.

### Realização das leituras

Depois que o limite é definido, o programa começa a receber as temperaturas.

As temperaturas também devem estar entre -100 °C e 100 °C.

Para encerrar manualmente o monitoramento, o usuário pode digitar o valor `-999`.

### Tratamento de valores inválidos

O programa verifica se o usuário digitou um número.

Quando uma entrada não numérica é informada, ela é identificada como inválida e o programa limpa a entrada antes de solicitar uma nova temperatura.

Temperaturas fora do intervalo permitido também são rejeitadas e não participam dos cálculos.

### Temperaturas acima do limite

Cada temperatura válida é comparada com o limite definido no início do programa.

Quando a temperatura é maior que o limite, o programa apresenta uma mensagem de alerta e aumenta a quantidade de temperaturas acima do limite.

### Contagem de temperaturas consecutivas

O programa possui um contador chamado `consecutivas`.

Quando uma temperatura ultrapassa o limite, esse contador é incrementado.

Quando uma temperatura está dentro do limite, o contador é zerado.

Dessa maneira, o programa consegue identificar quando três temperaturas consecutivas ultrapassam o limite.

Quando isso acontece, o monitoramento é encerrado automaticamente.

### Relatório final

Ao finalizar o monitoramento, o programa apresenta:

* quantidade de temperaturas registradas;
* maior temperatura;
* menor temperatura;
* média das temperaturas;
* quantidade de temperaturas acima do limite;
* percentual de temperaturas acima do limite.

---

## 4. Estruturas de repetição utilizadas

Neste projeto foram utilizadas as estruturas `do...while` e `while`.

### `do...while`

A estrutura `do...while` foi utilizada na definição do limite de temperatura.

Ela é adequada porque o programa precisa solicitar o limite pelo menos uma vez antes de verificar se o valor informado é válido.

Se o usuário informar um valor inválido, o processo é repetido até que um limite correto seja informado.

### `while`

A estrutura `while` foi utilizada para realizar o monitoramento das temperaturas.

Ela permite que o programa continue recebendo novas temperaturas enquanto o monitoramento estiver ativo.

O laço pode ser encerrado quando:

* o usuário digita `-999`;
* ou são registradas três temperaturas consecutivas acima do limite.

Também foi utilizado `while` para limpar entradas inválidas digitadas pelo usuário.

---

## 5. Como executar

### Compilação

Para compilar o programa utilizando o GCC, abra o terminal na pasta do projeto e execute:

```bash
gcc monitoramento.c -o monitoramento
```

### Execução no Windows

```bash
monitoramento.exe
```

### Execução no Linux ou macOS

```bash
./monitoramento
```

---

## 6. Testes realizados

### Teste 1 — Validação de entradas inválidas

**Objetivo:** verificar se o programa identifica entradas inválidas.

Foram testados valores que não correspondem a números e temperaturas fora do intervalo permitido.

**Resultado:** o programa apresentou mensagens de erro e solicitou uma nova entrada sem encerrar o monitoramento.

---

### Teste 2 — Temperaturas acima do limite, porém não consecutivas

**Objetivo:** verificar se o contador de temperaturas consecutivas é reiniciado quando uma temperatura fica dentro do limite.

**Exemplo:**

```text
Limite: 30

Temperaturas:
35
25
40
20
```

As temperaturas 35 °C e 40 °C ultrapassaram o limite, porém não foram consecutivas.

**Resultado:** o contador de temperaturas consecutivas foi reiniciado quando foram registradas temperaturas abaixo ou iguais ao limite. O programa continuou funcionando normalmente.

---

### Teste 3 — Três temperaturas consecutivas acima do limite

**Objetivo:** verificar o encerramento automático do monitoramento.

**Exemplo:**

```text
Limite: 30

Temperaturas:
35
40
45
```

As três temperaturas ficaram acima do limite de 30 °C.

**Resultado:** ao registrar a terceira temperatura consecutiva acima do limite, o programa apresentou um alerta crítico e encerrou automaticamente o monitoramento.

---

## 7. Organização do projeto

O projeto está organizado da seguinte forma:

```text
desafio-monitoramento/
│
├── monitoramento.c
│
├── README.md
│
└── evidencias/
    ├── teste01.png
    ├── teste02.png
    └── teste03.png
```

O arquivo `monitoramento.c` contém o código-fonte do programa.

O arquivo `README.md` contém a documentação técnica do projeto.

A pasta `evidencias` contém as capturas de tela dos testes realizados.

---

## 8. Reflexão final

Escolhi utilizar uma combinação das estruturas `do...while` e `while` porque cada uma atende melhor a uma parte diferente do algoritmo.

O `do...while` foi utilizado para definir o limite de temperatura, pois o usuário precisa informar um valor pelo menos uma vez antes que o programa possa verificar se ele é válido. Caso o valor esteja incorreto, a estrutura permite repetir a solicitação.

Já o `while` foi utilizado no monitoramento porque a quantidade de temperaturas não é conhecida antecipadamente. O programa precisa continuar recebendo valores até que o usuário encerre o processo ou até que sejam identificadas três temperaturas consecutivas acima do limite.

A diferença entre testar a condição antes ou depois da execução foi importante principalmente na definição do limite. Nesse momento, o `do...while` garante que a solicitação seja executada pelo menos uma vez. No monitoramento, o `while` permite controlar continuamente a entrada das temperaturas enquanto a condição de execução estiver válida.
