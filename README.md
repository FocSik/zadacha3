# zadacha3
Третья задача
---
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    namespace VLAD.LAB._3
    {
    class Program
    {
    static void Main(string[] args)
    {
    Console.WriteLine("введите длинну первого массива: ");
    int n = int.Parse(Console.ReadLine());
    Console.WriteLine("введите длинну второго массива: ");
    int m = int.Parse(Console.ReadLine());
    double[] arr1 = new double[n];
    double[] arr2=new double[m];
    int size=arr1.Length+arr2.Length;//можно взять n и m
    double[] unitedarr = new double[size];
    int k=0;
    for (;;)
    {
    Console.WriteLine("введите K; K должно быть меньше чем, длинна первого массива: ");
    k = int.Parse(Console.ReadLine());
    if (k < arr1.Length)
    break;
    }
    Random rnd = new Random();
    for (int i = 0;i<arr2.Length;i++) {
    arr2[i] = rnd.Next(0, 10);
    }
    for(int i = 0;i<arr1.Length;i++){               
    arr1[i] = rnd.Next(0, 10);
    }
    for (int i = 0; i < k; i++)
    {
    unitedarr[i] = arr1[i];
    }
    int j = 0;
    for (int i = k; i < (k + arr2.Length);j++, i++)
    {
    unitedarr[i] = arr2[j];
    }
    for (int i = (k + arr2.Length); i < size; i++)
    {
    unitedarr[i] = arr1[i-arr2.Length];
    }
    Console.WriteLine(" исходный массив 1:  ");
    for (int i = 0; i < arr1.Length; i++)
    {
    Console.Write(" {0}", arr1[i]);
    }
    Console.WriteLine("\n исходный массив 2: ");
    for (int i = 0; i < arr2.Length; i++)
    {
    Console.Write(" {0}", arr2[i]);
    }
    Console.WriteLine("\n конечный массив: ");
    for (int i = 0; i < size; i++)
    {  
    Console.Write(" {0}", unitedarr[i]);
    }
    Console.WriteLine(" ");
    }
    }
    }
