# Escrevendo-as-Classes-de-Um-Jogo
Escrevendo as Classes de Um Jogo. DIO e GFT Brasil
# 3️⃣ Escrevendo as classes de um Jogo

**O Que deve ser utilizado**

- Variáveis
- Operadores
- Laços de repetição
- Estruturas de decisões
- Funções
- Classes e Objetos

## Objetivo:

Crie uma classe generica que represente um herói de uma aventura e que possua as seguintes propriedades:

- nome
- idade
- tipo (ex: guerreiro, mago, monge, ninja )

além disso, deve ter um método chamado atacar que deve atender os seguientes requisitos:

- exibir a mensagem: "o {tipo} atacou usando {ataque}")
- aonde o {tipo} deve ser concatenando o tipo que está na propriedade da classe
- e no {ataque} deve seguir uma descrição diferente conforme o tipo, seguindo a tabela abaixo:

se mago -> no ataque exibir (usou magia) <br>
se guerreiro -> no ataque exibir (usou espada)<br>
se monge -> no ataque exibir (usou artes marciais)<br>
se ninja -> no ataque exibir (usou shuriken)<br>

## Saída

Ao final deve se exibir uma mensagem:

- "o {tipo} atacou usando {ataque}"
  ex: mago atacou usando magia
  guerreiro atacou usando espada

## Código feito em java:
<br>
  
```
class Heroi {

    String ataque;
    String nome;
    int idade;
    String tipo;

    // Construtor
    public Heroi(String nome, int idade, String tipo) {
        this.nome = nome;
        this.idade = idade;
        this.tipo = tipo;
    }

    // Método para definir o ataque com base no tipo do herói
    public void atacar() {

        switch (this.tipo) {
            case "mago":
                this.ataque = "magia";
                break;
            case "guerreiro":
                this.ataque = "espada";
                break;
            case "monge":
                this.ataque = "artes marciais";
                break;
            case "ninja":
                this.ataque = "shuriken";
                break;
            default:
                this.tipo = "- " + this.tipo + " - é um TIPO INVÁLIDO";
                this.ataque = "ATAQUE INVÁLIDO";
                break;
        }

        // Saída -> ataque
        System.out.println("O " + this.tipo + " atacou usando " + this.ataque);
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        // Laço de repetição para criar heróis indefinidamente até que o usuário decida parar
        do {
            System.out.print("Informe o nome do herói: ");
            String nome = input.nextLine();

            System.out.print("Informe a idade do herói: ");
            int idade = input.nextInt();
            input.nextLine();

            System.out.print("Informe o tipo do herói [mago, guerreiro, monge ou ninja]: ");
            String tipo = input.nextLine().toLowerCase(); // Converter o tipo para minúsculas

            // Criando o herói com os dados fornecidos
            Heroi heroi = new Heroi(nome, idade, tipo);
            heroi.atacar(); // Chama o método atacar para definir e exibir o ataque do herói

            // Pergunta ao usuário se deseja continuar criando novos heróis
            System.out.print("Deseja criar um novo herói? [s/n] ");
            String sair = input.nextLine().toLowerCase();

            // Se o usuário digitar 'n', o laço é encerrado
            if (sair.equals("n")) {
                break;
            }

        } while (true);

        input.close(); // Fecha o scanner
    }
}
```
