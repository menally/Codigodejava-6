java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Validacion de contraseña");
        int passwordCorrecta = 123;
        int passwordIngresada;
        do {
            System.out.println("Ingresa la contraseña numerica:");
            passwordIngresada = scanner.nextInt();

            if (passwordIngresada != passwordCorrecta) {
                System.out.println("Contraseña incorreta, Intentalo de nuevo");
            }
        } while (passwordIngresada != passwordCorrecta);
        System.out.println("Bienvenida al sistema");


        System.out.println("------------------------------------------------");
        System.out.println("FizzBuzz (1 al 30) ");

        for (int i = 1; i <= 30; i++) {
            if (i % 3 == 0 && i % 5 == 0) {
                System.out.println("FizzBuzz");
            } else if (i % 3 == 0) {
                System.out.println("Fizz");
            } else if (i % 5 == 0) {
                System.out.println("Buzz");
            } else {
                System.out.println(i);


            }
        }
        System.out.println("----------------------------------------");
        System.out.println("--- Cajero Automático ---");

                double saldo = 1000.0;
                int opcion;

                do {
                    System.out.println("\n--- Menú Principal ---");
                    System.out.println("1: Consultar saldo");
                    System.out.println("2: Retirar dinero");
                    System.out.println("3: Salir");
                    System.out.print("Elige una opción: ");
                    opcion = scanner.nextInt();

                    switch (opcion) {
                        case 1 -> {
                            System.out.println("Tu saldo actual es: $" + saldo);
                        }
                        case 2 -> {
                            System.out.print("¿Cuánto deseas retirar?: ");
                            double retiro = scanner.nextDouble();

                            if (retiro > saldo) {
                                System.out.println("Error: Fondos insuficientes. No puedes retirar más de lo que tienes.");
                            } else if (retiro <= 0) {
                                System.out.println("Cantidad inválida. Ingresa un monto mayor a 0.");
                            } else {
                                saldo -= retiro;
                                System.out.println("¡Retiro exitoso! Tu nuevo saldo es: $" + saldo);
                            }
                        }
                        case 3 -> {
                            System.out.println("Saliendo del cajero automático. ¡Gracias por tu visita!");
                        }
                        default -> {
                            System.out.println("Opción inválida. Por favor, elige una opción entre 1 y 3.");
                        }
                    }
                } while (opcion != 3);

                scanner.close();
            }
}
