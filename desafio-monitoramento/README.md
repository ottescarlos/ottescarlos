# 🌡️ Sistema de Monitoramento de Temperaturas

## Identificação

**Aluno:** [Carlos Henrique Fernandes Ottes]
**Disciplina:** [Algoritmos e Pensamento Computacional ]
**Professora:** Profa. Karla Sartin

## Objetivo

Desenvolver um programa em C para monitorar temperaturas, verificar valores acima de um limite e encerrar automaticamente após três temperaturas consecutivas acima desse limite.

## Funcionamento

O usuário define um limite de temperatura e depois informa as temperaturas.

O programa:

* valida entradas inválidas;
* identifica temperaturas acima do limite;
* conta temperaturas consecutivas acima do limite;
* calcula média, maior, menor, quantidade e percentual;
* encerra após três temperaturas consecutivas acima do limite ou quando o usuário digita `-999`.

## Estruturas utilizadas

Foi utilizado **do...while** para garantir que o limite seja informado corretamente.

O **while** foi utilizado para realizar as leituras das temperaturas até que uma condição de encerramento aconteça.

## Como executar

```bash
gcc monitoramento.c -o monitoramento
./monitoramento
```

No Windows:

```bash
gcc monitoramento.c -o monitoramento.exe
monitoramento.exe
```

## Testes

**Teste 1:** entradas inválidas foram rejeitadas corretamente.

**Teste 2:** temperaturas acima do limite, mas não consecutivas, não encerraram o programa.

**Teste 3:** três temperaturas consecutivas acima do limite encerraram o monitoramento automaticamente.

As evidências dos testes estão na pasta `evidencias/`.

## Reflexão

Escolhi `do...while` para validar o limite porque ele precisa ser solicitado pelo menos uma vez. Usei `while` para o monitoramento porque a quantidade de temperaturas não é conhecida e o programa deve continuar até uma condição de encerramento.
