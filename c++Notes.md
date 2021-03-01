## Syntax of code

Eg: Data types

```c
#include <iostream>
using namespace std;

int main()
{
char grade = 'A';
string phrase = "Giraffe Academy";
int age = 50;
float gpa = 9.3;
double = 4.3;     //Use double as default. Float is less used
bool isMale = TRUE;
return 0; //use this to indicate the successful completion of code if running on commandline. Read more here: https://stackoverflow.com/questions/20919733/what-is-the-significance-of-return-0-in-c-and-c
}
```
#### New Line

Below two lines gives the same results.
```c
cout << "Giraffe" << endl;
cout << "Giraffe \n";
```

#### strings

```c
int main ()
{
string phrase = "Giraffe Academy"
               //0123456789...
cout << phrase.length();    // Use "." followed by name of the function (Length here)
cout << phrase[0]; //print the first character
cout << phrase[0] = 'B'; //Substitute G with B
cout << phrase.find("Academy", 0) // search for index from where the word accademy occurs (which returns 8 here). 0 represents to start the search from the 0th index (i.e. starting of the string)
cout << phrase.substr(8,3)  // to grab a part of a string; requires the index position (say 8 here) and length of the substring that needs to be extracted (3 characters here).

}
```

#### Numbers

```c
#include <iostream>
#include <cmath>      // to do maths in C++

using namespace std;

int main ()
{
int wnum=5;
wnum += 80; // will print 5+80 and assign the number to wnum. You can do *=, -=, /= etc.
cout << "wnum";
cout << pow(2,5); // means 2 ki power 5
cout << sqrt(36); // square root of 36. Takes both integers and decimals.
cout << round(4.3);  // roundoff. another function ceil(4.3) will always round-up towards higher number i.e. 5 and floor(4.3) will always round-up towards a lower number (4 here).
cout << fmax(3,10);    // returns bigger number out of the two numbers
}
```

#### User Input

```c
int main ()
{
string name;
getline(cin, name);   // more efficient way to save the entire line in form of strings in C++ from console
}
```
#### Writing Functions

```c
// write a function block before the main() function block

void sayHi(string name, int age){   // giving function named sayHi two parameters
cout << "Hi "<< name << ". You are "<< age << " years old. \n";
}

int main {
sayHi("Rohit",24)
}
```

The above code will give error if you defined the function below main function. This is because compiler isn't aware about the newly written function yet. In case if you want to access the function from anywhere in the code, initialise the function first as follows

```c
// write initialisation before the main() function block

void sayHi(string name, int age);

int main {
sayHi("Rohit",24)
}

void sayHi(string name, int age){   // giving function named sayHi two parameters
cout << "Hi "<< name << ". You are "<< age << " years old. \n";
}

```

#### Return type

This is used when you wish to return values from a function. "return" is a special word and also tells c program that when encountered, the program must exit (or break) at that line and nothing below that is executed. And therefore it's preferentially mentioned at the end of the code. Eg:


```c
#include <iostream>
using namespace std;

double cube(double num){
return num * num * num;
cout << "Hello there!!";    // this line will never be printed because the return was encountered above it. So the code terminates above.
}

int main (){
cout << cube(5.0);
}
```

#### IF Else

```c
if(condition1 && condition2){}    //&& is for specifying two conditions are met
if(condition1 || condition2){}    //eitherof them is true
if(condition1 && !condition2){}     // ! mark  means condition2 is false
```

#### Switch

To see which number corresponds to which day. Use when you have lot of conditions to check beside if else statements.

```c
int daysOfWeek(int daynum){
string dayName;

switch(dayNam){
case 0:
dayName = "Sunday";
break;
case 1:
dayName = "Monday";

default:
dayName = "Invalid day Number"
}
return dayName;
}
```

#### 2D arrays

```c
int numGrid[3][2] = {
{1,2},
{3,4},
{5,6}
}

// [3][2] tells the number of rows andcolumns in array.
```

To write a block of comments enclose the lines as follows

```c

/* here I type comment
blah
blah

everything between these two tags are comment

*/
```

#### Call by reference

Access the address of a variable by using `&` beforeit

```c
int raja = 1

cout << &raja;

```

#### Pointer variable
The pointer variable stores the address of the variable

```c
int age = 19;
int *pAge = &age;   //usually we use small "p" before the name of pointer variable

```





