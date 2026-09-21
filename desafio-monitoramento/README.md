🌡️ Sistema de Monitoramento de Temperaturas
1. Identificação

Nome do aluno: [Carlos Henrique Fernandes Ottes]
Disciplina: []
Professora: Profa. Karla Sartin
Título do projeto: Sistema de Monitoramento de Temperaturas

2. Objetivo

O objetivo deste projeto é desenvolver um sistema em linguagem C capaz de realizar o monitoramento de temperaturas informadas pelo usuário.

O programa permite definir um limite de temperatura, registrar diversas leituras, identificar temperaturas acima do limite e verificar quando ocorrem três temperaturas consecutivas acima desse limite.

Ao final do monitoramento, o programa apresenta um relatório contendo a quantidade de temperaturas registradas, a média, a maior temperatura, a menor temperatura, a quantidade de temperaturas acima do limite e o percentual de leituras acima do limite.

3. Funcionamento do programa
Definição do limite

Inicialmente, o programa solicita ao usuário um limite de temperatura.

O limite deve estar entre -100 °C e 100 °C. Caso o usuário informe um valor inválido ou um dado que não seja numérico, o programa solicita uma nova entrada.

Realização das leituras

Depois que o limite é definido, o programa começa a receber as temperaturas.

As temperaturas também devem estar entre -100 °C e 100 °C.

Para encerrar manualmente o monitoramento, o usuário pode digitar o valor -999.

Tratamento de valores inválidos

O programa verifica se o usuário digitou um número.

Quando uma entrada não numérica é informada, ela é identificada como inválida e o programa limpa a entrada antes de solicitar uma nova temperatura.

Temperaturas fora do intervalo permitido também são rejeitadas e não participam dos cálculos.

Temperaturas acima do limite

Cada temperatura válida é comparada com o limite definido no início do programa.

Quando a temperatura é maior que o limite, o programa apresenta uma mensagem de alerta e aumenta a quantidade de temperaturas acima do limite.

Contagem de temperaturas consecutivas

O programa possui um contador chamado consecutivas.

Quando uma temperatura ultrapassa o limite, esse contador é incrementado.

Quando uma temperatura está dentro do limite, o contador é zerado.

Dessa maneira, o programa consegue identificar quando três temperaturas consecutivas ultrapassam o limite.

Quando isso acontece, o monitoramento é encerrado automaticamente.

Relatório final

Ao finalizar o monitoramento, o programa apresenta:

quantidade de temperaturas registradas;
maior temperatura;
menor temperatura;
média das temperaturas;
quantidade de temperaturas acima do limite;
percentual de temperaturas acima do limite.
