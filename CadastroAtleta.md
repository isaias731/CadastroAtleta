import java.util.Scanner;

public class CadastroAtletas {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String resposta;

        do {
            System.out.print("Digite o nome do atleta: ");
            String nome = scanner.nextLine();

            System.out.print("Digite a idade do atleta: ");
            int idade = scanner.nextInt();
            scanner.nextLine(); // Limpar o buffer do scanner

            String categoria = definirCategoria(idade);

            System.out.println("\nInformações do Atleta:");
            System.out.println("Nome: " + nome);
            System.out.println("Idade: " + idade);
            System.out.println("Categoria: " + categoria);

            System.out.print("\nDeseja cadastrar outro atleta? (sim/não): ");
            resposta = scanner.nextLine();

        } while (resposta.equalsIgnoreCase("sim"));

        System.out.println("Programa encerrado.");
        scanner.close();
    }

    public static String definirCategoria(int idade) {
        if (idade <= 10) {
            return "Infantil";
        } else if (idade <= 15) {
            return "Juvenil";
        } else if (idade <= 19) {
            return "Júnior";
        } else if (idade <= 40) {
            return "Adulto";
        } else {
            return "Master";
        }
    }
}
