# AMAZON-CLONE
Check index.html to view the clone

Clone of Amazon
//lagrange
#include<stdio.h>
int main()
{
	int i,j,n;
	float x[50],y[50],xp,yp=0,p;
	printf("MANEET GOYAL\n");
	printf("lagrange interpolation method\n");
	printf("enter number of data:");
	scanf("%d",&n);
	printf("enter the elements:\n");
	for(i=0;i<n;i++)
	{
		printf("x[%d]:",i);
		scanf("%f",&x[i]);
		printf("y[%d]:",i);
		scanf("%f",&y[i]);
	}
	printf("\nenter interpolation point:");
	scanf("%f",&xp);
	for(i=0;i<n;i++)
	{
		p=1;
		for(j=0;j<n;j++)
		{
			if(i!=j)
			{
				p=p*(xp-x[j])/(x[i]-x[j]);
			}
		}
		yp=yp+p*y[i];
	}
	printf("interpolation value at %f is :%f",xp,round(yp));
	return 0;
}

seidal//
#include<stdio.h>
#include<math.h>
#define f1(x,y,z) (105-y-z)/6
#define f2(x,y,z) (155-(4*x)-(3*z))/8
#define f3(x,y,z) (-65+(5*x)+(4*y))/10
int main()
{  printf("MANEET GOYAL\n");
   float x0=0,y0=0,z0=0,x1,y1,z1,e,e1,e2,e3;
   int count=1;
   printf("enter tolerable error:\n");
   scanf("%f",&e);
   printf("\ncount\tx\ty\tz\n");
   do
   {
   	  x1=f1(x0,y0,z0);
   	  y1=f2(x1,y0,z0);
   	  z1=f3(x1,y1,z0);
   	  printf("%d\t%f\t%f\t%f\n",count,x1,y1,z1);
   	  e1=fabs(x0-x1);
   	  e2=fabs(y0-y1);
   	  e3=fabs(z0-z1);
   	  count++;
   	  x0=x1;
   	  y0=y1;
   	  z0=z1;
   }while(e1>e&&e2>e&&e3>e);
   printf("\n solution:x=%f,y=%f and z=%f\n",x1,y1,z1);
   return 0;
	
}

//guass elimination
//10x+y+2z==44
//2x+10y+z=51
//x+2y+10z=61
#include<stdio.h>
#include<math.h>
int main()
{    printf("MANEET GOYAL\n");
	float a[10][10],c;
	int i,j,row ,col,k;
	printf("enter the rows of matrix:");
	scanf("%d",&row);
	printf("enter the col of matrix:");
	scanf("%d",&col);
	printf("input the elements of matrix:\n");
	for(i=0;i<row;i++)
	{
		for(j=0;j<col;j++)
		{
			printf("the element at index:a[%d][%d]",i,j);
			scanf("%f",&a[i][j]);
		}
	}
		printf("Before Back-Substitution Method:-\n\t");
	for(i=0;i<row;i++){
		for(j=0;j<col;j++){
			printf("\%f    ",a[i][j]);
		}
		printf("\n\n\t");
	}
	//loop for generate of upper triangular matrix
	for(i=0;i<row;i++)
	{
		for(j=0;j<col;j++)
		{
		if(i>j)
		{
			c=a[i][j]/a[j][j];
			for(k=0;k<col;k++)
			{
				a[i][k]=a[i][k]-c*a[j][k];
			}
		}
		}
	}
	printf("After Back-Substitution Method:-\n\t");
	for(i=0;i<row;i++){
		for(j=0;j<col;j++){
			printf("%f   ",a[i][j]);
		}
		printf("\n\n\t");
	}
	//perform elimination
	float z,y,x;
	z=a[2][3]/a[2][2];
	y=(a[1][3]-(a[1][2]*z))/a[1][1];
	x=(a[0][3]  -  (a[0][1]*y) - (a[0][2]*z) ) / a[0][0];
	printf("x= %f\n",x);
	printf("y= %f\n",y);
	printf("z= %f\n",z);
	
	return 0;
}


//berge veta
#include<stdio.h>
#include<math.h>
#define f(x) (x*x*x-x*x-x+1)
int main()
{  printf("MANEET GOYAL\n");
	float a[9],b[9],c[9],p,er,ans;
	int n,i;
	int d=1;
	printf("enter the no of cofficent:");
	scanf("%d",&n);
	printf("enter the intial root");
	scanf("%f",&p);
	printf("enter max allowed error:");
	scanf("%f",&er);
	printf("enter the cofficent value:\n");
	for( i=0;i<n;i++)
	{
		scanf("%f",&a[i]);
	}
	do
	{    printf("the value of root is %f :\n",p);
		b[0]=a[0];
		for(i=1;i<n;i++)
		{
			b[i]=a[i]+(p*b[i-1]);
			//printf("the value %f at index [%d]\n",b[i],i);
		}
		c[0]=b[0];
		for(i=1;i<n-1;i++)
		{
			c[i]=b[i]+(p*c[i-1]);
				//printf("the value %f at index [%d]\n",c[i],i);
		}
		
			ans=p-(b[n-1]/c[n-2]);
			p=ans;
			
		d++;
	}while( d<=n);
	printf("actual root is: %f\n",p);
	return 0;
}

//secant
#include<stdio.h>
#include<math.h>
#define f(x) ((x*x*x)-x-1)
int main()
{    printf("MANEET GOYAL\n");
	int i=0;
	float x1,x2,x3,er;
	printf("enter the intial approximation for x1 and x2:");
	scanf("%f%f",&x1,&x2);
	printf("enter max allowed error:");
	scanf("%f",&er);
	if(f(x1)*f(x2)>0)
	{
		printf("starting value are wrong");
		return 0;
	}
	do{
		i++;
		x3 = (x1*f(x2)-x2*f(x1))/(f(x2)-f(x1) );
			printf("the value of x3 : %f and iteration no :%d\n",x3,i);
		if(f(x3)==0)
		{
			printf("root of this equation is : %f\n",x3);
			return 0;
		}
		x1=x2;
		x2=x3;
	}while(fabs f(x3)>er);
	printf("the approx root is : %f\n",x3);
	return 0;
}




flase position//
#include<stdio.h>
#include<math.h>
int main(){
    printf("Program to find the roots by false postion method");
    printf("\n");
    printf("\t\t\t\t\t\t by : Abhay (BCA)\n");
    int i,k;
    float a,b,c,fa,fb,fc;
    //equation=x^3x-x-1;
    printf("Enter the roots:\n");
    printf("Enter the first interval a:");
    scanf("%f",&a);
     printf("Enter the Second interval b:");
    scanf("%f",&b);
    printf("\n");
    printf("Enter the number of iterations :");
    scanf("%d",&k);
    printf("\n");
    for(i=1;i<=k;i++){
        printf("iterations %d \n",i);
        printf("a: %.5f  ",a);
         printf("b: %.5f  ",b);
         
         fa=a*a*a-a-1;
         fb=b*b*b-b-a;
         
         printf("fa: %.5f  ",fa);
         printf("fb: %.5f  ",fb);
         c=a-((b-a)/(fb-fa))*fa;
         
         printf("  c: %.5f\t",c);
         
         fc=c*c*c-c-1;
         printf("   fc:%.5f\n\n",fc);
         
         if(fc>0){
             b=c;
         }
         
    }
    if(fc<0){
        a=c;
        
        
    }

}



newton//
#include<stdio.h>
#include<math.h>
int main(){
    int i,n;
    float a,b,c,fo,fc,fdc;
    printf("Program to find the roots of a equation using derivative");
    printf("\n");
    printf("\t\t\t\t\t\t by : Abhay (BCA)\n");
    
    printf("Enter the roots: ");
    scanf("%f%f",&a,&b);
    c=(a+b)/2;
    printf("value of c: %f\n",c);
    printf("Iterations: ");
    scanf("%d",&n);
    
    for(i=1;i<=n;i++){
        printf("\nIteration %d :\n",i);
        fc=c*c*c-c-1;
        printf("The equation f(c)=c*c*c-c-1 : %f\n",fc);
        fdc=3*c*c-1;
        printf("The derivative of the equation f(c)=3*c*c-1 : %f\n",fdc);
    
        fo=c-(fc/fdc);
        printf("%d Iteration %f\n",i,fo);
        c=fo;
    }
    }


    bisection//
    #include<stdio.h>
#include<math.h>
int main(){
	int i,k;
	float a,b,c,fa,fb,fc;
	printf("Program to find roots of a equation using bisection method");
	printf("\n");
	printf("\t\t\t\t\t\t\tby : Abhay (BCA)\n");
	//equation x3-2x-5;
	printf("\n");
	printf("Enter the roots\n");
	printf("Enter the first interval a:");
	scanf("%f",&a);
	printf("Enter the second interval b:");
	scanf("%f",&b);
	printf("Enter the number of iterations:");
	scanf("%d",&k);
	for(i=1;i<=k;i++){
		printf("\n");
		printf("In iteration %d\n",i);
		
		printf("a: %.5f  ",a);
		printf("b: %.5f  ",b);
		fa=2*a*a*a-2*a-5;
		fb=2*b*b*b-2*b-5;
		printf("fa: %.5f  ",fa);
		printf("fb: %.5f  ",fb);
		c=(a+b)/2;
		printf("c: %.5f  ",c);
		fc=2*c*c*c-2*c-5;
		printf("fc: %.5f\n",fc);
		if(fc>0){
			b=c;
		}
	
		if(fc<0){
			a=c;
		}
	}
}
