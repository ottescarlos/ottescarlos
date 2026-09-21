#include <stdio.h>

int main() {
    float limite;
    float temperatura;
    float soma = 0.0;
    float maior = -101.0;
    float menor = 101.0;
    
    int quantidade = 0;
    int acimaLimite = 0;
    int consecutivas = 0;

    // Solicita o limite de temperatura ao usuário
    do {
        printf("========================================\n");
        printf("     SISTEMA DE MONITORAMENTO\n");
        printf("========================================\n");
        printf("Digite o limite de temperatura (-100 a 100 C): ");

        // Verifica se foi digitado um número
        if (scanf("%f", &limite) != 1) {
            printf("Entrada invalida! Digite apenas numeros.\n");

            // Limpa o que ficou no teclado
            while (getchar() != '\n');

            limite = 101;
        } else if (limite < -100 || limite > 100) {
            printf("Limite invalido! Digite um valor entre -100 e 100.\n");
        }

    } while (limite < -100 || limite > 100);

    printf("\nMonitoramento iniciado!\n");
    printf("Digite as temperaturas entre -100 e 100 C.\n");
    printf("Digite -999 para encerrar manualmente.\n\n");

    // Continua realizando leituras enquanto o monitoramento estiver ativo
    while (1) {

        printf("Digite a temperatura: ");

        // Verifica se a entrada e numerica
        if (scanf("%f", &temperatura) != 1) {
            printf("Entrada invalida! Digite apenas numeros.\n");

            // Limpa a entrada invalida
            while (getchar() != '\n');

            continue;
        }

        // Valor especial para encerrar manualmente
        if (temperatura == -999) {
            printf("\nMonitoramento encerrado manualmente.\n");
            break;
        }

        // Valida a temperatura
        if (temperatura < -100 || temperatura > 100) {
            printf("Temperatura invalida! Digite entre -100 e 100 C.\n\n");

            // Temperatura invalida nao altera os calculos
            continue;
        }

        // Atualiza quantidade e soma das temperaturas
        quantidade++;
        soma += temperatura;

        // Verifica a maior temperatura
        if (temperatura > maior) {
            maior = temperatura;
        }

        // Verifica a menor temperatura
        if (temperatura < menor) {
            menor = temperatura;
        }

        // Verifica se a temperatura ultrapassou o limite
        if (temperatura > limite) {
            acimaLimite++;
            consecutivas++;

            printf("ALERTA: temperatura acima do limite!\n");
            printf("Temperaturas consecutivas acima do limite: %d\n",
                   consecutivas);

            // Encerra automaticamente após tres temperaturas consecutivas
            if (consecutivas == 3) {
                printf("\n*** ALERTA CRITICO ***\n");
                printf("Tres temperaturas consecutivas acima do limite!\n");
                printf("Monitoramento encerrado automaticamente.\n");
                break;
            }

        } else {
            // Reinicia a contagem quando a temperatura nao ultrapassa o limite
            consecutivas = 0;

            printf("Temperatura dentro do limite.\n");
        }

        printf("\n");
    }

    // Exibe o relatorio final
    printf("\n========================================\n");
    printf("          RELATORIO FINAL\n");
    printf("========================================\n");

    if (quantidade > 0) {
        printf("Quantidade de temperaturas: %d\n", quantidade);
        printf("Maior temperatura: %.2f C\n", maior);
        printf("Menor temperatura: %.2f C\n", menor);
        printf("Media das temperaturas: %.2f C\n",
               soma / quantidade);

        printf("Quantidade acima do limite: %d\n", acimaLimite);

        printf("Percentual acima do limite: %.2f%%\n",
               (acimaLimite * 100.0) / quantidade);
    } else {
        printf("Nenhuma temperatura valida foi registrada.\n");
    }

    printf("========================================\n");

    return 0;
}
