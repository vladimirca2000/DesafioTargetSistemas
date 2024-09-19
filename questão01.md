~~~~
int INDICE = 12, SOMA = 0, K = 1;

while (K < INDICE)
{
    K = K + 1;
    SOMA = SOMA + K;
}

imprimir(SOMA);
~~~~

## Analise
* Inicialmente, K = 1, INDICE = 12 e SOMA = 0.
* O loop continua enquanto K < 12. A cada iteração, K é incrementado em 1 e o valor de K é adicionado à variável SOMA.

### Interações

1. K = 1 → K = K + 1 (K = 2), SOMA = SOMA + K (SOMA = 0 + 2 = 2)
2. K = 2 → K = K + 1 (K = 3), SOMA = SOMA + K (SOMA = 2 + 3 = 5)
3. K = 3 → K = K + 1 (K = 4), SOMA = SOMA + K (SOMA = 5 + 4 = 9)
4. K = 4 → K = K + 1 (K = 5), SOMA = SOMA + K (SOMA = 9 + 5 = 14)
5. K = 5 → K = K + 1 (K = 6), SOMA = SOMA + K (SOMA = 14 + 6 = 20)
6. K = 6 → K = K + 1 (K = 7), SOMA = SOMA + K (SOMA = 20 + 7 = 27)
7. K = 7 → K = K + 1 (K = 8), SOMA = SOMA + K (SOMA = 27 + 8 = 35)
8. K = 8 → K = K + 1 (K = 9), SOMA = SOMA + K (SOMA = 35 + 9 = 44)
9. K = 9 → K = K + 1 (K = 10), SOMA = SOMA + K (SOMA = 44 + 10 = 54)
10. K = 10 → K = K + 1 (K = 11), SOMA = SOMA + K (SOMA = 54 + 11 = 65)
11. K = 11 → K = K + 1 (K = 12), SOMA = SOMA + K (SOMA = 65 + 12 = 77)

## Resultado
Quando K atinge 12, a condição do while (K < 12) não é mais verdadeira, e o loop termina.
> o valor final de SOMA será 77.
