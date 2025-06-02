EXP NO:1AC PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:
```
#include <stdio.h>
struct vacc
{
    char name[20];
    int age;
};
int main()
{
   struct vacc s;
   printf("ENTER THE NAME: ");
   scanf("%s",s.name);
   printf("ENTER THE AGE: ");
   scanf("%d",&s.age);
   printf("Vaccine Eligibility\n");
   if(s.age<=6)
   {
       printf("you are not eligible");
   }
   else
   {
       printf("you are eligible");
   }
}
```


Output:

![image](https://github.com/user-attachments/assets/3dbeeb92-3662-4bde-a991-ee097664e5b2)




Result:
Thus, the program is verified successfully. 



EXP NO:1B C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program: 
```
#include <stdio.h>
struct Student {
    int id;
    char name[50];
    float marks;
};
void displayStudent(struct Student s) {
    printf("Student Details:\n");
    printf("ID: %d\n", s.id);
    printf("Name: %s\n", s.name);
    printf("Marks: %.2f\n", s.marks);
}
struct Student inputStudent() {
    struct Student s;
    printf("Enter student ID: ");
    scanf("%d", &s.id);
    printf("Enter student name: ");
    scanf(" %[^\n]", s.name);
    printf("Enter student marks: ");
    scanf("%f", &s.marks);
    return s;
}

int main() {
    struct Student s1;
    s1 = inputStudent();
    displayStudent(s1);

    return 0;
}
```


Output:

![image](https://github.com/user-attachments/assets/e4ef8fd6-6075-426b-826a-1e53fe7678f2)





Result:
Thus, the program is verified successfully


 
EXP.NO:1C C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
```
#include <stdio.h>

int main() {
    char filename[100];
    FILE *file;
    scanf("%s", filename);
    
    file = fopen(filename, "w");
    
    if (file == NULL) {
        printf("Error opening file!\n");
        return 1;
    }
    
    printf("%s File Created Successfully\n", filename);
    printf("%s File Opened\n", filename);
    
    fclose(file);
    printf("%s File Closed\n", filename);
    
    return 0;
}
```


Output:

![image](https://github.com/user-attachments/assets/3052d511-14ec-4e10-9cef-c280b7e15372)


Result:
Thus, the program is verified successfully
 


EXP NO:1D  PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
```
#include <stdio.h>

int main() {
    char filename[100];
    FILE *file;
    int n;
    float value;
    scanf("%s", filename);
    
    file = fopen(filename, "w");
    
    if (file == NULL) {
        printf("Error opening file!\n");
        return 1;
    }
    
    printf("%s Opened", filename);
    scanf("%d", &n);
    
    for (int i = 0; i < n; i++) {
        scanf("%f", &value);
        fprintf(file, "%.2f\n", value);
    }
    
    fclose(file);
    printf("\nData added Successfully\n");

    
    return 0;
}
```


Output:

![image](https://github.com/user-attachments/assets/eb0d4f8c-93fc-4fa0-91a1-c691e258b2f1)




Result:
Thus, the program is verified successfully



Ex No !E: C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
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

Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Subject
{
    char name[20];
    int marks;
};
int main()
{
    int i,n;
    scanf("%d",&n);
    struct Subject *s = (struct Subject *)malloc(n*sizeof(struct Subject));
    if(s==NULL)
    {
        printf("Memory Alocation Failed\n");
        return 1;
    }
    for(i=0;i<n;i++)
    {
        scanf("%s %d",s[i].name,&s[i].marks);
    }
    for(i=0;i<n;i++)
    {
        printf("%s  %d\n",s[i].name,s[i].marks);
    }
    
    free (s);
    
    return 0;
}
```



Output:

![image](https://github.com/user-attachments/assets/634b13a3-c038-4cd9-98fd-b5f3b9d21157)



Result:
Thus, the program is verified successfully
