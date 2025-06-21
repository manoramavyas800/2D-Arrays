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
