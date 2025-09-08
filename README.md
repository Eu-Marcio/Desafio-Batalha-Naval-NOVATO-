//# Desafio-Batalha-Naval-NOVATO-
//Projeto simples, mas um desafio de programação estruturado, uma ótima maneira de aprimorar habilidades em linguagem C.

#include <stdio.h> // Biblioteca necessária para usar a função de impressão printf()

/*
 * PASSO 1: Definir uma estrutura para uma Coordenada.
 * Uma 'struct' agrupa diferentes tipos de dados. Aqui, agrupamos
 * dois inteiros, 'x' e 'y', para representar um ponto no tabuleiro.
 */
struct Coordenada {
    int x;                // Posição Horizontal
    int y;                 // Posição Vertical
};

int main() {
    printf("--- Desafio Batalha Naval: Nível Novato ---\n\n");     //Título do jogo.

    /*
     * PASSO 2: Definir os navios manualmente (entrada de dados).
     * Conforme o desafio, os valores são inseridos diretamente no código.
     */

    // Navio 1: HORIZONTAL
    int tamanho_H = 3;                             // Este navio terá 3 partes (Tamanho do navio) <<< DADO DE ENTRADA 1.
    int x_inicial_H = 5;                            // Posição X inicial <<< DADO DE ENTRADA 2.
    int y_inicial_H = 3;                          // Posição Y inicial <<< DADO DE ENTRADA 3.
    struct Coordenada navioHorizontal[tamanho_H];  // Vetor para guardar valor int tamanho_H.
    
    // Navio 2: VERTICAL
    int tamanho_V = 2;                           // Este navio terá 4 partes <<< DADO DE ENTRADA 4.
    int x_inicial_V = 5;                        // Posição X inicial <<< DADO DE ENTRADA 5.
    int y_inicial_V = 0;                         // Posição Y inicial <<< DADO DE ENTRADA 6.
    struct Coordenada navioVertical[tamanho_V];   // Vetor para guardaro valor int tamanho_V.

     /*
     * ===============================================================================
     *                    Um limite para o tabuleiro.
     * ===============================================================================
     *
     * Se quiséssemos um tabuleiro com limites (por exemplo, 15x15, indo de 0 a 14), 
     * a verificação aconteceria AQUI,
     * 
     * ANTES de calcular as posições.
     *
     * A lógica seria: "A coordenada final do navio ultrapassa o limite do tabuleiro?"
     *
     * Exemplo para um tabuleiro 15x15 (limites X e Y são 14):
     *
     * // Para o navio horizontal:
     * if (x_inicial_H + tamanho_H > 15) {
     * printf("Erro! O navio horizontal sairia do tabuleiro!\n");
     * } else {
     * // Só continua e calcula as posições se o navio couber.
     * }
     *
     * // Para o navio vertical:
     * if (y_inicial_V + tamanho_V > 15) {
     * printf("Erro! O navio vertical sairia do tabuleiro!\n");
     * } else {
     * // Só continua e calcula as posições se o navio couber.
     * }
     *
     * ===============================================================================
     */



    /*
     * PASSO 3: Calcular e preencher(laço for) as coordenadas de cada navio.
     */

    // Usamos um laço 'for' para percorrer cada parte do navio.
    // Lógica para preencher o navio HORIZONTAL
    for (int i = 0; i < tamanho_H; i++) {
        navioHorizontal[i].x = x_inicial_H + i; // A coordenada X aumenta (1, 2, 3...)
        navioHorizontal[i].y = y_inicial_H;     // A coordenada Y permanece a mesma.
    }

    // Lógica para preencher o navio VERTICAL
    for (int i = 0; i < tamanho_V; i++) {
        navioVertical[i].x = x_inicial_V;         // A coordenada X permanece a mesma.
        navioVertical[i].y = y_inicial_V + i;     // A coordenada Y aumenta (0, 1, 2, 3...)
    }

    /*
     * PASSO 4: Exibir os resultados no console (saída de dados).
     */
    printf("--- Coordenadas dos Navios Posicionados ---\n");

    // Imprime as coordenadas do primeiro navio
    printf("Navio Horizontal (Tamanho %d):\n", tamanho_H);
    for (int i = 0; i < tamanho_H; i++) {
        printf("  Parte %d: (%d, %d)\n", i + 1, navioHorizontal[i].x, navioHorizontal[i].y);
    }

    printf("\n"); // Adiciona uma linha em branco para melhor visualização

    // Imprime as coordenadas do segundo navio
    printf("Navio Vertical (Tamanho %d):\n", tamanho_V);
    for (int i = 0; i < tamanho_V; i++) {
        printf("  Parte %d: (%d, %d)\n", i + 1, navioVertical[i].x, navioVertical[i].y);
    }

    return 0; // Indica que o programa terminou com sucesso
}
