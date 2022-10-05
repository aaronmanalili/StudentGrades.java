# StudentGrades.java

An old assignment from my Fundamentals of Programming I class.

Given source code, I had to make modifications to it based on the assignment. Submitted on April 5, 2020

Text from Assignment:

Processing Grades 
The file Grades.java contains a program that reads in a sequence of student grades and computes the average grade, the 
number of students who pass (a grade of at least 60) and the number who fail. The program uses a loop (which you learn 
about in the next section). 
1. Compile and run the program to see how it works. 
2. Study the code and do the following. 
 Replace the statement that finds the sum of the grades with one that uses the += operator. 
 Replace each of three statements that increment a counting variable with statements using the increment operator. 
3. Run your program to make sure it works. 
4. Now replace the “if” statement that updates the pass and fail counters with the conditional operator. 
// ************************************************************ 
//  Grades.java 
// 
//  Read in a sequence of grades and compute the average 
//  grade, the number of passing grades (at least 60) 
//  and the number of failing grades. 
// ************************************************************ 
import java.util.Scanner; 
public class Grades 
{ 
// -----------------------------------------------------------------  
//  Reads in and processes grades until a negative number is entered. 
// -----------------------------------------------------------------  
public static void main (String[] args) 
{ 
  double grade;  //a student's grade 
  double sumOfGrades; // a running total of the student grades 
  int numStudents; //a count of the students 
  int numPass;     //a count of the number who pass 
  int numFail;     // a count of the number who fail 
  Scanner scan = new Scanner(System.in); 
  System.out.println ("\nGrade Processing Program\n"); 
// Initialize summing and counting variables 
  sumOfGrades = 0; 
  numStudents = 0; 
  numPass = 0; 
  numFail = 0; 
// Read in the first grade 
  System.out.print ("Enter the first student's grade: "); 
  grade = scan.nextDouble(); 
  while (grade >= 0) 
    { 
      sumOfGrades = sumOfGrades + grade; 
      numStudents = numStudents + 1; 
      
      if (grade < 60) 
      numFail = numFail + 1; 
      
      else 
      numPass = numPass + 1; 
 
      // Read the next grade 
      System.out.print ("Enter the next grade (a negative to quit): "); 
      grade = scan.nextDouble(); 
    } 
  if (numStudents > 0) 
    { 
      System.out.println ("\nGrade Summary: "); 
      System.out.println ("Class Average: " + sumOfGrades/numStudents); 
      System.out.println ("Number of Passing Grades: " + numPass); 
      System.out.println ("Number of Failing Grades: " + numFail); 
    } 
  else 
    System.out.println ("No grades processed."); 
  } 
} 
