# Attendence-management-system-in-Artificial-Intellegence
// Original code for a basic Attendance Management System in Java
// Author: [Your Name]
// Date: [Current Date]

import java.util.HashMap;
import java.util.Map;
import java.util.Scanner;

class AttendanceManagementSystem {
    private Map<String, Boolean> attendanceMap;

    public AttendanceManagementSystem() {
        this.attendanceMap = new HashMap<>();
    }

    public void markAttendance(String studentId) {
        attendanceMap.put(studentId, true);
        System.out.println("Attendance marked for student ID: " + studentId);
    }

    public void displayAttendance() {
        System.out.println("Attendance Report:");
        for (Map.Entry<String, Boolean> entry : attendanceMap.entrySet()) {
            System.out.println("Student ID: " + entry.getKey() + ", Present: " + entry.getValue());
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        AttendanceManagementSystem attendanceSystem = new AttendanceManagementSystem();

        while (true) {
            System.out.println("1. Mark Attendance");
            System.out.println("2. Display Attendance");
            System.out.println("3. Exit");
            System.out.print("Enter your choice: ");

            int choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    System.out.print("Enter student ID: ");
                    String studentId = scanner.next();
                    attendanceSystem.markAttendance(studentId);
                    break;
                case 2:
                    attendanceSystem.displayAttendance();
                    break;
                case 3:
                    System.out.println("Exiting the Attendance Management System. Goodbye!");
                    scanner.close();
                    System.exit(0);
                    break;
                default:
                    System.out.println("Invalid choice. Please enter a valid option.");
            }
        }
    }
}
