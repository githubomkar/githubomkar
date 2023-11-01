Exp.No.1: DDA algorithm:

#include<stdio.h>
#include<graphics.h>
void main()
{
float x,y,xinc,yinc,x1,y1,x2,y2,dx,dy,step;
int i, gd=DETECT, gm;
printf("Enter the value of s1 and y1:");
scanf("%f %f",&x1,&y1);
printf("Enter the value ofx2 and y2:");
scanf("%f %f", &x2,&y2);
initgraph(&gd,&gm,NULL);
dx=abs(x2-x1);
dy=abs(y2*y1);
if(dx>=dy)
step=dx;
else
step=dy;
xinc=dx/step;
yinc=dy/step;
for(i=1;i<=step;i++)
{
putpixel(x,y,5);
x=x+xinc;
y=y+yinc;
delay(1000);
}
closegraph();
}
Output:
student@complab:~$ cd /home/student/Desktop/parasss
student@complab:~/Desktop/parasss$ gcc exp1.c -o exp1 -lgraph
student@complab:~/Desktop/parasss$ ./exp1
Enter the value of s1 and y1:600 900
Enter the value ofx2 and y2:1000 800





	




Exp. No.2: Bresenham’s Line drawing Program

#include<stdio.h>
#include<graphics.h>
void main()
{
int gd=DETECT, gm, x2,y2,x1,y1;
int dx,dy,p,i;
printf("Enter co-ordinate of start point:");
scanf("%d %d",&x1,&y1);
printf("Enter co-ordinate of end point:");
scanf("%d %d",&x2,&y2);
initgraph(&gd,&gm,NULL);
dx=x2-x1;
dy=y2-y1;
p=2*dy-dx;
for(i=1;i<dx;i++)
{
if(p>=0)
{
putpixel(x1,y1,7);
y1=y1+1;
p-p+2*dy-2*dx;
}
else
{
putpixel(x1,y1,7);
p=p+2*dy;
}
x1=x1+1;
delay(1000);
}
getch();
closegraph();
}
Output:
student@complab:~$ cd /home/student/Desktop/parasss
student@complab:~/Desktop/parasss$ gcc exp2.c -o exp2 -lgraph
student@complab:~/Desktop/parasss$ ./exp2
Enter co-ordinate of start point:100 10
Enter co-ordinate of end point:400 40











EXP.No. 3: MID POINT Circle drawing algorithm

#include<stdio.h>
#include<graphics.h>
void main()
{
int gd=DETECT,gm;
int x,y,r,p;
printf("Enter the radius: ");
scanf("%d",&r);
initgraph(&gd,&gm,NULL);
p=1-r;
x=0;
y=r;
do
{
putpixel(200+x,200+y,YELLOW);
putpixel(200+y,200+x,YELLOW);
putpixel(200-y,200+x,YELLOW);
putpixel(200-x,200+y,YELLOW);
putpixel(200-x,200-y,YELLOW);
putpixel(200-y,200-x,YELLOW);
putpixel(200+y,200-x,YELLOW);
putpixel(200+x,200-y,YELLOW);
if(p<0)
{
p=p+2*x+1;
}
else{
y=y-1;
p=p+2*(x-y)+1;
}
x=x+1;
delay(1000);
}
while(y>x);
getch();
closegraph();
}
Output:
student@complab:~$ cd /home/student/Desktop/parasss
student@complab:~/Desktop/parasss$ gcc exp3.c -o exp3 -lgraph
student@complab:~/Desktop/parasss$ ./exp3
Enter the radius: 100


	

Exp. No. 4: Midpoint Ellipse drawing Program:

#include<stdio.h>
#include<graphics.h>
void main()
{
int i,x,y,rx,ry,p1,p2,a,b,gd=DETECT,gm;
printf("\nEnter the value of rx and ry");
scanf("%d%d",&rx,&ry);
initgraph(&gd,&gm,NULL);
x=0;
y=ry;
p1=(ry*ry)-(rx*rx*ry)+(0.25*rx*rx);
a=2*rx*rx*y;
b=2*ry*ry*x;
while(b<a)
{
putpixel(200+x,200+y,7);
putpixel(200-x,200+y,7);
putpixel(200-x,200-y,7);
putpixel(200+x,200-y,7);
if(p1>=0)
{
x=x+1;
y=y-1;
a=2*rx*rx*y;
b=2*ry*ry*x;
p1=p1+(2*ry*ry*x)-(2*rx*rx*y)+(ry*ry);
}
else
{
x=x+1;
y=y;
a=2*rx*rx*y;
b=2*ry*ry*x;
p1=p1+(2*ry*ry*x)+(ry*ry);
}
delay(1000);
}
p2=ry*ry*(x+0.5)*(x+0.5)+rx*rx*(y-1)*(y-1)-rx*rx*ry*ry
; while(y!=0)
{
putpixel(200+x,200+y,7);
putpixel(200-x,200+y,7);
putpixel(200-x,200-y,7);
putpixel(200+x,200-y,7);
if(p2<=0)
{
x=x+1;
y=y-1;
p2=p2+(2*ry*ry*x)-(2*rx*rx*y)+(rx*rx);
}
else
{
x=x;
y=y-1;
p2=p2-(2*rx*rx*y)+(rx*rx);
}
delay(10);
}
getch();
closegraph();
}
Output:
student@complab:~$ cd /home/student/Desktop/parasss
student@complab:~/Desktop/parasss$ gcc exp4th.c -o exp4th -lgraph
student@complab:~/Desktop/parasss$ ./exp4th
Enter the value of rx and ry 50 65














	






Experiment no: 5a
a)	Flood Fill Program:

#include<stdio.h>
#include<graphics.h>
void flood(int x,int y,int new_col,int old_col)
{
if(getpixel(x,y)==old_col)
{
putpixel(x,y,new_col);
delay(10);
flood(x+1,y,new_col,old_col);
flood(x-1,y,new_col,old_col);
flood(x,y+1,new_col,old_col);
flood(x,y-1,new_col,old_col);
flood(x+1,y+1,new_col,old_col);
flood(x+1,y-1,new_col,old_col);
flood(x-1,y+1,new_col,old_col);
flood(x-1,y-1,new_col,old_col);
}
}
int main()
{
int gd =DETECT,gm;
initgraph(&gd,&gm,NULL);
rectangle(50,50,200,400);
flood(51,51,12,0);
getch();
return 0;
}
Output:
student@complab:~$ cd /home/student/Desktop/parasss
student@complab:~/Desktop/parasss$ gcc exp5a.c -o exp5a -lgraph
student@complab:~/Desktop/parasss$ ./exp5a









	

Experiment no: 5b
b)	Boundary Fill Program

#include<stdio.h>
#include<graphics.h>
void boundaryfill8(int x,int y,int fill_color,int boundary_color)
{
if(getpixel(x,y)!=boundary_color&& getpixel(x,y)!=fill_color)
{
putpixel(x,y,fill_color);
delay(10);
boundaryfill8(x+1,y,fill_color,boundary_color);
boundaryfill8(x,y+1,fill_color,boundary_color);
boundaryfill8(x-1,y,fill_color,boundary_color);
boundaryfill8(x,y-1,fill_color,boundary_color);
boundaryfill8(x-1,y-1,fill_color,boundary_color);
boundaryfill8(x-1,y+1,fill_color,boundary_color);
boundaryfill8(x+1,y-1,fill_color,boundary_color);
boundaryfill8(x+1,y+1,fill_color,boundary_color);
}
}
int main()
{
int gd=DETECT, gm;
initgraph(&gd,&gm,NULL);
rectangle(50,50,200,400);
boundaryfill8(51,51,4,15);
getch();
closegraph();
}
Output:
student@complab:~$ cd /home/student/Desktop/parasss
student@complab:~/Desktop/parasss$ gcc exp5b.c -o exp5b -lgraph
student@complab:~/Desktop/parasss$ ./exp5b




	



Exp. No. 6: 2D transformations:
a)	Translation:
#include<stdio.h>
#include<graphics.h>
void main()
{
int x1,x2,x3,x4;
int y1,y2,y3,y4;
int tx,ty;
printf("\n Enter values of x1,y1 :");
scanf("%d %d",&x1,&y1);
printf("\n Enter values of x2,y2 :");
scanf("%d %d",&x2,&y2);
printf("\n Enter values of tx,ty :");
scanf("%d %d",&tx,&ty);
int i,gd = DETECT, gm;
initgraph(&gd, &gm, NULL);
x3=x1+tx;
y3=y1+ty;
x4=x2+tx;
y4=y2+ty;
line(x1,y1,x2,y2);
delay(100);
line(x3,y3,x4,y4);
getch();
closegraph();
}





b) Scaling:

#include<stdio.h>
#include<graphics.h>
void main()
{
int x1,x2,x3,x4;
int y1,y2,y3,y4;
int sx,sy;
printf("\n Enter values of x1,y1 :");
scanf("%d %d",&x1,&y1);
printf("\n Enter values of x2,y2 :");
scanf("%d %d",&x2,&y2);
printf("\n Enter values of sx,sy :");
scanf("%d %d",&sx,&sy);
int i,gd=DETECT, gm;
initgraph(&gd, &gm, NULL);
x3=x1*sx;
y3=y1*sy;
x4=x2*sx;
y4=y2*sy;
line(x1,y1,x2,y2);
delay(100);
line(x3,y3,x4,y4);
getch();
closegraph();
}




c) Rotation:

#include<stdio.h>
#include<graphics.h>
void main ()
{
int gd =DETECT,gm;
int x1,x2,x3,y1,y2,y3,nx1,nx2,nx3,ny1,ny2,ny3,c;
int r;
float t ;
printf("Enter the points x1,x2,x3,y1,y2,y3:");
scanf("%d%d%d%d%d%d",&x1,&y1,&x2,&y2,&x3,&y3);
printf("Enter the angle:");
scanf ("%d",&r);
initgraph(&gd,&gm,NULL);
line(x1,y1,x2,y2);
line(x2,y2,x3,y3);
line(x3,y3,x1,y1);
t=3.14*r/180;
nx1=abs(x1*cos(t)-y1*sin(t));
ny1=abs(x1*sin(t)+y1*cos(t));
nx2=abs(x2*cos(t)-y2*sin(t));
ny2=abs(x2*sin(t)+y2*cos(t));
nx3=abs(x3*cos(t)-y3*sin(t));
ny3=abs(x3*sin(t)+y3*cos(t));
delay(100);
line(nx1,ny1,nx2,ny2);
line(nx2,ny2,nx3,ny3);
line(nx3,ny3,nx1,ny1);
getch();
closegraph();
}




d) Reflection:

#include<stdio.h>
#include<graphics.h>
void main()
{
int x1,y1,x2,y2;
printf("Enter the x1 and y1 value: ");
scanf("%d%d",&x1,&y1);
printf("Enter the x2 and y2 value: ");
scanf("%d%d",&x2,&y2);
int gd = DETECT,gm;
initgraph(&gd,&gm,NULL);
line(200 +x1,200 +y1,200 +x2,200 +y2);
line(200 -x1,200 +y1,200 -x2,200 +y2);
line(200 +x1,200 -y1,200 +x2,200 -y2);
line(200 -x1,200 -y1,200 -x2,200 -y2);
getch();
closegraph();
}







Exp. No. 7:
Animation: Bouncing Ball

#include<stdio.h>
#include<graphics.h>
int main()
{
int gd = DETECT, gm;
int i, x, y, flag = 0;
initgraph(&gd, &gm, NULL);
x = 30;
y = getmaxy() / 2;
while(1)
{
if(x >= getmaxx() - 30 || x <=30)
flag =! flag;
setcolor(YELLOW);
circle(x, y, 20);
floodfill(x, y, YELLOW);
delay(50);
cleardevice();
if(flag)
x = x + 5;
else
x = x - 5;
}
getch();
closegraph();
}













Exp. No. 8
Cohen Sutherland Line clipping
Aim: Write a program to implement line clipping.

#include<stdio.h>
#include<graphics.h>
void main()
{
int gd=DETECT,gm;
int x,y,x1,y1,x2,y2,m,xmin,xmax,ymin,ymax,dx,dy;
// xmin=50,ymin=10,xmax=80,ymax=40,x1=70,y1=20,x2=100,y2=10;
printf("Enter x1,y1,x2,y2:");
scanf("%d%d%d%d",&x1,&y1,&x2,&y2);
printf("Enter value of xmin,ymin,xmax,ymax:");
scanf("%d%d%d%d",&xmin,&ymin,&xmax,&ymax);
initgraph(&gd,&gm,NULL);
rectangle(xmin,ymin,xmax,xmax);
line(x1,y1,x2,y2);
delay(100);
dy=y2-y1;
dx=x2-x1;
m=dy/dx;
cleardevice();
if(x2>=xmax)
{
if(y2>=ymin && y2<=ymax)
{
x=xmax;
y=y1+m*(xmax-x1);
delay(100);
rectangle(xmin,ymin,xmax,ymax);
line(x1,y1,x,y);
}
}
if(x2<=xmin)
{
if(y2>=ymin && y2<=ymax)
{
x=xmin;
y=y1+m*(xmin-x1);
delay(100);
rectangle(xmin,ymin,xmax,ymax);
line(x1,y1,x,y);
}
}
if(y2>=ymax)
{
if(x2>=ymin && x2<=ymax)
{
y=ymax;
x=x1+(ymax-y1)/m;
delay(100);
rectangle(xmin,ymin,xmax,ymax);
line(x1,y1,x,y);
}
}
if(y2<=ymin)
{
if(x2>=ymin && x2<=ymax)
{
y=ymin;
x=x1+(ymin-y1)/m;
delay(100);
rectangle(xmin,ymin,xmax,ymax);
line(x1,y1,x,y);
}
}
getch();
closegraph();
}
Output:
student@complab:~$ cd /home/student/Desktop/TanmayChawhan_S.E.Comps-A
student@complab:~/Desktop/TanmayChawhan_S.E.Comps-A$ gcc exp8.c -o exp8 -lgraph
student@complab:~/Desktop/TanmayChawhan_S.E.Comps-A$ ./exp8
Enter x1,y1,x2,y2:70
20
100
10
Enter value of xmin,ymin,xmax,ymax:50
10
80
40












Exp. No.9: Brezier curve

#include<stdio.h>
#include<graphics.h>
int main()
{
int gd = DETECT,gm;
int x[4],y[4],Px,Py,i,n;
double t;
printf("\n Enter Numbers of Control Points : ");
scanf("%d",&n);
printf("\n Enter the Control Points : ");
for(i=0;i<n;i++)
scanf("%d %d ",&x[i],&y[i]);
initgraph(&gd,&gm,NULL);
for(i=0;i<n;i++)
putpixel(x[i],y[i],BLUE);
for(t=0.0;t<=1.0;t += 0.001)
{
Px = (1-t)*(1-t)*(1-t)*x[0]+3*t*(1-t)*(1-t)*x[1]+3*t*t*(1-t)*x[2]+t*t*t*x[3];
Py = (1-t)*(1-t)*(1-t)*y[0]+3*t*(1-t)*(1-t)*y[1]+3*t*t*(1-t)*y[2]+t*t*t*y[3];
putpixel(Px,Py,RED);
delay(20);
}
getch();
closegraph();
}















Exp.no. 10
3D Transformation:

a)	Translation

#include<stdio.h>
#include<graphics.h>
#include<math.h>
void main()
{
int maxx, maxy,midx,midy;
int gd = DETECT,gm;
int tx,ty,z,o,x1,x2,y1,y2;
printf("\n Enter Translation factor : ");
scanf("%d %d",&tx ,&ty);
initgraph(&gd,&gm,NULL);
maxx = getmaxx();
maxy = getmaxy();
midx = maxx/2;
midy = maxy/2;
setcolor(RED);
bar3d(midx+50,midy-100,midx+60,midy-90,10,1);
delay(1000);
bar3d(midx+tx+50,midy-(ty+100),midx+tx+60,midy-(ty+90),10,1);
getch();
closegraph();

}







b) Scaling:


#include<stdio.h>
#include<graphics.h>
#include<math.h>
void main()
{
int maxx, maxy,midx,midy;
int gd = DETECT,gm;
int sx,sy,sz,o,x1,x2,y1,y2;
printf("\n Enter Translation factor : ");
scanf("%d %d %d",&sx ,&sy,&sz);
initgraph(&gd,&gm,NULL);
maxx = getmaxx();
maxy = getmaxy();
midx = maxx/2;
midy = maxy/2;
setcolor(RED);
bar3d(midx+50,midy-100,midx+60,midy-90,10,1);
delay(1000);
bar3d(midx+(sx*50),midy-(sy*100),midx+(sx*60),midy-(sy*90),5*sz,1);
getch();
closegraph();
}







c) Rotation:

#include<stdio.h>
#include<graphics.h>
#include<math.h>
void main()
{
int gd = DETECT,gm;
int maxx, maxy, midx,midy;
int tx,ty,z,o,x1,x2,y1,y2;
printf("\n Enter Rotational factor : ");
scanf("%d",&o);
initgraph(&gd,&gm,NULL);
maxx = getmaxx();
maxy = getmaxy();
midx = maxx/2;
midy = maxy/2;
setcolor(BLUE);
x1 = 50*cos(o*3.14/180)-100*sin(o*3.14/180);
y1 = 50*sin(o*3.14/180)+100*cos(o*3.14/180);
x2 = 60*cos(o*3.14/180)-90*sin(o*3.14/180);
y2 = 60*sin(o*3.14/180)+90*cos(o*3.14/180);
bar3d(midx+50,midy-x1,midx+60,midy-x2,50,10);
delay(100);
bar3d(midx+x1,midy-100,midx+x2,midy-90,50,10);
getch();
closegraph();
}

