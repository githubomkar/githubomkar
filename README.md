EXPERMENT-01
AIM: PROGRAM ON TAKING INPUT FROM USER

import java.util.Scanner;
class Arms
{
public static void main(String[]args)
{
int temp,rem,num,sum=0;
Scanner sc=new Scanner(System.in);
System.out.println("enter a number;");
num=sc.nextInt();
temp=num;
while(num!=0)
{
num=num%10;
sum=sum+(num*num*num);
num=num/10;
}
if(temp==sum)
{System.out.println("armstrong number");
}
else
{
System.out.println("not armstrong number");
}
}
}
OUTPUT:
enter a number;
78
not armstrong number












EXPERIMENT-2
AIM: PROGRAM ON CLASS & OBJECT

import java.util.*;
class Box
{
int length;
int breadth;
int height;
}
class Cube
{
int side;
}
class Sphere
{
int radius;
}
class volume
{
public static void main(String[]args)
{
Scanner v= new Scanner(System.in);
Box b=new Box();
System.out.println("enter length,breadth,height:");
b.length=v.nextInt();
b.breadth=v.nextInt();
b.height=v.nextInt();
int vob=b.length*b.breadth*b.height;
System.out.println("volume of Box is,"+vob);
Cube c=new Cube();
System.out.println("enter side:");
c.side=v.nextInt();
int voc=c.side*c.side*c.side;
System.out.println("volume of Cube is,"+voc);
Sphere s=new Sphere();
System.out.println("enter radius:");
s.radius=v.nextInt();
double vos=4.0/3.0*3.14*s.radius*s.radius*s.radius;
System.out.println("volume of Sphere is,"+vos);
}
}
OUTPUT:
enter length,breadth,height:
85 67 34
volume of Box is,193630
enter side:
63
volume of Cube is,250047
enter radius:
89
volume of Sphere is,2951470.213333334




Experiment-3A
AIM: PROGRAM ON CONSTRUCTOR OVERLOADING

import java.util.*;
class Rect
{
int length;
int breadth;
Rect()
{
System.out.println("constructor with no parameter");
length=breadth=0;
}
Rect(int side)
{
System.out.println("constructor with one parameter");
length=breadth=side;
}
Rect(int l,int b)
{
System.out.println("constructor with two parameters");
length=l;
breadth=b;
}
int display()
{
return(length*breadth);
}
}
class Constructor
{
public static void main(String[]args)
{
Rect r1=new Rect();
System.out.println("Area of the rectangle"+r1.display());
Rect r2=new Rect(5);
System.out.println("Area of the rectangle"+r2.display());
Rect r3=new Rect(7,8);
System.out.println("Area of the rectangle"+r3.display());
}
}
OUTPUT:
constructor with no parameter
Area of the rectangle0
constructor with one parameter
Area of the rectangle25
constructor with two parameters
Area of the rectangle56





EXPERIMENT-3B
AIM: PROGRAM ON METHOD OVERLOADING
import java.util.*;
class Adder
{
void add(int a, int b)
{
int sum=a+b;
System.out.println("sum of two integers="+sum);
}
void add(int a, int b, int c)
{
int sum=a+b+c;
System.out.println("sum of three integers="+sum);
}
void add(float a, float b)
{
float sum=a+b;
System.out.println("sum of two integers="+sum);
}
}
class Methodover
{
public static void main(String[]args)
{
Adder a1=new Adder();
a1.add(5,6);
a1.add(2,3,4);
a1.add(5.6f,2.7f);
}
}
OUTPUT:
sum of two integers=11
sum of three integers=9
sum of two integers=8.3









EXPERIMENT-4
AIM: PROGRAM ON PACKAGES
PROGRAM:
 package Arithmetic;
public class calculate
{
int a=10;
int b=5;
public void add()
{
int s=a+b;
System.out.println("sum is="+s);
}
public void sub()
{
int d=a-b;
System.out.println("difference is="+d);
}
public void mul()
{
int m=a*b;
System.out.println("product is="+m);
}
public void mod()
{
int o=a%b;
System.out.println("modulus is="+o);
}
public void div()
{
int p=a/b;
System.out.println("division is="+p);
}
}
import java.util.*;
import Arithmetic.calculate;
class Test
{
public static void main(String[]args)
{
calculate c=new calculate();
c.add();
c.sub();
c.mul();
c.mod();
c.div();
}
} 
OUTPUT:
student@complab:~$ cd /home/student/Desktop/Bhate04
student@complab:~/Desktop/Bhate04$ javac -d . calculate.java
^[[Astudent@complab:~/Desktop/Bhate04$ javac Test.java
^[[Astudent@complab:~/Desktop/Bhate04$ java Test
sum is=15
difference is=5
product is=50
modulus is=0
division is=2




EXPERIMENT-5A
AIM:OPERATION ON ARRAY
PROGRAM:
import java.util.*;
class Array
{
public static void main(String args[])
{
Scanner sc = new Scanner(System.in);
int i,j,k,m,n,p;
System.out.println("Enter the number of rows for 1st matrix");
m = sc.nextInt();
System.out.println("Enter the number of columns for 1st matrix");
n = sc.nextInt();
int[][] mat1 = new int[m][n];
System.out.println("Enter the elements of the 1st matrix") ;
for(i=0;i<m;i++)
{
for(j=0;j<n;j++)
{
mat1[i][j] = sc.nextInt();
}
}
System.out.println("Enter the number of columns for 2nd matrix");
p = sc.nextInt();
int [][] mat2 = new int[n][p];
System.out.println("Enter the elements of the 2nd matrix") ;
for(i=0;i<n;i++)
{
for(j=0;j<p;j++)
{
mat2[i][j] = sc.nextInt();
}
}
System.out.println("The elements of matrix1 are") ;
for(i=0;i<m;i++)
{
for(j=0;j<n;j++)
{
System.out.print(mat1[i][j]+"\t");
}
System.out.println("");
}
System.out.println("The elements of matrix2 are") ;
for(i=0;i<n;i++)
{
for(j=0;j<p;j++)
{
System.out.print(mat2[i][j]+"\t");
}
System.out.println("");
}
int mul[][] = new int [m][p];
System.out.println("\n MULTIPLICATION of elements of matrix1 and matrix2
are\n ") ;
for(i=0;i<m;i++)
{
for(j=0;j<p;j++)
{
mul[i][j] = 0;
for(k=0;k<n;k++)
{
mul[i][j]=mul[i][j]+mat1[i][k]*mat2[k][j];
}
System.out.print(mul[i][j]+"\t");
}
System.out.println("");
}
}
}
OUTPUT:
Enter the number of rows for 1st matrix
3
Enter the number of columns for 1st matrix
3
Enter the elements of the 1st matrix
23
78
65
43
70
26
54
20
10
Enter the number of columns for 2nd matrix
3
Enter the elements of the 2nd matrix
3
29
57
39
29
51
92
66
90
The elements of matrix1 are
23 78 65
43 70 26
54 20 10
The elements of matrix2 are
3 29 57
39 29 51
92 66 90
MULTIPLICATION of elements of matrix1 and matrix2 are
9091 7219 11139
5251 4993 8361
1862 2806 4998 







EXPERIMENT-5B
AIM:OPERATION ON STRING
PROGRAM:

import java.util.Scanner;
class Example
{
public static void main(String args[])
{
String str1="String function Example";
String str2="Program on String";
String lc=str1.toLowerCase();
System.out.println("LowerCase="+lc);
String uc=str2.toUpperCase();
System.out.println("UpperCase="+uc);
System.out.println("Length of String is="+str1.length());
System.out.println("String after replacement:"+str1.replace("Example","demo"));
System.out.println("String after concatenation:"+str1.concat(str2));
StringBuffer obj=new StringBuffer(str2);
obj.reverse();
System.out.println(obj);
}
}
OUTPUT:
LowerCase=string function example
UpperCase=PROGRAM ON STRING
Length of String is=23
String after replacement:String function demo
String after concatenation:String function ExampleProgram on String
gnirtS no margorP








EXPERIMENT-6A
AIM: PROGRAM ON MULTILEVEL
PROGRAM:
import java.util.*;
class data
{
int length,breadth,height,A1,V1;
void input(int l, int b, int h)
{
length= l;
breadth= b;
height= h;
}
}
class Area extends data
{
int calculatearea()
{
A1=length*breadth;
return A1;
}
}
class Volume extends Area
{
int calculatevolume()
{
V1=A1*height;
return V1;
}
}
class main
{
public static void main(String args[])
{
Volume V=new Volume();
V.input(5,15,2);
System.out.println("Area of rectangle-"+V.calculatearea());
System.out.println("Volume of
rectangle-"+V.calculatevolume()); }
}
OUTPUT:
student@complab:~$ cd /home/student/Desktop/37
student@complab:~/Desktop/37$ javac main.java
student@complab:~/Desktop/37$ java main
Area of rectangle-75
Volume of rectangle-150



EXPERIMENT- 6B
AIM:PROGRAM ON HIERARCHICAL CLASS

PROGRAM:

import java.util.*;
class Emp
{
float salary=40000;
void dispsal()
{
System.out.println("Salary of emp is="+salary);
}
}
class Peremp extends Emp
{
double hike=0.5;
void incsal()
{
System.out.println("Perm.emp.increased sol is="+(salary+(salary*hike))); }
}
class Tempemp extends Emp
{
double hike=0.35;
void incsal()
{
System.out.println("Temp.emp.increased.salary is="+(salary+(salary*hike))); }
}
public class HIDemo
{
public static void main(String args[])
{
Peremp p=new Peremp();
Tempemp t=new Tempemp();
p.dispsal();
p.incsal();
t.dispsal();
t.incsal();
}
}
OUTPUT:
student@complab:~$ cd /home/student/Desktop/37
student@complab:~/Desktop/37$ javac HIDemo.java
student@complab:~/Desktop/37$ java HIDemo
Salary of emp is=40000.0
Perm.emp.increased sol is=60000.0
Salary of emp is=40000.0
Temp.emp.increased.salary is=54000.0





EXPERIMENT-07
AIM: PROGRAM ON MULTILEVEL INHERITANCE
PROGRAM
interface Exam
{
void Percent_cal();
}
class Student
{
String name;
int roll_no, Marks1, Marks2;
Student(String n, int rn, int m1, int m2) {
name = n;
roll_no = rn;
Marks1 = m1;
Marks2 = m2;
}
void show()
{
System.out.println("Student Name : "+name);
System.out.println("Roll no : "+roll_no);
System.out.println("Marks1 : "+Marks1);
System.out.println("Marks2 : "+Marks2); }
}
class Result extends Student implements Exam {
float per;
Result(String n,int rn,int m1,int m2)
{
super(n,rn,m1,m2);
}
public void Percent_cal()
{
int tot = Marks1 + Marks2;
per = (float)tot / 2;
}
void display()
{
show();
System.out.println("Percentage = "+per);
}
}
public class StudentDetails
{
public static void main (String[] args)
{
Result r = new Result("Aashish",11,75,95);
r.Percent_cal();
r.display();
}
}
OUTPUT:
student@complab:~$ cd /home/student/Desktop/37
student@complab:~/Desktop/37$ javac StudentDetails.java
student@complab:~/Desktop/37$ java StudentDetails Student
Name : Aashish
Roll no : 11
Marks1 : 75
Marks2 : 95
Percentage = 85.0









EXPERIMENT 8
AIM: PROGRAM ON ABSTRACT CLASS AND ABSTRACT METHOD

import java.util.*;
abstract class Base
{
float r,l,b,h,area;
public abstract void calculate();
public void display()
{
System.out.println("Area= "+area);
}
}
class circle extends Base
{
public void read(float x)
{
r=x;
}
public void calculate()
{
area=(22/7)*(r*r);
}
}
class rectangle extends Base
{
public void read(float x,float y)
{
l=x;
b=y;
}
public void calculate()
{
area=l*b;
}
}
class triangle extends Base
{
public void read(float x,float y)
{
l=x;
h=y;
}
public void calculate()
{
area=0.5f*l*h;
}
}
class program
{
public static void main(String[]
args) {
float x,y;
Scanner sc=new Scanner(System.in);
System.out.println("Enter the Radius:");
x=sc.nextFloat();
circle c=new circle();
c.read(x);
c.calculate();
c.display();
System.out.println("Enter the Length and
Breadth:"); x=sc.nextFloat();
y=sc.nextFloat();
rectangle r=new rectangle();
r.read(x,y);
r.calculate();
r.display();
System.out.println("Enter Base and height:");
x=sc.nextFloat();
y=sc.nextFloat();
triangle t=new triangle();
t.read(x,y);
t.calculate();
t.display();
}
}
OUTPUT:
student@pc765:~$ cd /home/student/Desktop
student@pc765:~/Desktop$ javac program.java
student@pc765:~/Desktop$ java program
Enter the Radius:
4
Area= 48.0
Enter the Length and Breadth:
35 68
Area= 2380.0
Enter Base and height:
68 22
Area= 748.0











EXPERIMENT NO 9
AIM: PROGRAM ON EXCEPTION HANDLING

import java.util.Scanner;
public class Exhandle1 {
public static void main(String args[]) {
int m[] = new int[5];
Scanner sc = new Scanner(System.in);
System.out.println("Enter array index");
int a_in = sc.nextInt();
System.out.println("Enter the no. you want to divide with");
int in=sc.nexIn();
try {
System.out.println("The value at array_index is " + m[a_in] /in);
} catch (ArithmeticException e) {
System.out.println("Arithmetic Exception");
System.out.println(e);
}
/* catch (ArrayIndexOutOfBoundsException e)
{
System.out.println("Array index out of bounds");
System.out.println(e);
} catch (Exception e) {
System.out.println("Some other Exception");
System.out.println(e);
}*/
}
}
OUTPUT:
student@pc765:~$ cd /home/student/Desktop
student@pc765:~/Desktop$ javac Exhandle1.java
student@pc765:~/Desktop$ java Exhandle1
Enter array index
5
Enter the no. you want to divide with
0
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException:
Index 5 out of bounds for length 5
at Exhandle1.main(Exhandle1.java:16)






EXPERIMENT NO:10
AIM:Program on multithreading

import java.util.*;
class OddThread extends Thread {
public void run() {
for (int i = 1; i <= 50; i++) {
if (i % 2 != 0) {
System.out.println("Output of OddThread: " + i);
}
}
}
}
class SquareThread extends Thread {
public void run() {
for (int i = 1; i <= 25; i++) {
System.out.println("Output of SquareThread: " + (i * i));
}
}
}
public class Threading {
public static void main(String[] args) {
OddThread oddThread = new OddThread();
SquareThread squareThread = new SquareThread();
oddThread.start();
squareThread.start();
}
}
OUTPUT:
student@complab:~/Desktop$ javac Threading.java
student@complab:~/Desktop$ java Threading
Output of OddThread: 1
Output of SquareThread: 1
Output of OddThread: 3
Output of SquareThread: 4
Output of OddThread: 5
Output of OddThread: 7
Output of OddThread: 9
Output of OddThread: 11
Output of OddThread: 13
Output of SquareThread: 9
Output of OddThread: 15
Output of SquareThread: 16
Output of OddThread: 17
Output of SquareThread: 25
Output of OddThread: 19
Output of OddThread: 21
Output of OddThread: 23
Output of SquareThread: 36
Output of OddThread: 25
Output of SquareThread: 49
Output of SquareThread: 64
Output of OddThread: 27
Output of SquareThread: 81
Output of OddThread: 29
Output of SquareThread: 100
Output of OddThread: 31
Output of SquareThread: 121
Output of OddThread: 33
Output of SquareThread: 144
Output of SquareThread: 169
Output of SquareThread: 196
Output of SquareThread: 225
Output of SquareThread: 256
Output of SquareThread: 289
Output of SquareThread: 324
