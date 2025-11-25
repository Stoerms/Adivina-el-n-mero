# Adivina-el-n-mero
import java.util.Random;
import java.util.Scanner;

        class Main {

            public static void main(String[] args) {
                Scanner sc = new Scanner(System.in);
                Random rd = new Random();

                int numeroSecreto = rd.nextInt(100) + 1;  // número del 1 al 100
                int intento = 0;
                int intentos = 0;

                System.out.println("==================================");
                System.out.println("   ¡ADIVINA EL NÚMERO! (1-100)   ");
                System.out.println("==================================\n");

                while (true) {
                    System.out.print("Dime un número: ");

                    // Esto evita errores si metes letras
                    while (!sc.hasNextInt()) {
                        System.out.println("¡Eso no es un número! Inténtalo de nuevo.");
                        sc.next(); // limpiar el error
                        System.out.print("Dime un número: ");}
                      intento = sc.nextInt();
                        intentos++;

                    if (intento < numeroSecreto) {
                        System.out.println("¡Más alto! ↑\n");
                    } else if (intento > numeroSecreto) {
                        System.out.println("¡Más bajo! ↓\n");
                    } else {
                        System.out.println("==================================");
                        System.out.println("¡ENHORABUENA! Lo adivinaste");
                        System.out.println("Número de intentos: " + intentos);
                        System.out.println("==================================");
                        break;
                    }
                }

                sc.close();
            }
        }
