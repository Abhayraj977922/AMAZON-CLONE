Bubble sort
#include <stdio.h>

int main() {
    int size, temp;
    printf("Enter the size: ");
    scanf("%d", &size);
    
    int array[size];
    
    printf("Enter elements:\n");
    for (int i = 0; i < size; i++) {
        scanf("%d", &array[i]);
    }

    for (int i = 0; i < size - 1; i++) {
        for (int j = 0; j < size - 1 - i; j++) {
            if (array[j] > array[j + 1]) {
                temp = array[j];
                array[j] = array[j + 1];
                array[j + 1] = temp;
            }
        }
    }

    printf("Sorted list in ascending order:\n");
    for (int i = 0; i < size; i++) {
        printf("%d ", array[i]);
    }

    return 0;
}
Binary search
#include <stdio.h>

int main() {
    int size, key; // Declare variables for size and key
    printf("Program to perform the Binary search operation\n");
    printf("Enter the size of the array: ");
    scanf("%d", &size); // Corrected the format specifier

    int array[size]; // Declare the array after reading the size

    printf("Enter %d Elements!\n", size); // Corrected the format specifier
    for (int i = 0; i < size; i++) {
        scanf("%d", &array[i]); // Corrected format specifier
    }

    printf("Enter the element to search (A key): ");
    scanf("%d", &key);

    int start = 0;
    int end = size - 1;

    while (start <= end) {
        int mid = (start + end) / 2; // Corrected the calculation

        if (array[mid] == key) {
            printf("Key found at position %d\n", mid + 1);
            break;
        } else if (key < array[mid]) {
            end = mid - 1; // Corrected the condition
        } else {
            start = mid + 1; // Corrected the condition
        }
    }

    if (start > end) {
        printf("Key not found in the array.\n");
    }

    return 0;
    }
Linear search
#include <stdio.h>

int main() {
    printf("Linear Search\n");
    int i, n, b;
    
    printf("Enter the size of array: ");
    scanf("%d", &n);
    
    int arr[n];
    
    printf("Enter the elements of array:\n");
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    printf("Enter the element you want to search: ");
    scanf("%d", &b);
    
    for (i = 0; i < n; i++) {
        if (arr[i] == b) {
            printf("%d element is present at position %d\n", b, i);
            break;
        }
    }
    
    if (i == n) {
        printf("%d value not found\n", b);
    }
    
    return 0;
}
Deletion in linear array
#include <stdio.h>

int main() {
    int size, position;

    printf("Enter the size of the array: ");
    scanf("%d", &size);

    int array[size];

    printf("Enter %d elements:\n", size);
    for (int i = 0; i < size; i++) {
        scanf("%d", &array[i]);
    }

    printf("Enter the position of the element to be deleted: ");
    scanf("%d", &position);

    if (position < 1 || position > size) {
        printf("Invalid position!\n");
    } else {
        for (int i = position - 1; i < size - 1; i++) {
            array[i] = array[i + 1];
        }
        size--;

        printf("Updated Array:\n");
        for (int i = 0; i < size; i++) {
            printf("%d ", array[i]);
        }
        printf("\n");
    }

    return 0;
}
Insertion in array
#include <stdio.h>

int main() {
    int i, n, pos, num;
    
    printf("Enter number of elements: ");
    scanf("%d", &n);
    
    int a[n];
    
    for (i = 0; i < n; i++) {
        printf("Enter element at index %d: ", i);
        scanf("%d", &a[i]);
    }
    
    printf("Enter a number: ");
    scanf("%d", &num);
    
    printf("Enter position for insertion: ");
    scanf("%d", &pos);
    
    for (i = n; i >= pos; i--) {
        a[i] = a[i - 1];
    }
    
    a[pos - 1] = num;
    
    printf("After Insertion:\n");
    for (i = 0; i < n + 1; i++) {
        printf("In Arr[%d]: %d\n", i, a[i]);
    }
    
    return 0;
}
 Average of n number
 #include <stdio.h>

int main() {
    int i, n;
    float sum = 0, avg;
    
    printf("Enter the number of elements: ");
    scanf("%d", &n);

    int a[n];

    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &a[i]);
        sum += a[i];
    }

    avg = sum / n;

    printf("The average of the entered elements is: %f\n", avg);

    return 0;
}
Traverse in 1d array
#include <stdio.h>

int main() {
    int i, n;
    
    printf("Enter the number of elements: ");
    scanf("%d", &n);
    
    int a[n];
    
    for (i = 0; i < n; i++) {
        printf("Enter element at index %d: ", i);
        scanf("%d", &a[i]);
    }
    
    printf("Elements you have entered are:\n");
    
    for (i = 0; i < n; i++) {
        printf("a[%d]: %d\n", i, a[i]);
    }
    
    return 0;
}
Transpose
#include <stdio.h>

int main() {
    int a[10][10], transpose[10][10];
    int r, c; // Rows and columns

    printf("Enter the number of rows and columns: ");
    scanf("%d %d", &r, &c);

    printf("Enter matrix elements:\n");
    for (int i = 0; i < r; i++) {
        for (int j = 0; j < c; j++) {
            printf("Enter Element a[%d][%d]: ", i, j);
            scanf("%d", &a[i][j]);
        }
    }

    printf("Entered matrix:\n");
    for (int i = 0; i < r; i++) {
        for (int j = 0; j < c; j++) {
            printf("%d\t", a[i][j]);
        }
        printf("\n");
    }

    // Computing the transpose
    for (int i = 0; i < c; i++) {
        for (int j = 0; j < r; j++) {
            transpose[i][j] = a[j][i];
        }
    }

    printf("Transpose of the matrix:\n");
    for (int i = 0; i < c; i++) {
        for (int j = 0; j < r; j++) {
            printf("%d\t", transpose[i][j]);
        }
        printf("\n");
    }

    return 0;
}
matrix
#include<stdio.h>
int main(){
    int i,j,r,c,a[100][100],b[100][100],sum[100][100];
    
    printf("Enter the no. of rows and columns");
    scanf("%d%d",&r,&c);
    
    printf("Enter the first matrix\n");
    for(i=0;i<r;i++){
        for(j=0;j<c;j++){
            printf("Elements at [%d][%d] are :",i,j);
            scanf("%d",&a[i][j]);
        }
    }
    printf("\n");
printf("Entered Elements of 1st matrix are :\n");
    for(i=0;i<r;i++){
        for(j=0;j<c;j++){
            printf("%d\t",a[i][j]);
           
        }
}
printf("\n");
printf("Enter the second matrix\n");
printf("\n");
    for(i=0;i<r;i++){
        for(j=0;j<c;j++){
            printf("Elements at [%d][%d] are :",i,j);
            scanf("%d",&b[i][j]);
        }
    }
    printf("\n");
printf("Entered Elements of 2nd matrix are :\n");
    for(i=0;i<r;i++){
        for(j=0;j<c;j++){
            printf("%d\t",b[i][j]);
           
        }
}

printf("\n");
printf("Sum of matrix\n");
printf("\n");
    for(i=0;i<r;i++){
        for(j=0;j<c;j++){
            sum[i][j]=a[i][j]+b[i][j];
            printf("%d\t",sum[i][j]);
            
        }
    }
    printf("\n");
printf("Subtraction of matrix\n");
printf("\n");
    for(i=0;i<r;i++){
        for(j=0;j<c;j++){
            subtract[i][j]=a[i][j]-b[i][j];
            printf("%d\t",subtract[i][j]);
            
        }
    }


}
#include<stdio.h>
int main(){
    int i,a[10],n,pos;
    
    printf("Enter the size of array");
    scanf("%d",&n);
    
    printf("Enter the elements");
    for(i=0;i<n;i++){
    scanf("%d",&a[i]);
}

printf("Enter the index of postion you want to delete");
scanf("%d",&pos);
for(i=pos;i<n;i++){
    a[i]=a[i+1];
}

printf("After Deletion");
for(i=0;i<n-1;i++){
    printf("%d\t",a[i]);
}
}
 #include<stdio.h>
int main(){
    int n,a[10],i,key,pos;
    
    printf("Enter the size of array");
    scanf("%d",&n);
    
    printf("Enter elements");
    for(i=0;i<n;i++){
        scanf("%d",&a[i]);
    }
    
    printf("Enter the index of postion where you want to insert ");
    scanf("%d",&pos);
    
    printf("Enter the element you want to insert ");
    scanf("%d",&key);
    
    for(i=n-1;i<=pos;i--){
        a[n+1]=a[n];
    }
    a[pos]=key;
    printf("After Insertion :");
    for(i=0;i<n;i++){
        printf("%d\t",a[i]);
    }
}
