
# C++ Codes MSc. Bioinformatics Ist-Sem

1. **Calculate the area of circle**

```c
//Area of the circle
#include <iostream>

using namespace std;

class CircleArea{
  private:
  double area;
  
 
  public:
  int radius;
  void inputRadius(){
      cout<<"Please Enter Radius of circle";
    cin>>radius;
    
  }
  
  void calculateArea(){
      area=3.14*radius*radius;
      cout<<"Area of Circle is: "<<area;
  }
    
};

int main()
{
    CircleArea circleArea;
    circleArea.inputRadius();
    circleArea.calculateArea();

    return 0;
}
```
2. **Check Gender**

```c
//Check whether a person is male or female
#include <iostream>

using namespace std;

class CheckGender{
    private:
    string gender;
    
    public:
    string ch;
    void inputCharacter(){
        cout<<"Please enter gender as M/F";
        cin>>ch;
    }
    
    void displayGender(){
        if(ch=="m" || ch=="M"){
            gender="Male";
            cout<<"You have selected: "<<gender;
        }
        else if(ch=="f" || ch=="F"){
            gender="Female";
            cout<<"You have selected: "<<gender;
        }
        else{
            cout<<"You have entered invalid character";
        }
        
            }
};

int main()
{
    
    CheckGender checkGender;
    checkGender.inputCharacter();
    checkGender.displayGender();
    return 0;
}
```
3. **Check Vowel**

```c
//Check Vowel Using Switch Case
#include <iostream>

using namespace std;

class CheckVowel
{
  
  private:
  char chk;
  
  public:
  char ch;
  void input(){
      cout<<"Enter a letter to check: ";
      cin>>ch;
      chk=ch;
  }
  
  void check()
  {
      switch (chk) 
    { 
        case 'a':  
            cout << "You entered ["<<chk<<"] which is a vowel"; 
            break; 
        case 'e':  
            cout <<  "You entered ["<<chk<<"] which is a vowel";
            break; 
        case 'i':  
            cout <<  "You entered ["<<chk<<"] which is a vowel";
            break; 
        case 'o':  
            cout <<  "You entered ["<<chk<<"] which is a vowel";
            break; 
        case 'u':  
            cout <<  "You entered ["<<chk<<"] which is a vowel";
            break; 
        
        default:  
            cout << "You entered ["<<chk<<"] which is a consonant"; 
            break;   
    } 
  }
};

int main()
{
   CheckVowel vowel;
   vowel.input();
   vowel.check();

    return 0;
}
```
4. **Display Name**

```c
//Display Name on screen
#include <iostream>

using namespace std;

class DisplayName{
  private:
  string privateName;
 
  public:
  string name;
  void inputName(){
      cout<<"Please Enter your name";
    cin>>name;
    privateName=name;
  }
  
  void display(){
      cout<<"Hello, I am "<<privateName;
  }
    
};

int main()
{
    DisplayName displayName;
    displayName.inputName();
    displayName.display();

    return 0;
}
```
5. **Calculate salary**

```c
#include <iostream>

using namespace std;
class CalculateSalary{
    private: 
    double salary;
    double hra;
    
    public:
    int basicSal;
    void inputBasicSalary(){
        cout<<"Please enter basic salary: ";
        cin>>basicSal;
    }
    
    void totalSalary(){
        if(basicSal>20000){
            salary=basicSal*1.02;
            hra=basicSal*0.02;
        }
        else{
            salary=basicSal*1.012;
            hra=basicSal*0.012;
        }
        
        cout<<"Total Salary including HRA is: "<<salary<<" and HRA is: "<<hra;
    }
};

int main()
{
    CalculateSalary calculateSalary;
    calculateSalary.inputBasicSalary();
    calculateSalary.totalSalary();
  
    return 0;
}
```
6. **Simple Interest**

```c

//Find Simple Interest
#include <iostream>

using namespace std;

class SimpleInterest{
  private: 
  double interest;
  
  public:
  int principal,years,rate;
  
  void enterValues() {
      cout<<"Program to calculate Simple Interest "<<endl;
     cout<<"Please enter Principal: ";
      cin>>principal;
      cout<<"Please enter Years: ";
      cin>>years;
    
      cout<<"Please enter Rate of Interest: ";
      cin>>rate;
  }
  
  void calculateInterest(){
      interest=(principal*rate*years)/100;
      cout<<"Simple Interest of Entered values is:Rs "<<interest;
  }
    
};



int main()
{
    SimpleInterest simpleInterest;
    simpleInterest.enterValues();
    simpleInterest.calculateInterest();
    return 0;
}
```

6. **WAP to print 1 to 100**

```c
#include<iostream>
using namespace std;
 class sequence
 {
     private:
     int i=1;
     public:
     void input();
     void output();
 };
 void sequence::input(){
     
 }

 void sequence::output()
 {
while(i<=100)
{
    cout<<"\t"<<i;
    i++;

}
 }
int main()
 {
     sequence(x);
     x.input();
     x.output();
 }
 ```
 7. **Display even number from 1 - 50 & find its sum.**
 
 ```c
 #include<iostream>
using namespace std;
 class even
 {
     private:
     int i=2,sum=0;
     public:
     void input();
     void output();
 };
 void even::input(){
     
 }

 void even::output()
 {
while(i<=50)
{
    cout<<"\t"<<i;
    i=i+2;
    sum=sum+i;
}
 cout<<"sum:"<<sum;
 }
int main()
 {
     even(x);
     x.input();
     x.output();
 }
 ```
 8. **Display odd number from 1 - 50 & find its sum.**
 
 ```c
 #include<iostream>
using namespace std;
 class odd
 {
     private:
     int i=1,sum=0;
     public:
     void input();
     void output();
 };
 void odd::input(){
     
 }

 void odd::output()
 {
for(i=1;i<=50;i=i+2)
{
    cout<<"\t"<<i;
    i=i+2;
    sum=sum+i;
}
 cout<<"sum:"<<sum;
 }
int main()
 {
     odd(x);
     x.input();
     x.output();
 }
 ```
 9. **Find root of quadratic equation**
 
 ```c
 #include <iostream>
#include <cmath>
using namespace std;
class roots {
    private:
    int a, b, c, d, r1, r2;
    public: 
    void input();
    void output();
};
void roots::input() {
    cout << "Standard form of quadratic equation is:\n";
    cout << "ax^2 + bx + c = 0\n";
    cout << "where a, b, c are known numbers and a != 0\n\n";
    
    cout << "Enter a: ";
    cin >> a;
    
    cout << "Enter b: ";
    cin >> b;
    
    cout << "Enter c: ";
    cin >> c;
}
void roots::output() {
     d = (b*b) - 4*a*c;
    if (d > 0) {
        cout << "It has two real roots:\n";
        r1 = (-b + sqrt(d)) / 2*a;
        r2 = (-b - sqrt(d)) / 2*a;
        cout << "First root: " << r1;
        cout << "\nSecond root: " << r2;
    }
    else if (d == 0) {
        cout << "It has one real root.\n";
        r1 = -b / 2*a;
        cout << "Root: " << r1;
    }
    else if (d < 0) {
        cout << "It has no real roots";
    }
    else {
        cout << "Enter valid numbers";
    }
}
int main () {
    roots q;
    q.input();
    q.output();
}
```
10. **Find sequence of a protein as given below:  
            C = ccttaattaattccat
            A = attcttcttc
            T = ttatccta by entering a character. (switch case)**
```c
 #include <iostream>
using namespace std;
class protein {
    private:
    char letter;
    public: 
    void switchcase();  //I named the function switchcase
};
void protein::switchcase() {
    cout << "Enter a letter: ";
    cin >> letter;
    switch (letter) {
        case 'c':
        case 'C': cout << "The protein sequence is: ccttaattaattccat";
        break;
        case 'a':
        case 'A': cout << "The protein sequence is: attcttcttc";
        break;
        case 't':
        case 'T': cout << "The protein sequence is: ttatccta";
        break;
        default: cout << "ERROR: Enter an appropriate character.";
    }
}
int main () {
    protein q;
    q.switchcase();
}
```
11. **Generate number from 1 - 100 using do/while loop.**

```c
#include <iostream>
using namespace std;
class numbers {
    private:
    int i;
    public: 
    void no();
};
void numbers::no() {
    i = 1;
    do {
        cout << i << "\t";
        i++;
    }
    while (i <= 100);
}
int main () {
    numbers n;
    n.no();
}

```
12. **Generate numbers from 1 - 100 without using a loop**

```c
#include <iostream>
using namespace std;
class numbers {
    private:
    int i;
    public: 
    void no();
};
void numbers::no() {
    i = 1;
    x:
    cout << i << "\t";
    i++;
    if (i <= 100) {
        goto x;
    }
}
int main () {
    numbers n;
    n.no();
}
```
13. **Calculate electricity bill of a consumer with the following condition:**
-	Unit less than 200. Price is Rs. 1.5  per unit.
-	Unit greater than 200 and less than 400. Price is Rs. 4 per unit.
-	Unit greater than 400 and less than 900. Price is Rs. 6 per unit.

```c
#include <iostream>
using namespace std;
class elecBill {
    private:
    int units;
    float bill;
    public: 
    void input();
    void output();
};
void elecBill::input() {
    cout << "Enter units of electricity consumed: ";
    cin >> units;
}
void elecBill::output() {
    if (units <= 200) {
        cout << "\nFor the units consumed by you, rate of 1 unit electricity is: Rs. 1.5\n";
        bill = 200 * 1.5;
        cout << "\nYour electricity bill is Rs. " << bill;
    }
    else if (units > 200 && units <= 400) {
        cout << "\nFor the units consumed by you, rate of 1 unit electricity is: Rs. 4\n";
        bill = 200 * 4;
        cout << "\nYour electricity bill is Rs. " << bill;
    }
    else if (units > 400 && units <= 900) {
        cout << "\nFor the units consumed by you, rate of 1 unit electricity is: Rs. 6\n";
        bill = 200 * 6;
        cout << "\nYour electricity bill is Rs. " << bill;
    }
    else {
        cout << "\nERROR: Enter valid amount";
    }
}
int main () {
    elecBill n;
    n.input();
    n.output();
}
```
14. **Swap two characters**

```c
#include<iostream>
using namespace std;
class swp
{
    private:
    char a,b,c;
    public:
    void inputz();
    void outputz();
};
void swp::inputz()
{
cout<<"enter value of a,b=";
cin>>a>>b;
cout<<"After swaping:\n";
}
void swp::outputz()
{
c=a;
a=b;
b=c;
cout<<"a="<<a<<"\n";
cout<<"b="<<b;
}
int main()
{
swp o;
o.inputz();
o.outputz();
}
```
15. **Area of Rectangle**

```
#include<iostream>
using namespace std;
class rectangle
{
    private:
    int l,b,a;
    public:
    void inputz();
    void outputz();
};
void rectangle::inputz()
{
cout<<"enter value of l and b=";
cin>>l>>b;
}
void rectangle::outputz()
{
a=l*b;
cout<<"area of rectangle="<<a;
}
int main()
{
rectangle o;
o.inputz();
o.outputz();
}
```
16. **Area of Circle**

```c
#include<iostream>
using namespace std;
class circle
{
    private:
    float r,a;
    public:
    void inputz();
    void outputz();
};
void circle::inputz()
{
cout<<"enter value of r=";
cin>>r;
}
void circle::outputz()
{
a=3.14*r*r;
cout<<"area of circle="<<a;
}
int main()
{
circle o;
o.inputz();
o.outputz();
}
```
17. **Swap two variables**

```c
#include<iostream>
using namespace std;
class exchange
{
    private:
    int a,b,e;
    public:
    void inputz();
    void outputz();
};
void exchange::inputz()
{
cout<<"enter value of a,b=";
cin>>a>>b;
}
void exchange::outputz()
{
e=a;
a=b;
b=e;
cout<<"a:"<<a<<"\t";
cout<<"b:"<<b;
}
int main()
{
exchange o;
o.inputz();
o.outputz();
}
```
18. **Swap two variables without the third variable**

```c
#include<iostream>
using namespace std;

class swp
{
    private:
    int a,b;
    public:
    void inputz();
    void outputz();
};
void swp::inputz()
{
cout<<"enter value of a,b=";
cin>>a>>b;
cout<<"After swaping:\n";
}
void swp::outputz()
{
a=a+b;
b=a-b;
a=a-b;
cout<<"a="<<a<<"\n";
cout<<"b="<<b;
}
int main()
{
swp o;
o.inputz();
o.outputz();
}
```
19. **Square of a number**

```c
#include<iostream>
using namespace std;
class square
{
    private:
    int a,s;
    public:
    void inputz();
    void outputz();
};
void square::inputz()
{
cout<<"enter value of a=";
cin>>a;
}
void square::outputz()
{
s=a*a;
cout<<"square="<<s;
}
int main()
{
square o;
o.inputz();
o.outputz();
}
```
20. **Sum of 2 numbers**

```c
#include<iostream>
using namespace std;
class swp
{
    private:
    int a,b,s;
    public:
    void inputz();
    void outputz();
};
void swp::inputz()
{
cout<<"enter value of a,b=";
cin>>a>>b;
}
void swp::outputz()
{
s=a+b;
cout<<"sum="<<s;
}
int main()
{
swp o;
o.inputz();
o.outputz();
}
```
21. **Product of 3 numbers**

```c
#include<iostream>
using namespace std;
class prod
{
    private:
    int a,b,c,p;
    public:
    void inputz();
    void outputz();
};
void prod::inputz()
{
cout<<"enter value of a,b,c=";
cin>>a>>b>>c;
}
void prod::outputz()
{
p=a*b*c;
cout<<"product="<<p;
}
int main()
{
prod o;
o.inputz();
o.outputz();
}
```
22. **WAP in c++ to enter the 4 protien, to store its biological name, protien symbol and sequence**
```c
#include <iostream>

using namespace std;

class Mat{
    
    private:
        string arr[6][4];
        int i, j;
    
    public:
        void data();
};

void Mat::data(){
    int newLength=0;
    string newSeq;
    
    cout<<"Enter the elements of the array"<<endl;
    for(int i=0; i<3; i++){
        for(int j=0; j<3; j++){
            cin>>arr[i][j];
        }
    }
    cout<<"Elements of the array in tabular form: "<<endl;
    for(i=0; i<3; i++){
        for(j=0; j<3; j++){
            cout<<arr[i][j]<<"\t";
        }
         cout<<endl;
         string str = arr[i][2];
         newSeq = newSeq + str;
         newLength = newLength + str.length();
    }
    cout<<"New Sequence is : "<<newSeq<<endl<<"Length of new sequence is : "<<newLength<<endl;
}

int main()
{
    Mat m;
    m.data();

    return 0;
}
```
23. **WAP in c++ to enter the 4 protien, to store its biological name, protien symbol and sequence using unstructured programing**
```c
#include <iostream>

using namespace std;

class Proteins
{
  
  public:
  string protein[5][3];
  void enterData() 
  {
      
      for(int i=0;i<5;i++)
    
        {   
            int num=(i+1);;
             cout<<"Enter Protein "<<num<<" details"<<endl;
        
            for(int j=0;j<3;j++)
                {
                    if(protein[i][j]==protein[i][0])
                    {
                     cout<<"Enter Protein's Name"<<endl;
                     cin>>protein[i][j];
                    }
            
                    else if(protein[i][j]==protein[i][1])
                     {
                          cout<<"Enter Protein's Symbol"<<endl;
                          cin>>protein[i][j];
                     }
            
                    else if(protein[i][j]==protein[i][2])
                    {
                        cout<<"Enter Protein's Sequence"<<endl;
                        cin>>protein[i][j];
                    }
            
          
                    
                    else
                    { 
                        continue; 
                        
                    }
            
        }
    }
  }
   
    void displayData()
    {
         for(int i=0;i<5;i++)
         {
             int num2=(i+1);
                for(int j=0;j<3;j++)
           {
             if(protein[i][j]==protein[i][0])
             {
                cout<<protein[i][j]<<"\t";
             }
            
           else if(protein[i][j]==protein[i][1])
            {
                cout<<protein[i][j]<<"\t";
            }
            
            else if(protein[i][j]==protein[i][2])
            {
                cout<<protein[i][j]<<"\t\n";
            }
            
           
            else
            { continue; 
                
            }
        }
                
    }
    
  
    }  
};

 int main(){
     Proteins ptn;
     cout<<"Please enter details of 3 Proteins"<<endl;
     ptn.enterData();
      cout<<"\n";
    cout<<"The data entered is as follows:\n";
    cout<<"-----------------------------------\n";
    cout<<"PROTEIN NAME\tSYMBOL\tSEQUENCE\t"<<endl;
    cout<<"------------------------------------"<<endl;
    ptn.displayData();
    
    return 0;
}

25. WAP to measure the length of the aminoacid sequence stored in multi-dimensional array
```c
#include <iostream>
#include <string.h>
using namespace std;
class mat {
    private:
    string a[5][3];
    int i, j, len1, len2, len3, len4, len5, len6;
    string h1, h2, h3, h4, h5, h6;
    public:
    void data();
};
void mat::data() {
    cout << "Enter data of a table:";
    for (i = 0; i < 5; i++) {
        for (j = 0; j < 3; j++) {
            cin >> a[i][j];
        }
    }
    for (i = 0; i < 5; i++) {
        for (j = 0; j < 3; j++) {
            cout << a[i][j] << "\t";
        }
        cout << "\n";
    }
    h1 = a[0][2];
    len1 = h1.length();
    cout << "\nLength of first protein sequence is: " << len1 << "\n";
    h2 = a[1][2];
    len2 = h2.length();
    cout << "\nLength of second protein sequence is: " << len2 << "\n";
    h3 = a[2][2];
    len3 = h3.length();
    cout << "\nLength of third protein sequence is: " << len3 << "\n";
    h4 = a[3][2];
    len4 = h4.length();
    cout << "\nLength of fourth protein sequence is: " << len4 << "\n";
    h5 = a[4][2];
    len5 = h5.length();
    cout << "\nLength of fifth protein sequence is: " << len5 << "\n";
    h6 = a[5][2];
    len6 = h6.length();
    cout << "\nLength of sixth protein sequence is: " << len6 << "\n";
}
int main () {
    mat x;
    x.data();
}
```
24. **Percentage of A,T,G,C content & merge two sequence and calculate length of merged sequence** 
 ```c
 #include <iostream>
#include <string.h>
using namespace std;
class nmerge {
    private:
    char seq1[5];
     float  len;
    char seq2[5];
   
    char i;
   
    float t =0; float  a = 0;float g = 0, c = 0;
    public:
    void seqmerge ();
};
void nmerge::seqmerge ()
{
  cout << "Enter first sequence: ";
  cin>>seq1;
  cout << "Enter second sequence: ";
  cin>>seq2;
strcat (seq1,seq2);
 cout << "Merged sequence: " << seq1<< "\n";
   len=strlen(seq1);
  cout << "length of merged sequence: " << len<<endl;
  
  for (i=0; i < 10; i++) {
      if (seq1[i] == 't') {
          t = t + 1;
      }
      else if (seq1[i] == 'a') {
          a = a + 1;
      }
      else if (seq1[i] == 'c') {
          c = c + 1;
      }
      else if   (seq1[i] == 'g') {
          g = g + 1;
      }
  }
      cout << "Number of t in the merged sequence: " << t << "\n";
      cout << "Number of a in the merged sequence: " << a << "\n";
      cout << "Number of g in the merged sequence: " << g << "\n";
      cout << "Number of c in the merged sequence: " << c << "\n";
      
      int percentT, percentA, percentG, percentC;
      percentT = (t/10) * 100;
      cout << "Percent of t is: " << percentT << "\n";
      percentA = (a/10) * 100;
      cout << "Percent of a is: " << percentA << "\n";
      percentG = (g/10) * 100;
      cout << "Percent of g is: " << percentG << "\n";
      percentC = (c/10) * 100;
      cout << "Percent of c is: " << percentC << "\n";
}
int main()
{
  nmerge  x;
  x.seqmerge ();
  return 0;
}
```
25. Calculate the division of students based on marks entered
```c
#include <iostream>

using namespace std;
class Marks{
  private:
  int numbers[10];
  
  public:
  float percentage;
  void input();
  void output();
  };
  
  void Marks::input() {
      float sum=0;
      cout<<"Take 10 marks as input"<<endl;
      for (int i = 0; i < 10; ++i) {
        cin >> numbers[i];
        sum=sum+numbers[i];
      }
    percentage=(sum/1000)*100;
  }
  void Marks::output (){
      if(percentage>=70)
      {
          cout<<"first division with distinction";
      }
      else if (percentage >=60 && percentage  <=70)
      {
          cout<<"first division";
      }
      else if (percentage <=45 && percentage>=33)
      {
          cout<<"third division";
      }
      else
      {cout<<"fail";
      }
  }
  
 int main(){
      Marks m;
      m.input();
      m.output();
  }
  ```
26. **Sum of First 100 numbers** 
```c
#include <iostream>
using namespace std;
class TotalSum
{
    
    public:
    
    void display(){
        int sum=0;
        for(int i=1;i<=100;i++){
            sum+=i;
        }
        
        cout<<"Sum of First 100 numbers is: "<<sum;
    }
};

int main()
{
    TotalSum s;
    s.display();
    return 0;
}
```



