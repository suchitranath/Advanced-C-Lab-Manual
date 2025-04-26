## EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

# Aim: 
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

# Algorithm:
Declare structure eligible with age (integer) and n (character array)
Declare variable e of type eligible
Input age and name using scanf, store in e
If e.age <= 6
Print "Vaccine Eligibility: No" Else
Print "Vaccine Eligibility: Yes"
Print details (e.age, e.n)
Return 0

# Program:
```
#include <stdio.h>
struct eligible {
    int age;
    char n[50];
};

int main() {
    struct eligible e;

    printf("Enter name: ");
    scanf("%s", e.n);
    printf("Enter age: ");
    scanf("%d", &e.age);

    if(e.age <= 6) {
        printf("Vaccine Eligibility: No\n");
    } else {
        printf("Vaccine Eligibility: Yes\n");
    }
    return 0;
}

```

# Output:
![image](https://github.com/user-attachments/assets/12affb60-056c-4063-9361-1d44a5f780e8)

# Result: 
Thus, the program is verified successfully.

## EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION 

# Aim: 
To write a C program for passing structure as function and returning a structure from a function

# Algorithm:

Define structure numbers with members a and b.
Declare variable n of type numbers.
Prompt the user to enter values for a and b.
Input values for a and b into n using scanf.
Call the add function with n as an argument.
Print the result returned by the add function.
Return 0

# Program:
```
#include <stdio.h>
struct numbers {
    int a;
    int b;
};
struct numbers add(struct numbers n) {
    struct numbers result;
    result.a = n.a + n.b;  
    result.b = 0;          
    return result;
}

int main() {
    struct numbers n, res;
    printf("Enter two numbers:\n");
    scanf("%d %d", &n.a, &n.b);
    res = add(n);
    printf("Sum = %d\n", res.a);

    return 0;
}

```

# Output:
![image](https://github.com/user-attachments/assets/e58d37d7-c4ae-44d4-ad64-babc4040e1f8)

# Result: 
Thus, the program is verified successfully

## EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

# Aim: 
To write a C program to read a file name from user

# Algorithm:

Include the necessary header file stdio.h.
Begin the main function.
Declare a file pointer p. Declare a character array name to store the file name.
Prompt the user to enter a file name. Use scanf to input the file name into the name array.
Print a message indicating that the file with the specified name has been created successfully.
Use fopen to open a file with the name provided by the user in write mode ("w").
If successful, continue to the next step.
If unsuccessful, print an error message and exit the program with a non-zero status.
Print a message indicating that the file has been opened successfully.
Use fclose to close the file.
Print a message indicating that the file has been closed.
End the main function.
Return 0 to indicate successful program execution.

# Program:

![image](https://github.com/user-attachments/assets/29f16d85-1649-45cf-bb56-12f5ab7ec1e1)


//type your code here

# Output:

//paste your output here

# Result: Thus, the program is verified successfully

## EXP NO:4 PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE 

# Aim: To write a C program to read, a file and insert text in that file Algorithm:

# Algorithm
Include the necessary header file stdio.h.
Begin the main function.
Declare a file pointer p. Declare character arrays name and text. Declare an integer variable num.
Prompt the user to enter a file name and the number of strings. Use scanf to input the file name into the name array and the number of strings into the num variable.
Use fopen to open a file with the name provided by the user in write mode ("w").
If successful, continue to the next step.
If unsuccessful, print an error message and exit the program with a non-zero status.
Print a message indicating that the file has been opened successfully.
Use a loop to input strings from the user and write them to the file using fputs.
Use fclose to close the file.
Print a message indicating that data has been added successfully.
End the main function.
Return 0 to indicate successful program execution.

# Program:

//type your code here

# Output:

//paste your output here

# Result: 
Thus, the program is verified successfully

## Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

# Aim: 
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

# Algorithm: 
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

# Program:

//type your code here

# Output:

//paste your output here

# Result: 
Thus, the program is verified successfully
