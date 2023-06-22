Maja 22812 C6


import java.util.Scanner;

/**
 * Klasa BMICalculator umożliwia obliczanie wskaźnika BMI (Body Mass Index)
 * na podstawie podanych wartości wagi i wzrostu.
 */
public class BMICalculator {
    /**
     * Metoda główna programu, która wykonuje obliczenia BMI na podstawie danych wprowadzonych przez użytkownika.
     *
     * @param args argumenty wiersza poleceń
     */
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Witaj w kalkulatorze BMI!");
        System.out.println("Podaj swoją wagę w kilogramach: ");
        double weight = scanner.nextDouble();

        System.out.println("Podaj swój wzrost w metrach: ");
        double height = scanner.nextDouble();

        double bmi = calculateBMI(weight, height);
        String category = getBMICategory(bmi);

        System.out.println("Twoje BMI wynosi: " + bmi);
        System.out.println("Kategoria BMI: " + category);

        scanner.close();
    }

    /**
     * Oblicza wskaźnik BMI na podstawie podanej wagi i wzrostu.
     *
     * @param weight waga w kilogramach
     * @param height wzrost w metrach
     * @return wartość wskaźnika BMI
     */
    public static double calculateBMI(double weight, double height) {
        return weight / (height * height);
    }

    /**
     * Zwraca kategorię BMI na podstawie wartości wskaźnika BMI.
     *
     * @param bmi wartość wskaźnika BMI
     * @return kategoria BMI
     */
    public static String getBMICategory(double bmi) {
        if (bmi < 18.5) {
            return "Niedowaga";
        } else if (bmi >= 18.5 && bmi < 25) {
            return "Prawidłowa waga";
        } else if (bmi >= 25 && bmi < 30) {
            return "Nadwaga";
        } else {
            return "Otyłość";
        }
    }
}

/**
 * Klasa InputValidator służy do walidacji danych wejściowych.
 */
class InputValidator {
    /**
     * Sprawdza, czy podana waga jest prawidłowa (większa od zera).
     *
     * @param weight waga do sprawdzenia
     * @return true, jeśli waga jest prawidłowa; false w przeciwnym razie
     */
    public static boolean isValidWeight(double weight) {
        return weight > 0;
    }

    /**
     * Sprawdza, czy podany wzrost jest prawidłowy (większy od zera).
     *
     * @param height wzrost do sprawdzenia
     * @return true, jeśli wzrost jest prawidłowy; false w przeciwnym razie
     */
    public static boolean isValidHeight(double height) {
        return height > 0;
    }
}

/**
 * Klasa BMIStatistics zawiera narzędzia do obliczania statystyk związanych z BMI.
 */
class BMIStatistics {
   
