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

#### Length of strings

```
int main ()
{
string phrase = "Giraffe Academy"
cout << phrase.length();    // Use "." followed by name of the function (Length here)

}
```
