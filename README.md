# Atividade-em-C

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define num_alunos 5
#define num_notas 4

int main() {
    char alunos[num_alunos][50];
    float notas[num_alunos][num_notas];
    float total[num_alunos] = {0};
    float media[num_alunos] = {0};
    char status[num_alunos][15];
    
    int opcao = 0;
    
    while (1) {
        system("cls");
        printf("Bem vindo ao sistema de notas\n\n");
        printf("Menu\n\n");
        printf("1- Cadastro de Alunos e Notas\n");
        printf("2- Alterar notas de Alunos\n");
        printf("3- Sair\n");
        scanf("%i", &opcao);

        switch (opcao) {
            case 1:
                for (int i = 0; i < num_alunos; i++) {
                    printf("Digite o nome do aluno %d: ", i + 1);
                    scanf("%s", alunos[i]);
                }
                for (int i = 0; i < num_alunos; i++) {
                    printf("Digite as notas do aluno %s:\n", alunos[i]);
                    for (int j = 0; j < num_notas; j++) {
                        do {
                            printf("Nota %d: ", j + 1);
                            scanf("%f", &notas[i][j]);
                            if (notas[i][j] < 0 || notas[i][j] > 10) {
                                printf("Nota inválida! Digite um valor entre 0 e 10.\n");
                            }
                        } while (notas[i][j] < 0 || notas[i][j] > 10);
                        total[i] += notas[i][j];
                    }
                    media[i] = total[i] / num_notas;
                    if (media[i] < 4) {
                        strcpy(status[i], "Reprovado");
                    } else if (media[i] >= 4 && media[i] <= 6) {
                        strcpy(status[i], "Recuperação");
                    } else {
                        strcpy(status[i], "Aprovado");
                    }
                }
                for (int i = 0; i < num_alunos; i++) {
                    printf("Aluno: %s\n", alunos[i]);
                    printf("Média: %.2f\n", media[i]);
                    printf("Status: %s\n\n", status[i]);
                }
                system("pause");
                break;
            case 2:
                for (int i = 0; i < num_alunos; i++) {
                    printf("Digite o nome do aluno %d: ", i + 1);
                    scanf("%s", alunos[i]);
                }
                for (int i = 0; i < num_alunos; i++) {
                    printf("Digite as notas do aluno %s:\n", alunos[i]);
                    for (int j = 0; j < num_notas; j++) {
                        do {
                            printf("Nota %d: ", j + 1);
                            scanf("%f", &notas[i][j]);
                            if (notas[i][j] < 0 || notas[i][j] > 10) {
                                printf("Nota inválida! Digite um valor entre 0 e 10.\n");
                            }
                        } while (notas[i][j] < 0 || notas[i][j] > 10);
                        total[i] += notas[i][j];
                    }
                    media[i] = total[i] / num_notas;
                    if (media[i] < 4) {
                        strcpy(status[i], "Reprovado");
                    } else if (media[i] >= 4 && media[i] <= 6) {
                        strcpy(status[i], "Recuperação");
                    } else {
                        strcpy(status[i], "Aprovado");
                    }
                }
                for (int i = 0; i < num_alunos; i++) {
                    printf("Aluno: %s\n", alunos[i]);
                    printf("Média: %.2f\n", media[i]);
                    printf("Status: %s\n\n", status[i]);
                }
                system("pause"); 
                break;
            case 3:
                printf("Saindo...\n");
                return 0;
            default:
                printf("Opção Inválida!\n");
                system("pause");
                break;
        }
    }

    return 0;
}
