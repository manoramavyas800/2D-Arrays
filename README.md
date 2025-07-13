# 2D-Arrays
//CREATE A 2D ARRAYS.
import java.util.Scanner;
public class MyFirstArrays {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int r1 = sc.nextInt();
        int c1 = sc.nextInt();
        int[][] arr = new int[r1][c1];
        for(int i=0;i<r1;i++){
            for(int j=0;j<c1;j++){
                arr[i][j]=sc.nextInt();
            }
        }
        for(int i=0;i<r1;i++){
            for(int j=0;j<c1;j++){
                System.out.print(arr[i][j]+" ");
            }
            System.out.println();
        }
        sc.close();

    }
    }
//ADDITION 2D ARRAYS

import java.util.Scanner;

public class Addition {
    static int[][] sum(int[][] result1, int row, int col, int[][] result2) {
        int[][] sum = new int[row][col];
        for (int i = 0; i < row; i++) {
            for (int j = 0; j < col; j++) {
                sum[i][j] = result1[i][j] + result2[i][j];
            }
        }
        return sum;
    }

    static void printArray(int[][] matrix) {

        for (int[] row : matrix) {
            for (int col : row) {
                System.out.print(col + " ");
            }
            System.out.println();
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the row number : ");
        int r1 = sc.nextInt();
        System.out.println("Enter the column number : ");
        int c1 = sc.nextInt();
        System.out.println("Enter the arrays number : ");
        int[][] arr1 = new int[r1][c1];
        for (int i = 0; i < r1; i++) {
            for (int j = 0; j < c1; j++) {
                arr1[i][j] = sc.nextInt();
            }
        }
        System.out.println("Enter the second row number : ");
        int r2 = sc.nextInt();
        System.out.println("Enter the column number : ");
        int c2 = sc.nextInt();
        System.out.println("Enter the arrays number : ");
        int[][] arr2 = new int[r2][c2];
        for (int i = 0; i < r2; i++) {
            for (int j = 0; j < c2; j++) {
                arr2[i][j] = sc.nextInt();
            }
        }
        if (r1 != r2 || c1 != c2) {
            System.out.println("Error-Addition is not possible");
        }
        int[][] sum = sum(arr1, r1, c1, arr2);
        System.out.println("Sum is of matrix : ");
        printArray(sum);
    }
}
//SUBSTITUTION 2D MATRIX.

import java.util.Scanner;
public class Substitution {
    static void PrintArray(int[][]matrix) {
        for (int[] ans : matrix) {
            for (int anInt : ans) {
                System.out.print(anInt + " ");
            }
            System.out.println();
        }
    }
    static void Diff(int [][]ans,int r1,int c1,int[][]arr2,int r2,int c2){
        if(r1!=r2||c1!=c2){
            System.out.println("Error- Substitution not possible");
            return;
        }
        for(int i=0;i<ans.length;i++){
            int j=0;
            while (j<ans[i].length) {
                ans[i][j]=ans[i][j]-arr2[i][j];
                j++;
            }
        }
        PrintArray(ans);

    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the row of array");
        int r1 = sc.nextInt();
        System.out.println("Enter the column of array");
        int c1 = sc.nextInt();
        int[][] ans = new int[r1][c1];
        System.out.println("Enter the elements of array");
        for (int i = 0; i < r1; i++) {
            for (int j = 0; j < c1; j++) {
                ans[i][j] = sc.nextInt();
            }
        }
        System.out.println("Enter the r2 of array");
        int r2 = sc.nextInt();
        System.out.println("Enter the column2 of array");
        int c2 = sc.nextInt();
        int[][] arr2 = new int[r2][c2];
        System.out.println("Enter the elements of array2");
        for (int i = 0; i < r2; i++) {
            for (int j = 0; j < c2; j++) {
                arr2[i][j] = sc.nextInt();

            }
        }
        System.out.println("matrix1");
        PrintArray(arr2);
        System.out.println("matrix2");
        PrintArray(ans);
        System.out.println("matrix substitution");
        Diff(ans, r1, c1, arr2, r2, c2);
    }
    }
    //INVERSE MATRIX.

    
import java.util.Scanner;
public class Permutation {
    static void PrintArray(int[][]matrix) {
        for (int[] ans : matrix) {
            for (int anInt : ans) {
                System.out.print(anInt + " ");
            }
            System.out.println();
        }
    }
    static void inverse(int[][] matrix, int row, int col) {
      for(int i = 0; i < row; i++) {
          for(int j = i; j < col; j++) {
              int temp=matrix[i][j];
              matrix[i][j]=matrix[j][i];
             matrix[j][i]=temp;
          }
      }
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the row of array");
        int r1 = sc.nextInt();
        System.out.println("Enter the column of array");
        int c1 = sc.nextInt();
        int[][] ans = new int[r1][c1];
        System.out.println("Enter the elements of array");
        for (int i = 0; i < r1; i++) {
            for (int j = 0; j < c1; j++) {
                ans[i][j] = sc.nextInt();
            }
        }
        System.out.println("matrix2");
        PrintArray(ans);
        inverse(ans, r1, c1);
        PrintArray(ans);
    }
    }
    //ROTATE ARRAY IN 90 DEGREE.
    /*1 2 
      3 4
      ROTARE.
      3 4
      1 2 */
import java.util.Scanner;
public class RotateArray {
    static void PrintArray(int[][]matrix) {
        for (int i = 0; i < matrix.length; i++) {
           for (int j = 0; j < matrix[i].length; j++) {
               System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }
    }
    static void inverse(int[][] matrix, int row, int col) {
      for(int i = 0; i < row; i++) {
          for(int j = i; j < col; j++) {
              int temp=matrix[i][j];
              matrix[i][j]=matrix[j][i];
             matrix[j][i]=temp;
          }
      }
    }
    static void rotateArray(int[][]ans, int n) {
        inverse(ans, n,n);
        for(int i = 0; i < n; i++) {
           reverse(ans[i]);
        }
    }
    static void reverse(int[]ans) {
      int i=0, j=ans.length-1;
      while(i<j) {
          int temp=ans[i];
          ans[i]=ans[j];
          ans[j]=temp;
          i++;
          j--;
      }
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the row of array");
        int r1 = sc.nextInt();
        System.out.println("Enter the column of array");
        int c1 = sc.nextInt();
        int[][] ans = new int[r1][c1];
        System.out.println("Enter the elements of array");
        for (int i = 0; i < r1; i++) {
            for (int j = 0; j < c1; j++) {
                ans[i][j] = sc.nextInt();
            }
        }
        System.out.println("matrix2");
        PrintArray(ans);
       rotateArray(ans,r1);
        System.out.println("rotate matrix.");
        PrintArray(ans);
    }
    }
//PASCAL TREBGLE

import java.util.Scanner;
public class PascalTrengle {
    static void PrintArray(int[][]matrix) {
        for (int[] ints : matrix) {
            for (int anInt : ints) {
                System.out.print(anInt + " ");
            }
            System.out.println();
        }
    }
    static int[][] pascalTrengle(int n) {
        int[][] result = new int[n][];
        for (int i = 0; i < n; i++) {
            result[i] = new int[i+1];
            result[i][0] =result[i][i] = 1;
            for (int j = 1; j < i; j++) {
                result[i][j] = result[i-1][j-1] + result[i-1][j];
            }
        }
        return result;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the row of array");
        int n= sc.nextInt();
       int[][] ans =pascalTrengle(n);
        System.out.println("matrix2");
        PrintArray(ans);

    }
    }
    //SPIRAL ORDER PRINTING

    import java.util.Scanner;
class Spiral {
    static int[][] spiralOrder(int[][] matrix,int r1,int c1) {
        int topSide = 0, rightSide = c1 - 1, bottomSide = r1 - 1, leftSide = 0;
        int totelElement = 0;
        while (totelElement < r1 * c1) {
            /*topside=left to right
            rightSide=top to bottomSide
            bottomSider=right to left
            leftSide=bottom to top
             */
            for (int i = leftSide; i <= rightSide && totelElement < r1 * c1; i++) {
               System.out.print(matrix[topSide][i] + " ");
                totelElement++;
            }
            topSide++;
        for (int i = topSide; i <=bottomSide && totelElement < r1 * c1; i++) {
            System.out.print(matrix[i][rightSide] + " ");
            totelElement++;
        }
        rightSide--;
    for(int i=rightSide; i>=leftSide&&totelElement<r1*c1; i--) {
       System.out.print(matrix[bottomSide][i] + " ");
        totelElement++;
    }
    bottomSide--;
    for(int i=bottomSide; i>=topSide&&totelElement<r1*c1; i--) {
       System.out.print(matrix[i][leftSide] + " ");
        totelElement++;
    }
    leftSide++;
        }
        return matrix;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the row of array");
        int r1= sc.nextInt();
        System.out.println("Enter the column of array");
        int c1= sc.nextInt();
        System.out.println("Enter the element of array");
        int[][]matrix= new int[r1][c1];
        for (int i = 0; i < r1; i++) {
            for (int j = 0; j < c1; j++) {
                matrix[i][j]= sc.nextInt();
            }
        }
        System.out.println("Enter the  totel element of array: ="+r1*c1);
        spiralOrder(matrix,r1,c1);
    }
    }
    //GENERET SPIRAL MATRIX


import java.util.Scanner;
class SpiralMatrix {
    static void printArray(int [][]matrix){
        for(int i=0;i<matrix.length;i++){
            for(int j=0;j<matrix[i].length;j++){
                System.out.print(matrix[i][j]+" ");
            }
            System.out.println();
        }
    }
    static int[][] generetspairalOrder(int n) {
        int[][] matrix = new int[n][n];
        int topSide = 0, rightSide = n - 1, bottomSide = n - 1, leftSide = 0;
        int curent = 1;
        while (curent<= n*n) {
            /*topside=left to right
            rightSide=top to bottomSide
            bottomSider=right to left
            leftSide=bottom to top
             */
            for (int i = leftSide; i <= rightSide && curent<=n*n; i++) {
               matrix[topSide][i] =curent++;
            }
            topSide++;
        for (int i = topSide; i <=bottomSide && curent<=n*n; i++) {
            matrix[i][rightSide] =curent++;
        }
        rightSide--;
    for(int i=rightSide; i>=leftSide&&curent<=n*n; i--) {
       matrix[bottomSide][i]=curent++;
    }
    bottomSide--;
    for(int i=bottomSide; i>=topSide&&curent<=n*n; i--) {
       matrix[i][leftSide]=curent++;
    }
    leftSide++;
        }
        return matrix;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the row of array");
        int r1= sc.nextInt();
       int[][]ans= generetspairalOrder(r1);
        printArray(ans);

    }
    }
//SUM OF RECTANGLE USING BRUTE FORCE METHOD


import java.util.Scanner;
class RectangleSum {
    static int sum(int [][]matrix,int l1,int l2,int r1,int r2){
        int sum=0;
        for(int i=l1;i<=l2;i++){
            for(int j=r1;j<=r2;j++){
                sum+=matrix[i][j];
            }
        }
        return sum;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the row of array");
        int r= sc.nextInt();
        System.out.println("Enter the column of array");
        int c= sc.nextInt();
        System.out.println("Enter the Element of array");
        int [][]matrix= new int[r][c];
        for(int i=0;i<r;i++){
            for(int j=0;j<c;j++){
                matrix[i][j]=sc.nextInt();
            }
        }
        System.out.println("Enter the value of l1 array");
        int l1= sc.nextInt();
        System.out.println("Enter the value of l2 array");
        int l2= sc.nextInt();
        System.out.println("Enter the value of  r1 array");
        int r1= sc.nextInt();
        System.out.println("Enter the value of r2 array");
        int r2= sc.nextInt();
        System.out.println("sum of matrix is "+sum(matrix,l1,l2,r1,r2));
    }
    }
    //SUM OF RECTANGLE USING PRE-CALCULATING THE HORIZONTAL SUM FOR EACH ROW

    
import java.util.Scanner;
class RectangleSum {
    static void prafixSum(int[][]matrix) {
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 1; j < matrix[0].length; j++) {
                matrix[i][j]+= matrix[i][j-1];
            }
        }
    }
    static int sum2(int [][]matrix,int l1,int l2,int r1,int r2) {
        int sum = 0;
        prafixSum(matrix);
        for(int i=l1;i<=l2;i++){
            if(r1>=1)
            sum+=matrix[i][r1]-matrix[i][r1-1];
            else
                sum+=matrix[i][r2];
        }

        return sum;
    }

    static int sum(int [][]matrix,int l1,int l2,int r1,int r2){
        int sum=0;
        for(int i=l1;i<=l2;i++){
            for(int j=r1;j<=r2;j++){
                sum+=matrix[i][j];
            }
        }
        return sum;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the row of array");
        int r= sc.nextInt();
        System.out.println("Enter the column of array");
        int c= sc.nextInt();
        System.out.println("Enter the Element of array");
        int [][]matrix= new int[r][c];
        for(int i=0;i<r;i++){
            for(int j=0;j<c;j++){
                matrix[i][j]=sc.nextInt();
            }
        }
        System.out.println("Enter the value of l1 array");
        int l1= sc.nextInt();
        System.out.println("Enter the value of l2 array");
        int l2= sc.nextInt();
        System.out.println("Enter the value of  r1 array");
        int r1= sc.nextInt();
        System.out.println("Enter the value of r2 array");
        int r2= sc.nextInt();
        System.out.println("sum of matrix is "+sum(matrix,l1,l2,r1,r2));
        System.out.println("sum of matrix is "+sum2(matrix,l1,l2,r1,r2));
    }
    }
    //PREFIX SUM  OVER COLUMNS AND ROW BOTH(all three method in these code)

    
import java.util.Scanner;
class permutation {
    static void prafixSum(int[][]matrix) {
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 1; j < matrix[0].length; j++) {
                matrix[i][j]+= matrix[i][j-1];
            }
        }
        //traverse vertically to calculate colum-wise sum
        for (int i = 0; i < matrix[0].length; i++) {
            for (int j = 1; j < matrix.length; j++) {
               matrix[j][i]+=matrix[j-1][i];
            }
        }
    }
    static int sum3(int[][]matrix,int l1,int l2,int r1,int r2) {
        int ans = 0;
        int sum=0,up=0,left=0,leftup=0;
        prafixSum(matrix);
        sum=matrix[l2][r2];
        if(r1>=1) {
            left = matrix[l2][r1 - 1];
        }
        if(l1>=1) {
            up = matrix[l1 - 1][r2];
        }
        if(l1>=1&&r1>=1) {
            leftup = matrix[l1 - 1][r1 - 1];
        }
        ans=sum-up-left+leftup;
        return ans;
    }
    static int sum2(int [][]matrix,int l1,int l2,int r1,int r2) {
        int sum = 0;
        prafixSum(matrix);
        for(int i=l1;i<=l2;i++){
            if(r1>=1)
            sum+=matrix[i][r1]-matrix[i][r1-1];
            else
                sum+=matrix[i][r2];
        }

        return sum;
    }

    static int sum(int [][]matrix,int l1,int l2,int r1,int r2){
        int sum=0;
        for(int i=l1;i<=l2;i++){
            for(int j=r1;j<=r2;j++){
                sum+=matrix[i][j];
            }
        }
        return sum;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the row of array");
        int r= sc.nextInt();
        System.out.println("Enter the column of array");
        int c= sc.nextInt();
        System.out.println("Enter the Element of array");
        int [][]matrix= new int[r][c];
        for(int i=0;i<r;i++){
            for(int j=0;j<c;j++){
                matrix[i][j]=sc.nextInt();
            }
        }
        System.out.println("Enter the value of l1 array");
        int l1= sc.nextInt();
        System.out.println("Enter the value of l2 array");
        int l2= sc.nextInt();
        System.out.println("Enter the value of  r1 array");
        int r1= sc.nextInt();
        System.out.println("Enter the value of r2 array");
        int r2= sc.nextInt();
        System.out.println("sum of matrix is "+sum(matrix,l1,l2,r1,r2));
        System.out.println("sum of matrix is "+sum3(matrix,l1,l2,r1,r2));
    }
    }
//SNAKS FROBLEM.

import java.util.Scanner;

public class Main {
    static int[][] snaksMat(int[][] matrix,int left,int right){
        for(int i=0;i<matrix.length;i++) {
            if (i % 2 == 0) {
                for (int j = 0; j < matrix[i].length; j++) {
                    System.out.print(matrix[i][j] + " ");
                    left++;
                }
            } else {
                for (int j = matrix[i].length - 1; j >= 0; j--) {
                    System.out.print(matrix[i][j] + " ");
                    right++;
                }
            }
        }
        return matrix;
    }
            public static void main(String[] args) {
               Scanner sc = new Scanner(System.in);
               System.out.println("Enter the name of a row");
               int r1 = sc.nextInt();
               System.out.println("Enter the name of a column");
               int c1 = sc.nextInt();
               System.out.println("Enter the value of a matrix");
               int[][] matrix = new int[r1][c1];
               for (int i = 0; i < matrix.length; i++) {
                   for (int j = 0; j < matrix[i].length; j++) {
                       matrix[i][j] = sc.nextInt();
                   }
               }
                snaksMat(matrix,r1,c1);

            }
        }
