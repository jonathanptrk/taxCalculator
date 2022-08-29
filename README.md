# TaxCalculator
Crie uma calculadora de imposto de renda que calcule qual será o imposto sobre o salário digitado pelo usuário(Considere as faixas do imposto de renda atual). 


package exercicios;
import java.util.Scanner;

public class CalculadoraImposto {
    public static void main(String[] args) {
        Scanner teclado = new Scanner(System.in);
        System.out.println("Digite o seu salário ?  (ex: 1975,80)");
        double salarioBase = teclado.nextDouble();

        /* A primeira faixa do imposto de renda vai de 0 a R$ 1.903,98 (isento)
        A segunda faixa vai de R$ 1.903,98 até R$ 2.826,65 (7,5%)
        A terceira faixa vai de R$ 2.826,65 até R$ 3.751,05 (15%)
        A quarta faixa vai de R$ 3.751,05 até R$ 4.664,68 (22,5%)
        A quinta e última faixa vai acima de R$ 4.664,68  (27,5%) */

        if (salarioBase < 1903.98) {
            System.out.println("Você é isento de imposto de renda");
        }else if(salarioBase > 1903.98 && salarioBase <= 2826.65){
            double primeiraFaixa = 0.075;
            double descontoPrimeiraFaixa = salarioBase * primeiraFaixa;
            System.out.println(" A sua faixa é de 7.5% de imposto");
            System.out.println(" O desconto será de: R$ " + (salarioBase * primeiraFaixa ));
            System.out.println(" O seu salário com os descontos é de: R$ " + (salarioBase - descontoPrimeiraFaixa));
        } else if (salarioBase > 2826.65 && salarioBase <= 3751.05){
            double segundaFaixa = 0.15;
            double descontoSegundaFaixa = salarioBase * segundaFaixa;
            System.out.println(" A sua faixa é de 15% de imposto");
            System.out.println(" O desconto será de: R$ " + (salarioBase * segundaFaixa ));
            System.out.println(" O seu salário com os descontos é de: R$ " + (salarioBase - descontoSegundaFaixa));
        } else if (salarioBase > 3751.05 && salarioBase <= 4664.68){
            double terceiraFaixa = 0.225;
            double descontoTerceiraFaixa = salarioBase * terceiraFaixa;
            System.out.println(" A sua faixa é de 22% de imposto");
            System.out.println(" O desconto será de: R$ " + (salarioBase * terceiraFaixa ));
            System.out.println(" O seu salário com os descontos é de: R$ " + (salarioBase - descontoTerceiraFaixa));
        } else if (salarioBase > 4664.68) {
            double quartaFaixa = 0.275;
            double descontoQuartaFaixa = salarioBase * quartaFaixa;
            System.out.println(" A sua faixa é de 27.5% de imposto");
            System.out.println(" O desconto será de: R$ " + (salarioBase * quartaFaixa));
            System.out.println(" O seu salário com os descontos é de: R$ " + (salarioBase - descontoQuartaFaixa));
        }
    }

}

