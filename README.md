#include <stdio.h>

#define TAM 8

// Função para inicializar o tabuleiro com peças
void inicializarTabuleiro(char tabuleiro[TAM][TAM]) {
    // Peças pretas
    char linha1[] = {'T', 'C', 'B', 'D', 'R', 'B', 'C', 'T'};
    char linha2[] = {'P', 'P', 'P', 'P', 'P', 'P', 'P', 'P'};

    // Peças brancas
    char linha7[] = {'p', 'p', 'p', 'p', 'p', 'p', 'p', 'p'};
    char linha8[] = {'t', 'c', 'b', 'd', 'r', 'b', 'c', 't'};

    for (int i = 0; i < TAM; i++) {
        for (int j = 0; j < TAM; j++) {
            if (i == 0)
                tabuleiro[i][j] = linha1[j];
            else if (i == 1)
                tabuleiro[i][j] = linha2[j];
            else if (i == 6)
                tabuleiro[i][j] = linha7[j];
            else if (i == 7)
                tabuleiro[i][j] = linha8[j];
            else
                tabuleiro[i][j] = '.';
        }
    }
}

// Função imprimir tabuleiro
void imprimirTabuleiro(char tabuleiro[TAM][TAM]) {
    printf("  a b c d e f g h\n");
    for (int i = 0; i < TAM; i++) {
        printf("%d ", 8 - i);
        for (int j = 0; j < TAM; j++) {
            printf("%c ", tabuleiro[i][j]);
        }
        printf("\n");
    }
}

int main() {
    char tabuleiro[TAM][TAM];
    inicializarTabuleiro(tabuleiro);
    imprimirTabuleiro(tabuleiro);
    return 0;
}
