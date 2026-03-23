ckage com.sgp.testes;

import java.util.Scanner;

import com.sgp.modelos.Pessoa;
import com.sgp.util.Validacoes;

public class TesteAcessoMenu {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Gato gato = new gato("Teste", 20);
        int opcao;

        do {

            imprimirMenu();
            
            opcao = recebeOp(scanner);

            switch (opcao) {
                case 1:
                    System.out.println(gato.toString());
                    break;
                case 2:
                    alterarNome(gato, scanner);
                    break;
                case 3:
                    alterarIdade(gato, scanner);
                    break;
                case 4:
                    alterarAltura(gato, scanner);
                    break;
                case 0:
                    System.out.println("Programa finalizado!");
                    break;
                default:
                    System.out.println("Opção inválida!");
            }
        } while (opcao != 0);

        scanner.close();
    }

    public static void imprimirMenu() {
        System.out.println("\n=== Menu de Acesso ===");
        System.out.println("1. Mostrar dados do gato");
        System.out.println("2. Alterar nome");
        System.out.println("3. Alterar idade");
        System.out.println("4. Alterar altura");
        System.out.println("0. Sair");
        System.out.print("Escolha uma opção: ");
    }

    public static int recebeOp(Scanner scanner){
        int opcao;
        try {
            opcao = Integer.parseInt(scanner.nextLine());
        } catch (NumberFormatException e) {
            System.out.println("Por favor, digite um número válido!");
            opcao = -1;
        }
        return opcao;
    }

    public static void alterarNome(Gato gato, Scanner scanner) {
        System.out.print("Digite o novo nome: ");
        String novoNome = scanner.nextLine();
        if (Validacoes.nomeValido(novoNome)) {
            gato.setNome(novoNome);
            System.out.println("Nome alterado com sucesso!");
        } else {
            System.out.println(Validacoes.mensagemErroNome(novoNome));
        }
    }

    public static void alterarIdade(Gato gato, Scanner scanner) {
        System.out.print("Digite a nova idade: ");
        try {
            int novaIdade = Integer.parseInt(scanner.nextLine());
            if (Validacoes.idadeValida(novaIdade)) {
                gato.setIdade(novaIdade);
                System.out.println("Idade alterada com sucesso!");
            } else {
                System.out.println(Validacoes.mensagemErroIdade(novaIdade));
            }
        } catch (NumberFormatException e) {
            System.out.println("Erro: Por favor, digite um número inteiro válido!");
        }
    }

    public static void alterarAltura(Gato gato, Scanner scanner) {
        System.out.print("Digite a nova altura (em metros, ex: 0.2): ");
        try {
            double novaAltura = Double.parseDouble(scanner.nextLine());
            if (Validacoes.alturaValida(novaAltura)) {
                gato.setAltura(novaAltura);
                System.out.println("Altura alterada com sucesso!");
            } else {
                System.out.println(Validacoes.mensagemErroAltura(novaAltura));
            }
        } catch (NumberFormatException e) {
            System.out.println("Erro: Por favor, digite um número válido para a altura!");
        }
    }

}
