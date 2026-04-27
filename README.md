MINI PROJECT

NAME:VAIRA PRAKASH V

CLASS:ICSE-B

SUBJECT: DATA STRUCTURE

REG NO: 711525BCS175
---------------------------------------------------------------------------------------------------------------------------------------------------------------------
1. Aim
To design and implement a ticket booking system that checks seat availability dynamically using Binary Search, and
performs efficient sorting and searching operations.

2. Problem Statement
A ticket booking system needs to manage seat availability efficiently. The system should store seat numbers, sort
them, and allow users to search for a specific seat using binary search to quickly determine availability.

3. Algorithm
Step 1: Start
Step 2: Input number of seats (n)
Step 3: Enter seat numbers
Step 4: Sort the seat numbers (Ascending)
Step 5: Input seat number to search
Step 6: Apply Binary Search:
 Set low = 0, high = n-1
 Repeat until low <= high
o mid = (low + high) / 2
o If seat[mid] == key → Seat Found
o If key < seat[mid] → Search left half
o Else → Search right half
Step 7: Display result (Available / Not Available)
Step 8: Stop

4. C Program
import java.util.Scanner;
class TicketSystem {
public static int binarySearch(int seats[], int key) {
int low = 0;

int high = seats.length - 1;

while (low <= high) {
int mid = (low + high) / 2;

if (seats[mid] == key)
return mid;
else if (seats[mid] < key)
low = mid + 1;
else
high = mid - 1;
}
return -1; // Seat not found
}

public static void displaySeats(int seats[]) {
System.out.println("\nAvailable Seats:");
for (int seat : seats) {
if (seat != -1)
System.out.print(seat + " ");
}
System.out.println();
}

public static void main(String[] args) {

Scanner sc = new Scanner(System.in);

int seats[] = {1,2,3,4,5,6,7,8,9,10};

int choice, seatNo;

do {
System.out.println("\n===== Ticket Booking System =====");

System.out.println("1. View Available Seats");
System.out.println("2. Book Ticket");
System.out.println("3. Search Seat");
System.out.println("4. Exit");
System.out.print("Enter choice: ");
choice = sc.nextInt();

switch(choice) {

case 1:
displaySeats(seats);
break;

case 2:
System.out.print("Enter seat number to book: ");
seatNo = sc.nextInt();

int index = binarySearch(seats, seatNo);

if(index != -1 && seats[index] != -1) {
seats[index] = -1; // Mark booked
System.out.println("seat " + seatNo + " booked successfully!");
} else {
System.out.println("seat not available!");
}
break;

case 3:
System.out.print("Enter seat number to search: ");
seatNo = sc.nextInt();
index = binarySearch(seats, seatNo);

if(index != -1 && seats[index] != -1)
System.out.println("seat Available");

else
System.out.println("seat Not Available");
break;

case 4:
System.out.println("Thank You!");
break;

default:
System.out.println("Invalid choice!");
}

} while(choice != 4);

sc.close();
}
}

5. Output:
===== Ticket Booking System =====
1. View Available Seats
2. Book Ticket
3. Search Seat
4. Exit
Enter choice: 1

Available Seats:
1 2 3 4 5 6 7 8 9 10

===== Ticket Booking System =====
1. View Available Seats
2. Book Ticket
3. Search Seat
4. Exit

Enter choice: 2
Enter seat number to book: 5
seat 5 booked successfully!

===== Ticket Booking System =====
1. View Available Seats
2. Book Ticket
3. Search Seat
4. Exit
Enter choice: 1

Available Seats:
1 2 3 4 6 7 8 9 10

===== Ticket Booking System =====
1. View Available Seats
2. Book Ticket
3. Search Seat
4. Exit
Enter choice: 3
Enter seat number to search: 5
seat Not Available

===== Ticket Booking System =====
1. View Available Seats
2. Book Ticket
3. Search Seat
4. Exit
Enter choice: 4
