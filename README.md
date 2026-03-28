import java.util.Scanner;

class management {
    int studentId;
    String name;
    int age;
    String course;
    double marks;
    Scanner sc = new Scanner(System.in);
    void inputDetails() {
        System.out.print("Enter ID: ");
        studentId = sc.nextInt();
        sc.nextLine();
        System.out.print("Enter Name: ");
        name = sc.nextLine();
        System.out.print("Enter Age: ");
        age = sc.nextInt();
        sc.nextLine();
        System.out.print("Enter Course: ");
        course = sc.nextLine();
        System.out.print("Enter Marks: ");
        marks = sc.nextDouble();
    }
    void displayDetails() {
        System.out.println(studentId + " " + name + " " + age + " " + course + " " + marks);
    }
}

public class Student1 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        management s[] = new management[5];   
        int n = 0;
        int choice;
        do {
            System.out.println("\n1 Add");
            System.out.println("2 Display");
            System.out.println("3 Search by ID");
            System.out.println("4 Marks above X");
            System.out.println("5 Exit");
            choice = sc.nextInt();
            switch (choice) {
                case 1:
                    s[n] = new management();   
                    s[n].inputDetails();
                    n++;
                    break;
                case 2:
                    for (int i = 0; i < n; i++) {
                        s[i].displayDetails();
                    }
                    break;
                case 3:
                    System.out.print("Enter ID: ");
                    int id = sc.nextInt();
                    for (int i = 0; i < n; i++) {
                        if (s[i].studentId == id) {
                            s[i].displayDetails();
                        }
                    }
                    break;
                case 4:
                    System.out.print("Enter marks: ");
                    double m = sc.nextDouble();
                    for (int i = 0; i < n; i++) {
                        if (s[i].marks > m) {
                            s[i].displayDetails();
                        }
                    }
                    break;
            }
        } while (choice != 5);
    }
}
