# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>
int main() {
    int length, breadth, area;
    int *x, *y;
    printf("Enter length and breadth of rectangle: ");
    scanf("%d %d", &length, &breadth);
    x = &length;
    y = &breadth;
    area = (*x) * (*y);
    printf("Area of rectangle: %d\n", area);
    return 0;
}
```

## OUTPUT
```
Enter length and breadth of rectangle: 5 10
Area of rectangle: 50
```
		       	


## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
int main() {
    char *str;
    str = (char *)malloc(10 * sizeof(char));
    if (str == NULL) {
        printf("Memory not allocated.\n");
        return 1;
    }
    strcpy(str, "WELCOME");
    printf("%s\n", str);
    free(str);
    return 0;
}
```

## OUTPUT
```
WELCOME
```



## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 
.



# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```
#include <stdio.h>
struct Student {
    char name[50];
    int roll;
    float marks;
};
int main() {
    struct Student s;
    printf("Enter name: ");
    scanf("%s", s.name);
    printf("Enter roll number: ");
    scanf("%d", &s.roll);
    printf("Enter marks: ");
    scanf("%f", &s.marks);

    printf("\nStudent Details:\n");
    printf("Name: %s\n", s.name);
    printf("Roll Number: %d\n", s.roll);
    printf("Marks: %.2f\n", s.marks);
    return 0;
}
```


## OUTPUT
```
Enter name: John
Enter roll number: 101
Enter marks: 89.5

Student Details:
Name: John
Roll Number: 101
Marks: 89.50
```


## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>
struct Employee {
    char name[50];
    int id;
    float basic_salary, hra, da, gross_salary;
};
int main() {
    struct Employee e[3];
    int i;
    for(i = 0; i < 3; i++) {
        printf("Enter name, id, basic salary, hra, da for employee %d:\n", i + 1);
        scanf("%s %d %f %f %f", e[i].name, &e[i].id, &e[i].basic_salary, &e[i].hra, &e[i].da);
        e[i].gross_salary = e[i].basic_salary + e[i].hra + e[i].da;
    }
    printf("\nEmployee Details:\n");
    for(i = 0; i < 3; i++) {
        printf("Name: %s\nID: %d\nGross Salary: %.2f\n\n", e[i].name, e[i].id, e[i].gross_salary);
    }
    return 0;
}
```


 ## OUTPUT
 ```
Enter name, id, basic salary, hra, da for employee 1:
Alice 1 15000 3000 2000
Enter name, id, basic salary, hra, da for employee 2:
Bob 2 18000 3500 2500
Enter name, id, basic salary, hra, da for employee 3:
Charlie 3 20000 4000 3000

Employee Details:
Name: Alice
ID: 1
Gross Salary: 20000.00

Name: Bob
ID: 2
Gross Salary: 24000.00

Name: Charlie
ID: 3
Gross Salary: 27000.00
```

 

## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM
```
#include <stdio.h>
struct student {
    char name[10];
    int rollno;
    int subject[5];
    int total;
};
int main() {
    struct student s[2];
    int i, j;
    for(i = 0; i < 2; i++) {
        printf("Enter roll number for student %d: ", i + 1);
        scanf("%d", &s[i].rollno);
        printf("Enter 5 subject marks for student %d:\n", i + 1);
        for(j = 0; j < 5; j++) {
            scanf("%d", &s[i].subject[j]);
        }
    }
    for(i = 0; i < 2; i++) {
        s[i].total = 0;
        for(j = 0; j < 5; j++) {
            s[i].total += s[i].subject[j];
        }
        printf("\nStudent %d Total Marks: %d", i + 1, s[i].total);
        printf("\nStudent %d Average Marks: %.2f\n", i + 1, (float)s[i].total/5);
    }
    return 0;
}
```


## OUTPUT
```
Enter roll number for student 1: 1
Enter 5 subject marks for student 1:
75 80 78 70 71
Enter roll number for student 2: 2
Enter 5 subject marks for student 2:
80 79 78 73 73

Student 1 Total Marks: 374
Student 1 Average Marks: 74.80

Student 2 Total Marks: 383
Student 2 Average Marks: 76.60
```

 

## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


