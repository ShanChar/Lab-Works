# Lab Works 1: User Defined Function
**1. Write a program to find the simple interest using function.**  
```C
#include <stdio.h>

float calculateSimpleInterest(float principal, float rate, float time) {
    return (principal * rate * time) / 100;
}

int main() {
    float principal, rate, time;
    printf("Enter principal amount: ");
    scanf("%f", &principal);
    printf("Enter rate of interest: ");
    scanf("%f", &rate);
    printf("Enter time (in years): ");
    scanf("%f", &time);

    float interest = calculateSimpleInterest(principal, rate, time);

    printf("Simple Interest = %.2f\n", interest);

    return 0;
}

```
**2. Write a program to find out greatest number among four different numbers.**  
```C
#include <stdio.h>

int findMax(int a, int b, int c, int d) {
    int max = a;
    if (b > max) max = b;
    if (c > max) max = c;
    if (d > max) max = d;
    return max;
}

int main() {
    int num1, num2, num3, num4;
    printf("Enter four numbers: ");
    scanf("%d %d %d %d", &num1, &num2, &num3, &num4);

    int max = findMax(num1, num2, num3, num4);

    printf("The greatest number is %d\n", max);

    return 0;
}

```
**3. Write a program to display the multiplication table of given number.**  
```C
#include <stdio.h>

void displayMultiplicationTable(int num) {
    for (int i = 1; i <= 10; i++) {
        printf("%d x %d = %d\n", num, i, num * i);
    }
}

int main() {
    int number;
    printf("Enter a number to display its multiplication table: ");
    scanf("%d", &number);

    displayMultiplicationTable(number);

    return 0;
}

```
**4. Write a program using user defined function to calculate y raise power to x.**
```C
#include <stdio.h>

double power(double x, int y) {
    double result = 1.0;
    for (int i = 0; i < y; i++) {
        result *= x;
    }
    return result;
}

int main() {
    double base;
    int exponent;
    printf("Enter base: ");
    scanf("%lf", &base);
    printf("Enter exponent: ");
    scanf("%d", &exponent);

    double result = power(base, exponent);

    printf("%.2lf ^ %d = %.2lf\n", base, exponent, result);

    return 0;
}

```  
**5. Write a program to find the factorial of a number using recursion.**    
```C
#include <stdio.h>

int factorial(int n) {
    if (n == 0 || n == 1) {
        return 1;
    }
    return n * factorial(n - 1);
}

int main() {
    int number;
    printf("Enter a number to find its factorial: ");
    scanf("%d", &number);

    int result = factorial(number);

    printf("Factorial of %d = %d\n", number, result);

    return 0;
}

```
**6.Write a program to display the fibonacci series using recursion.**  
```C
#include <stdio.h>

int fibonacci(int n) {
    if (n <= 1) {
        return n;
    }
    return fibonacci(n - 1) + fibonacci(n - 2);
}

int main() {
    int terms;
    printf("Enter the number of terms in the Fibonacci series: ");
    scanf("%d", &terms);

    printf("Fibonacci Series:\n");
    for (int i = 0; i < terms; i++) {
        printf("%d ", fibonacci(i));
    }

    printf("\n");

    return 0;
}

```
**7. Write a program to find sum and average of n numbers using array and function.** 
```C
#include <stdio.h>

void calculateSumAndAverage(int arr[], int n, int *sum, float *average) {
    *sum = 0;
    for (int i = 0; i < n; i++) {
        *sum += arr[i];
    }
    *average = (float)*sum / n;
}

int main() {
    int n;
    printf("Enter the number of elements: ");
    scanf("%d", &n);

    int numbers[n];
    for (int i = 0; i < n; i++) {
        printf("Enter number %d: ", i + 1);
        scanf("%d", &numbers[i]);
    }

    int sum;
    float average;

    calculateSumAndAverage(numbers, n, &sum, &average);

    printf("Sum = %d\n", sum);
    printf("Average = %.2f\n", average);

    return 0;
}

``` 
**8.Write a program to print greatest number among n numbers using array and function.**  
```C
#include <stdio.h>

int findMax(int arr[], int n) {
    int max = arr[0];
    for (int i = 1; i < n; i++) {
        if (arr[i] > max) {
            max = arr[i];
        }
    }
    return max;
}

int main() {
    int n;
    printf("Enter the number of elements: ");
    scanf("%d", &n);

    int numbers[n];
    for (int i = 0; i < n; i++) {
        printf("Enter number %d: ", i + 1);
        scanf("%d", &numbers[i]);
    }

    int max = findMax(numbers, n);

    printf("The greatest number is %d\n", max);

    return 0;
}

```
**9.Write a program to print transpose of matrices (2 × 2 type) using array and function.**  
```C
#include <stdio.h>

void transpose(int mat[2][2]) {
    int temp = mat[0][1];
    mat[0][1] = mat[1][0];
    mat[1][0] = temp;
}

int main() {
    int matrix[2][2];
    printf("Enter elements of the 2x2 matrix:\n");
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }

    transpose(matrix);

    printf("Transpose of the matrix:\n");
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }

    return 0;
}

```
**10.Write a program to print sum of two matrices (2 × 2 type) using array and function.**  
```C
#include <stdio.h>

void addMatrices(int mat1[2][2], int mat2[2][2], int result[2][2]) {
        for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            result[i][j] = mat1[i][j] + mat2[i][j];
        }
    }
}

int main() {
    int matrix1[2][2], matrix2[2][2], result[2][2];
    
    printf("Enter elements of the first 2x2 matrix:\n");
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            scanf("%d", &matrix1[i][j]);
        }
    }

    printf("Enter elements of the second 2x2 matrix:\n");
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            scanf("%d", &matrix2[i][j]);
        }
    }

    addMatrices(matrix1, matrix2, result);

    printf("Sum of the matrices:\n");
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            printf("%d ", result[i][j]);
        }
        printf("\n");
    }

    return 0;
}


```

# Lab Works 2: Structure and Union
**1. Write a program considering user defined variable distance with members: feet and inch. Calculate the sum two different distances.**  
```C
#include <stdio.h>

struct Distance {
    int feet;
    float inch;
};

int main() {
    struct Distance d1, d2, sum;

    printf("Enter first distance (feet inch): ");
    scanf("%d %f", &d1.feet, &d1.inch);

    printf("Enter second distance (feet inch): ");
    scanf("%d %f", &d2.feet, &d2.inch);

    sum.feet = d1.feet + d2.feet;
    sum.inch = d1.inch + d2.inch;

    if (sum.inch >= 12.0) {
        sum.inch -= 12.0;
        sum.feet++;
    }

    printf("Sum of distances: %d feet %.2f inches\n", sum.feet, sum.inch);

    return 0;
}

```
**2. Write a program considering user defined variable time with members: hh,mm, and ss. Calculate the sum of different times.**  
```C
#include <stdio.h>

struct Time {
    int hh, mm, ss;
};

int main() {
    struct Time t1, t2, sum;

    printf("Enter first time (hh:mm:ss): ");
    scanf("%d:%d:%d", &t1.hh, &t1.mm, &t1.ss);

    printf("Enter second time (hh:mm:ss): ");
    scanf("%d:%d:%d", &t2.hh, &t2.mm, &t2.ss);

    sum.ss = t1.ss + t2.ss;
    sum.mm = t1.mm + t2.mm + (sum.ss / 60);
    sum.ss %= 60;
    sum.hh = t1.hh + t2.hh + (sum.mm / 60);
    sum.mm %= 60;

    printf("Sum of times: %02d:%02d:%02d\n", sum.hh, sum.mm, sum.ss);

    return 0;
}

```
**3. Consider structure student with members: sid, name and height. Write a program that takes maximum 100 records, rearrange the records in ascending order on the basic of height and prints them.**  
```C
#include <stdio.h>
#include <string.h>

struct Student {
    int sid;
    char name[50];
    float height;
};

void sortStudents(struct Student students[], int n) {
    struct Student temp;
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (students[j].height > students[j + 1].height) {
                temp = students[j];
                students[j] = students[j + 1];
                students[j + 1] = temp;
            }
        }
    }
}

int main() {
    int n;
    printf("Enter the number of students (up to 100): ");
    scanf("%d", &n);

    struct Student students[100];

    for (int i = 0; i < n; i++) {
        printf("Enter Student %d details:\n", i + 1);
        students[i].sid = i + 1;
        printf("Name: ");
        scanf("%s", students[i].name);
        printf("Height (in cm): ");
        scanf("%f", &students[i].height);
    }

    sortStudents(students, n);

    printf("\nSorted Student Records (Ascending Order of Height):\n");
    printf("SID\tName\tHeight\n");
    for (int i = 0; i < n; i++) {
        printf("%d\t%s\t%.2f cm\n", students[i].sid, students[i].name, students[i].height);
    }

    return 0;
}

```
**4. Write a program that takes empid, name and salary of 100 employees and search a particular employee's record in the array of structure on the basis of empid. Also find the position of the record.**  
```C
#include <stdio.h>

struct Employee {
    int empid;
    char name[50];
    float salary;
};

int searchEmployee(struct Employee employees[], int n, int targetEmpid) {
    for (int i = 0; i < n; i++) {
        if (employees[i].empid == targetEmpid) {
            return i; 
        }
    }
    return -1; 
}

int main() {
    int n, targetEmpid;
    printf("Enter the number of employees (up to 100): ");
    scanf("%d", &n);

    struct Employee employees[100];

    for (int i = 0; i < n; i++) {
        printf("Enter Employee %d details:\n", i + 1);
        printf("Empid: ");
        scanf("%d", &employees[i].empid);
        printf("Name: ");
        scanf("%s", employees[i].name);
        printf("Salary: ");
        scanf("%f", &employees[i].salary);
    }

    printf("Enter the empid to search: ");
    scanf("%d", &targetEmpid);

    int position = searchEmployee(employees, n, targetEmpid);

    if (position != -1) {
        printf("Employee found at position %d\n", position);
        printf("Empid: %d\n", employees[position].empid);
        printf("Name: %s\n", employees[position].name);
        printf("Salary: %.2f\n", employees[position].salary);
    } else {
        printf("Employee not found.\n");
    }

    return 0;
}

```
**5. Define structure type employee with members: empid, name, post and bsalasy. Write a C program to print the record of the employee who has maximum salary.**  
```C
#include <stdio.h>

struct Employee {
    int empid;
    char name[50];
    float salary;
};

int main() {
    int n;
    printf("Enter the number of employees (up to 100): ");
    scanf("%d", &n);

    struct Employee employees[100];
    struct Employee maxSalaryEmployee;

    for (int i = 0; i < n; i++) {
        printf("Enter Employee %d details:\n", i + 1);
        printf("Empid: ");
        scanf("%d", &employees[i].empid);
        printf("Name: ");
        scanf("%s", employees[i].name);
        printf("Salary: ");
        scanf("%f", &employees[i].salary);

        if (i == 0 || employees[i].salary > maxSalaryEmployee.salary) {
            maxSalaryEmployee = employees[i]; 
        }
    }

    printf("Employee with Maximum Salary:\n");
    printf("Empid: %d\n", maxSalaryEmployee.empid);
    printf("Name: %s\n", maxSalaryEmployee.name);
    printf("Salary: %.2f\n", maxSalaryEmployee.salary);

    return 0;
}

```


# Lab Works 3: Pointer
**1. Write a program to swap two numbers using pointer.**  
```C
#include <stdio.h>

void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int num1, num2;
    printf("Enter two numbers: ");
    scanf("%d %d", &num1, &num2);

    printf("Before swapping: num1 = %d, num2 = %d\n", num1, num2);

    swap(&num1, &num2);

    printf("After swapping: num1 = %d, num2 = %d\n", num1, num2);

    return 0;
}

```
**2. Write a program using call by value and call by reference to swap two numbers.**  
```C
#include <stdio.h>

void swapByValue(int a, int b) {
    int temp = a;
    a = b;
    b = temp;
}

void swapByReference(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int num1, num2;
    printf("Enter two numbers: ");
    scanf("%d %d", &num1, &num2);

    printf("Before swapping by value: num1 = %d, num2 = %d\n", num1, num2);
    swapByValue(num1, num2);
    printf("After swapping by value: num1 = %d, num2 = %d\n", num1, num2);

    printf("Before swapping by reference: num1 = %d, num2 = %d\n", num1, num2);
    swapByReference(&num1, &num2);
    printf("After swapping by reference: num1 = %d, num2 = %d\n", num1, num2);

    return 0;
}

```
**3. Write a program to input 25 numbers and display them ascending order.**  
```C
#include <stdio.h>

int main() {
    int n = 25;
    int arr[n];

    printf("Enter %d numbers:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }

    printf("Numbers in ascending order:\n");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    return 0;
}

```
**4. Write a program to input 100 numbers and search a given number given by user.**  
```C
#include <stdio.h>

int main() {
    int n = 100;
    int arr[n];
    int target;

    printf("Enter %d numbers:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    printf("Enter the number to search: ");
    scanf("%d", &target);

    int found = 0;
    for (int i = 0; i < n; i++) {
        if (arr[i] == target) {
            printf("Number found at index %d\n", i);
            found = 1;
            break;
        }
    }

    if (!found) {
        printf("Number not found.\n");
    }

    return 0;
}

```
**5. Write a program to calculate the sum and the average of 10 numbers.**  
```C
#include <stdio.h>

int main() {
    int n = 10;
    int arr[n];

    printf("Enter %d numbers:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    int sum = 0;
    for (int i = 0; i < n; i++) {
        sum += arr[i];
    }

    float average = (float)sum / n;

    printf("Sum of the numbers: %d\n", sum);
    printf("Average of the numbers: %.2f\n", average);

    return 0;
}

```

# Lab Works 4: Working With Files
**1. Write a program to enter name, roll_no, and marks of 10 students and store them in the file.**   
```C
#include <stdio.h>

struct Student {
    char name[50];
    int roll_no;
    float marks;
};

int main() {
    FILE *file;
    struct Student students[10];

    printf("Enter data for 10 students:\n");
    for (int i = 0; i < 10; i++) {
        printf("Student %d:\n", i + 1);
        printf("Name: ");
        scanf("%s", students[i].name);
        printf("Roll No: ");
        scanf("%d", &students[i].roll_no);
        printf("Marks: ");
        scanf("%f", &students[i].marks);
    }

    file = fopen("student_data.txt", "w");

    for (int i = 0; i < 10; i++) {
        fprintf(file, "Name: %s\nRoll No: %d\nMarks: %.2f\n\n", students[i].name, students[i].roll_no, students[i].marks);
    }

    fclose(file);

    printf("Data written to file successfully.\n");

    return 0;
}

```
**2. Write a program to store empid, name and salary of 10 employees in a data file and display the records from file.**   
```C
#include <stdio.h>

struct Employee {
    int empid;
    char name[50];
    float salary;
};

int main() {
    FILE *file;
    struct Employee employees[10];

    printf("Enter data for 10 employees:\n");
    for (int i = 0; i < 10; i++) {
        printf("Employee %d:\n", i + 1);
        printf("Employee ID: ");
        scanf("%d", &employees[i].empid);
        printf("Name: ");
        scanf("%s", employees[i].name);
        printf("Salary: ");
        scanf("%f", &employees[i].salary);
    }

    file = fopen("employee_data.txt", "w");

    for (int i = 0; i < 10; i++) {
        fprintf(file, "Employee ID: %d\nName: %s\nSalary: %.2f\n\n", employees[i].empid, employees[i].name, employees[i].salary);
    }

    fclose(file);

    printf("Data written to file successfully.\n");

    file = fopen("employee_data.txt", "r");
    char ch;
    if (file) {
        while ((ch = fgetc(file)) != EOF) {
            printf("%c", ch);
        }
        fclose(file);
    } else {
        printf("File not found.\n");
    }

    return 0;
}

```
**3. Write a program using C language that reads successive records from new data file and displays each record on the screen in an appropriate format.**   
```C
#include <stdio.h>

int main() {
    FILE *file;
    char filename[50];

    printf("Enter the name of the data file: ");
    scanf("%s", filename);

    file = fopen(filename, "r");

    if (file) {
        char ch;
        while ((ch = fgetc(file)) != EOF) {
            printf("%c", ch);
        }
        fclose(file);
    } else {
        printf("File not found.\n");
    }

    return 0;
}

```
**4. Write a program to store std_id, name, and mark of 'n' students in a data file. Display the records in appropraite format reading from the file.**   
```C
#include <stdio.h>

struct Student {
    int std_id;
    char name[50];
    float marks;
};

int main() {
    FILE *file;
    int n;

    printf("Enter the number of students: ");
    scanf("%d", &n);

    struct Student students[n];

    printf("Enter data for %d students:\n", n);
    for (int i = 0; i < n; i++) {
        printf("Student %d:\n", i + 1);
        printf("Student ID: ");
        scanf("%d", &students[i].std_id);
        printf("Name: ");
        scanf("%s", students[i].name);
        printf("Marks: ");
        scanf("%f", &students[i].marks);
    }

    file = fopen("student_records.txt", "w");

    for (int i = 0; i < n; i++) {
        fprintf(file, "Student ID: %d\nName: %s\nMarks: %.2f\n\n", students[i].std_id, students[i].name, students[i].marks);
    }

    fclose(file);

    printf("Data written to file successfully.\n");

    file = fopen("student_records.txt", "r");
    char ch;
    if (file) {
        while ((ch = fgetc(file)) != EOF) {
            printf("%c", ch);
        }
        fclose(file);
    } else {
        printf("File not found.\n");
    }

    return 0;
}

```
**5. Write a program to enter name, roll_no, and marks of 10 students and store them in the file. Read and display the same from the file.**   
```C
#include <stdio.h>

struct Student {
    char name[50];
    int roll_no;
    float marks;
};

int main() {
    FILE *file;
    struct Student students[10];

    printf("Enter data for 10 students:\n");
    for (int i = 0; i < 10; i++) {
        printf("Student %d:\n", i + 1);
        printf("Name: ");
        scanf("%s", students[i].name);
        printf("Roll No: ");
        scanf("%d", &students[i].roll_no);
        printf("Marks: ");
        scanf("%f", &students[i].marks);
    }

    file = fopen("student_data.txt", "w");

    for (int i = 0; i < 10; i++) {
        fprintf(file, "Name: %s\nRoll No: %d\nMarks: %.2f\n\n", students[i].name, students[i].roll_no, students[i].marks);
    }

    fclose(file);

    printf("Data written to file successfully.\n");

    file = fopen("student_data.txt", "r");
    char ch;
    if (file) {
        while ((ch = fgetc(file)) != EOF) {
            printf("%c", ch);
        }
        fclose(file);
    } else {
        printf("File not found.\n");
    }

    return 0;
}

```
