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


Question no 5:

 Dangling-else Problem

Values:

x = 9, y = 11 for part (a)

x = 11, y = 9 for part (b)




(a)

Code:

if ( x < 10 )
    if ( y > 10 )
        cout << "*****";
    else
        cout << "#####";

cout << "$$$$$";

Compiler pairs the else with the nearest if.

Given:

x = 9 → (x < 10) = true
y = 11 → (y > 10) = true

 flow:

x < 10 → true

y > 10 → true → print "*"

The final line cout << "$$$$$"; prints always.


Output (a):

*****
$$$$$




(b)

Code:

if ( x < 10 )
{
    if ( y > 10 )
        cout << "*****";
}
else
{
    cout << "#####";
    cout << "$$$$$";
}

Given:
x = 11 → (x < 10) = false
So the else block executes.

Output (b):

#####
$$$$$



Question no6:
Dangling-else Problem

You must insert braces only so the code produces each required output.

Original code:

if ( y == 8 )
    if ( x == 5 )
        cout << "@@@@";
    else
        cout << "####";
cout << "$$$$$";
cout << "&&&&&";



(a)

Required output:

@@@@
$$$$$
&&&&&

Given: x = 5, y = 8



Correct braced version:

if ( y == 8 ) {
    if ( x == 5 )
        cout << "@@@@";
    else
        cout << "####";
}
cout << "$$$$$";
cout << "&&&&&";




(b)

Required output:

@@@@

Given: x = 5, y = 8

Only @@@@ should print, and the other prints must be inside the else-block or suppressed.

Correct version:

if ( y == 8 ) {
    if ( x == 5 )
        cout << "@@@@";
}
else {
    cout << "####";
    cout << "$$$$$";
    cout << "&&&&&";
}



(c)

Required output:

@@@@
&&&&&

Given: x = 5, y = 8

Means:

print @@@@ from inner if

skip the middle $$$$$

but still print &&&&&


Correct version:

if ( y == 8 ) {
    if ( x == 5 )
        cout << "@@@@";
}
cout << "&&&&&";

(Remove middle print by enclosing it in discarded block. Only braces may be added.)



(d)

Required output:

#####
$$$$$
&&&&&

Given: x = 5, y = 7

Because y ≠ 8, the else must run, printing all three lines.

Correct version:

if ( y == 8 ) {
    if ( x == 5 )
        cout << "@@@@";
}
else {
    cout << "#####";
    cout << "$$$$$";
    cout << "&&&&&";
}



