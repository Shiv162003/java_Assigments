

Main class
//name -Shivansh nautiyal
//prn-21070126086
//batch-AI-ML-B1


import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
public class Main extends Functions
{
    public static void main(String args[])throws IOException
    {
        UserInput ob=new UserInput();
        int arr[]=new int[1000]; 
        int t=0;
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        while(t!=1)
        {
            System.out.println("enter 1 for working on two numbers enter 2 if you want to work on a list of numbers");
            int num = Integer.parseInt(br.readLine());
            if(num==1)
            {
                System.out.println("enter 1 for addition 2 for subtraction 3 for multiplication 4 for division");
                int a= Integer.parseInt(br.readLine());
                if(a==1)
                {
                    arr=ob.input_1(a);
                    long sum=sumTwo(arr);
                    System.out.println(sum);
                }
                else if (a==2)
                {
                    arr=ob.input_1(a);
                    long val=subtract(arr);
                    System.out.println(val);
                }
                else if (a==3)
                {
                    arr=ob.input_1(a);
                    long val=multiply(arr);
                    System.out.println(val);
                }
                else if (a==4)
                {
                    arr=ob.input_1(a);
                    double val=divide(arr);
                    System.out.println(val);
                }
            }
            else if(num==2)
            {
                 System.out.println("enter the size of the array you wanna put in");
                 int n= Integer.parseInt(br.readLine());
                 arr=ob.input_2(n);                
                 int a=100000; 
                 while(a!=0)
                 {
                     System.out.println("enter 1 for sum of the array  2 for mean  3 for Standard deviation  4 for variance 0 to exit the array  ");
                     a=Integer.parseInt(br.readLine());
                     if (a==1)
                     {
                          long x=sum(arr,n);
                          System.out.println("SUM="+x);
                     }
                     else if (a==2)
                     {
                         double x=mean(arr,n);
                         System.out.println("SUM="+x);                 
                     }
                     else if (a==3)
                     {
                         double x=SD(arr,n);
                         System.out.println("Standard deviation="+x); 
                     }
                     else if (a==4)
                     {
                         double x=getVariance(arr);
                         System.out.println("Standard deviation="+x); 
                     }
                 }
           }
           System.out.println("enter 1 if you want close the calculator");
           t=Integer.parseInt(br.readLine());
        }
    }
}

Function class
import java.util.*;
import java.lang.*;
import java.math.*;
class Functions extends UserInput
{
    static long sumTwo(int arr[])
    {
        long sum=0;
        sum=arr[0]+arr[1];
        return sum;
    }
    static long subtract(int arr[])
    {
        long val=0;
        val=arr[0]-arr[1];
        return val;
    }
    static long multiply(int arr[])
    {
        long val=0;
        val=arr[0]*arr[1];
        return val;
    }
    static double divide(int arr[])
    {
        double val=0;
        val=arr[0]/arr[1];
        return val;
    }
    static long sum(int arr[],int l) //for sum of the array 
    {
        long sum=0;
        for(int i=0;i<l;i++)
        {
            sum=sum+arr[i];
        }
        return sum;
    }
    static double mean(int  arr[],int l)// for array mean
    {
        double mean=0;
        long sum=sum(arr,l);
        mean=sum/l;
        return mean;
    }
    static double SD(int arr[],int l)//for standard deviation 
    {
        double sd;
        double mean=0;
        long sum=sum(arr,l);
        mean=sum/l;
        int mean1 =(int)mean;
        for(int i=0;i<l;i++)
        {
            arr[i]=arr[i]-mean1;
            arr[i]=arr[i]*arr[i];
        }
        sum=sum(arr,l);
        sd=Math.sqrt(sum);
        sd=sd/l;
        return sd;
    }
    static double getVariance(int[] arr)
    {
        double mean = 0;
        double sum = 0;
        // Calculate the mean of the array
        for (double num : arr) {
            sum += num;
        }
        mean = sum / arr.length;
        // Calculate the variance of the array
        double variance = 0;
        for (double num : arr) {
            variance += Math.pow(num - mean, 2);
        }
        variance /= arr.length;
        return variance;
    }
}

Input class
import java.util.*;
import java.io.*;
public class UserInput
{
    int[] input_1(int a)// input for  addition subtraction ,multiplacation and division
    {
        int arr[]=new int[2];
        Scanner so=new Scanner(System.in);
        if(a==1)//inputs for addition
        {
            System.out.println("enter  the numbers to be added");
            arr[0]=so.nextInt();
            arr[1]=so.nextInt();
        }
        else if(a==2)//input for subtraction
        {
            System.out.println("enter  the numbers from which you want to subtract from");
            arr[0]=so.nextInt();
            System.out.println("enter  the numbers from which you want to subtract ");
            arr[1]=so.nextInt();
        }
        else if(a==3)//input for multiplication
        {
            System.out.println("enter  the numbers to be multiplied");
            arr[0]=so.nextInt();
            arr[1]=so.nextInt();
        }
        else if(a==3)//input for division
        {
            System.out.println("enter  the  divident");
            arr[0]=so.nextInt();
            System.out.println("enter  the divisor ");
            arr[1]=so.nextInt();
        }
        return arr;
    }
    int[] input_2(int l)// input for  addition ,variance  and standard deviation of array . .
    {
        System.out.println("Enter the array");
        Scanner so=new Scanner(System.in);
        int arr[]=new int[l];
        for (int i=0;i<l;i++)
        arr[i]=so.nextInt();
        return arr;
    }
}








OUTPUT

 















LINK TO GITHUB
https://github.com/Shiv162003/java_Assigments
