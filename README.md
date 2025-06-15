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
