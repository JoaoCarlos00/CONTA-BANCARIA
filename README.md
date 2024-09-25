# ETAPA 6 AC1

Criação de uma classe de conta bancária com condições

## 🚀 Enunciados

Crie uma classe conta bancária da qual o atributo saldo é encapsulado e seu valor será acessado por meio dos métodos, depósito, saque e consulta.

Para cada depósito deve ser cobrado uma taxa de 1%.
Para cada saque deve ser cobrado uma taxa de 0,5%.
A cada 5 consultas, será cobrado uma taxa de 0,10 centavos.

### 📋 Códigos
Crie uma classe conta bancária da qual o atributo saldo é encapsulado e seu valor será acessado por meio dos métodos, depósito, saque e consulta.

Para cada depósito deve ser cobrado uma taxa de 1%.
Para cada saque deve ser cobrado uma taxa de 0,5%.
A cada 5 consultas, será cobrado uma taxa de 0,10 centavos.

import java.util.Scanner;

public class ContaBancaria { //Criaçao da classe da conta e seus atributos
    private double saldo;
    private int contadorConsultas;

    public ContaBancaria(double saldoInicial) { //Utilizei o metodo constructor, getters e setters para validaçao e controle dos atrbiutos do recem objeto criado
        this.saldo = saldoInicial;
        this.contadorConsultas = 0;
    }

    public double getSaldo() {
        return saldo;
    }

    public void deposito(double valor) { //Condição que o deposito na conta deve ser maior que zero
        if (valor <= 0) {
            System.out.println("Valor de depósito deve ser maior que zero.");
            return;
        }
        double taxa = valor * 0.01; // Condição de 1% de taxa do deposito
        saldo += valor - taxa;
        System.out.printf("Depósito de" + valor + "realizado com taxa de " + taxa + ". Saldo atual: " + saldo);
    }

    public void saque(double valor) { //Condiçao que o saque deve ser maior que zero
        if (valor <= 0) {
            System.out.println("Valor de saque deve ser maior que zero.");
            return;
        }
        double taxa = valor * 0.005; //Condição de 0,5% de taxa do valor saque
        if (saldo >= valor + taxa) {
            saldo -= valor + taxa;
            System.out.printf("Saque de " + valor + "realizado com taxa de " + taxa + "Saldo atual: " + saldo);
        } else {
            System.out.println("Saldo insuficiente para saque.");
        }
    }

    public void consulta() { 
        contadorConsultas++;
        if (contadorConsultas % 5 == 0) {
            saldo -= 0.10; // Condçao de cobrança de 10 centavos por consulta
            System.out.printf("Consulta realizada. Cobrança de R$ 0,10 aplicada. Saldo atual: " + saldo);
        } else {
            System.out.printf("Consulta realizada. Saldo atual: " + saldo);
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ContaBancaria conta = new ContaBancaria(1138.00); // Saldo inicial de R$ 1138,00
        conta.consulta(); // Consulta 1
        conta.consulta(); // Consulta 2
        conta.deposito(200.00); // Depósito
        conta.consulta(); // Consulta 3
        conta.saque(150.00); // Saque
        conta.consulta(); // Consulta 4
        conta.consulta(); // Consulta 5
        conta.consulta(); // Consulta 6 (cobrança de R$ 0,10)

    }
}
//NOTA: Tive dificuldade com a parte de imprimir esta ultima parte do condigo, ele da em uma linha só tudo e nao consegui resolver e não entendi pelo chatgpt portanto achei melhor deixar como está e entendo que possa interferir na nota da avaliação
### 🔧 Instalação

* Explicação de como deve ser utilizado o projeto

## 🛠️ Construído com

Ferramentas utilizadas e bibliotecas

* IDE Eclipse

## 📌 Versão

* **Versão 1.0** caso seja atualizado manter a descrição inicial e inserir uma nova linha com descrição da atualização.
* **Versão 1.1** - *Refatoração* *data 09/09/24*

## ✒️ Autores

João Carlos Ferreira de Araujo RA 248152 -- Programação Orientada à Objetos

