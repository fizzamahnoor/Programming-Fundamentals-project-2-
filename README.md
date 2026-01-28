# Programming-Fundamentals-Fizza Mahnoor-2582

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
}


loops:


Question no1:


(a) 
Sum the odd integers between 1 and 99 using a for statement. (Assume sum and count declared.)
Code + result:

int sum = 0;
int count = 0;
for (int i = 1; i <= 99; i += 2) {
    sum += i;
    ++count;
}
 sum == 2500, count == 50

Printed result: sum = 2500 (there are 50 odd numbers from )


(b)
 Print integers from 1 to 20 using a while loop and counter variable x. (Hint about printing newline when x % 5 == 0.)
Important: if x was declared but not initialized, you must initialize it. Correct code:

int x = 1;                
while (x <= 20) {
    cout << x;
    if (x % 5 == 0)
        cout << '\n';
    else
        cout << '\t';
    ++x;
}


(c) 

Repeat (b) using a for statement:

for (int x = 1; x <= 20; ++x) {
    cout << x;
    if (x % 5 == 0)
        cout << '\n';
    else
        cout << '\t';
}



Question no2:
Find the errors in the code segments and explain how to correct them

(a) Given (incorrect) fragment:

x = 1;
while ( x <= 10 );
    x++;
}

Errors & fixes:

The semicolon after while (...) makes the loop body empty.

Extra closing brace } is stray.

x should be declared (e.g. int x = 1;). Correct version (to print 1..10):


int x = 1;
while (x <= 10) {
    cout << x << ' ';
    ++x;
}




(b)

for ( y = .1; y != 1.0; y += .1 )
    cout << y << endl;

Errors & explanation:

Using floating-point equality y != 1.0 is unsafe (floating rounding error may skip or never hit exactly 1.0).

y = .1 should be 0.1 (style), and y should be declared (e.g. double y). Correct approach: iterate an integer loop and compute y from the integer:


for (int i = 1; i <= 10; ++i) {
    double y = i / 10.0;
    cout << y << endl;
}

This reliably prints 0.1, 0.2, …, 1.0.



(c)

switch ( n ) {
case 1:
    cout << "The number is 1" << endl;
case 2:
    cout << "The number is 2" << endl;
    break;
default:
    cout << "The number is not 1 or 2" << endl;
    break;
}

Error: missing break; at end of case 1: execution will fall through to case 2.
Fix: add break; after case 1's statement:

case 1:
    cout << "The number is 1" << endl;
    break;




(d) 

n = 1;
while ( n < 10 )
    cout << n++ << endl;

Error: condition n < 10 prints 1..9, not 1..10.
Fix: use while (n <= 10):

int n = 1;
while (n <= 10)
    cout << n++ << endl;
________

Question no 3:



 Find the errors

a) 
Given (rough form):
For ( x = 100, x >= 1, x++ ) cout << x << endl;

Errors 

Keyword must be lowercase for.

for-statement parts are separated by semicolons ; not commas ,.

If you start at 100 and want to count down to 1 the increment should be x-- (not x++).

x should be declared (e.g. int x;).


Correct:

for (int x = 100; x >= 1; x--)
    cout << x << endl;




b) 
Given (rough):

switch ( value % 2 )
{
  case 0:
    cout << "Even integer" << endl;
  case 1:
    cout << "Odd integer" << endl;
}

Errors 

Missing break; after each case so both branches would run.

Optionally use default: though not necessary here.


Correct:

switch ( value % 2 ) {
  case 0:
    cout << "Even integer" << endl;
    break;
  case 1:
    cout << "Odd integer" << endl;
    break;
}



c) 
Given (rough):
for ( x = 19; x >= 1; x += 2 ) cout << x << endl;

Errors 

If you want odd integers from 19 down to 1, the update should subtract 2 (x -= 2) not add 2.

Declare x (e.g. int x).


Correct:

for (int x = 19; x >= 1; x -= 2)
    cout << x << endl;



d)
 Given (rough):

counter = 2;
do
{
  cout << counter << endl;
  counter += 2;
} While ( counter < 100 );

Errors 

while should be lowercase.

Condition: to include 100 in output we should test counter <= 100.

The do-while needs a semicolon after closing while


Correct:

int counter = 2;
do {
    cout << counter << endl;
    counter += 2;
} while (counter <= 100);

____________

Question no 4

(Summing Integers)

Problem: first integer read specifies number of values remaining; sum those values. Example input: 5 100 200 300 400 500 (5 indicates next 5 values should be summed).

Solution (C++):

#include <iostream>
using namespace std;

int main() {
    int n;
    if (!(cin >> n)) return 0;             number of values to sum
    int sum = 0, value;
    for (int i = 0; i < n; ++i) {
        cin >> value;
        sum += value;
    }
    cout << "Sum = " << sum << endl;
    return 0;
}

_________

Question no 5:

(Averaging Integers)

Problem: Use a for-style approach to compute average of several integers where last value is sentinel 9999 (which should not be included). Example input: 10 8 11 7 9 9999.

Solution (C++):

#include <iostream>
using namespace std;

int main() {
    int value;
    int sum = 0;
    int count = 0;

    while (cin >> value && value != 9999) {
        sum += value;
        ++count;
    }

    if (count > 0)
        cout << "Average = " << static_cast<double>(sum) / count << endl;
    else
        cout << "No values entered." << endl;

    return 0;
}




___________

Question no6:

 What does the program print?


for (int i = 1; i <= y; i++) {
    for (int j = 1; j <= x; j++)
        cout << '@';
    cout << endl;
}

@@@@
@  @
@  @
@@@@


__________
Questionno 7:
(Find the Smallest Integer)

Problem: First value read specifies the number of values to be entered. Find the smallest of them.

Solution :

#include <iostream>
#include <limits>
using namespace std;

int main() {
    int n;
    if (!(cin >> n) || n <= 0) {
        cout << "Invalid count" << endl;
        return 0;
    }

    int value, smallest;
    cin >> smallest; // read first value
    for (int i = 1; i < n; ++i) {
        cin >> value;
        if (value < smallest) smallest = value;
    }

    cout << "Smallest = " << smallest << endl;
    return 0;
}


______________

Question no 7:
(Product of Odd Integers)

Problem: Compute the product of the odd integers from 1 to 15.

Solution :

#include <iostream>
using namespace std;

int main() {
    long long product = 1;
    for (int i = 1; i <= 15; i += 2)
        product *= i;
    cout << "Product of odd integers 1..15 = " << product << endl;
    return 0;
}

Result: product = 1*3*5*7*9*11*13*15 = 2027025 



______________
Question no 8:
(Factorials)

Problem: Use a for to evaluate factorials of integers from 1 to 5 and print in tabular format. (Also mentions difficulty calculating factorial of 20 — overflow in typical 32-bit int.)

Solution :

#include <iostream>
using namespace std;

int main() {
    cout << "n\tfactorial\n";
    unsigned long long factorial = 1;
    for (int n = 1; n <= 20; ++n) {
        factorial *= n;
        cout << n << '\t' << factorial << 
}






