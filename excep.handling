public class GradeException extends Exception {
    public static final char[] VALID_GRADES = {'A', 'B', 'C', 'D', 'F', 'I'};

    public GradeException(String message) {
        super(message);
    }
}
import java.util.Scanner;

public class TestGrade {
    public static void main(String[] args) {
        int numStudents = 10;
        String[] studentIDs = new String[numStudents];
        char[] studentGrades = new char[numStudents];

        Scanner scanner = new Scanner(System.in);

        for (int i = 0; i < numStudents; i++) {
            System.out.print("Enter Student ID for student " + (i + 1) + ": ");
            studentIDs[i] = scanner.nextLine();

            try {
                System.out.print("Enter a letter grade for student " + (i + 1) + ": ");
                char grade = scanner.nextLine().toUpperCase().charAt(0);

                // Check if the entered grade is valid
                boolean isValidGrade = false;
                for (char validGrade : GradeException.VALID_GRADES) {
                    if (grade == validGrade) {
                        isValidGrade = true;
                        break;
                    }
                }

                if (!isValidGrade) {
                    throw new GradeException("Invalid grade entered. Setting grade to 'I' (Incomplete).");
                }

                studentGrades[i] = grade;
            } catch (GradeException e) {
                System.out.println(e.getMessage());
                studentGrades[i] = 'I'; // Set grade to 'I' for Incomplete
            }
        }

        scanner.close();

        // Display student IDs and grades
        System.out.println("\nStudent IDs and Grades:");
        for (int i = 0; i < numStudents; i++) {
            System.out.println("Student ID: " + studentIDs[i] + ", Grade: " + studentGrades[i]);
        }
    }
}
