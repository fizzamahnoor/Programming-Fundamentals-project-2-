# Programming-Fundamentals-project-2-

Question no1:
if Cout is greater than 10 print cout is greater thsb 10
#include <iostream >
using namespace std; 
int main()
{
int cout;
cout<<"enter cout:";
cin>>cout;
if(cout<10)
{
cout<<"cout is greater than 10";
}
}

Question no2:
write a code in C++ to find x raised to the power y using while loop.

Answer:

#include<iostream>
using namespace std;
int main()
{
int i=;
int x,y;
int power;
cout<<"enter base integer:";
cin>>x;
cout<<"enter power of integar:";
cin>>y;
while(i<=y)
{
power*=x;
i++;}
cout<<"x^y=";
cout<<power;
}

Question 3:
Identify and correct the errors in each of the following:

a) while ( c <= 5 )
{
 product *= c;
 ++c;
Error:
missing brace at the end
end
b) cin << value;

Error 
wrong << used

c) if ( gender == 1 )
 cout << "Woman" << endl;
else;
 cout << "Man" << endl;
Error 
semicolon after else

Question no4:

 What’s wrong with the following while repetition statement?

 while ( z >= 0 )
 sum += z;
Error 
condition will never be false for positive integars and infinite loop will be created 

Question no4:



