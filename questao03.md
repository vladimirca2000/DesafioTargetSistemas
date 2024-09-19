## Aqui está a solução:
~~~~ csharp
using System;
using System.Linq;

class FaturamentoDistribuidora
{
    static void Main()
    {
        // Vetor de faturamento diário (com zeros representando dias sem faturamento)
        decimal[] faturamentos = { 0, 1500, 2000, 0, 1800, 0, 0, 1900, 2200, 0, 1700, 0 };

        // Variáveis auxiliares
        decimal menorFaturamento = decimal.MaxValue;
        decimal maiorFaturamento = decimal.MinValue;
        decimal somaFaturamento = 0;
        int diasComFaturamento = 0;

        // Primeira varredura: encontra o menor e maior faturamento, e calcula a soma dos faturamentos válidos
        foreach (var faturamento in faturamentos)
        {
            if (faturamento > 0) // Ignora dias sem faturamento
            {
                if (faturamento < menorFaturamento) menorFaturamento = faturamento;
                if (faturamento > maiorFaturamento) maiorFaturamento = faturamento;

                somaFaturamento += faturamento;
                diasComFaturamento++;
            }
        }

        // Calcula a média de faturamento anual, excluindo os dias sem faturamento
        decimal mediaFaturamento = somaFaturamento / diasComFaturamento;

        // Segunda varredura: conta o número de dias com faturamento superior à média
        int diasAcimaDaMedia = faturamentos.Count(faturamento => faturamento > mediaFaturamento);

        // Resultados
        Console.WriteLine($"Menor faturamento do ano: {menorFaturamento}");
        Console.WriteLine($"Maior faturamento do ano: {maiorFaturamento}");
        Console.WriteLine($"Número de dias com faturamento superior à média anual: {diasAcimaDaMedia}");
    }
}
~~~~




