//C# code

using System.IO;
using System;
using System.Diagnostics;

public class Program
{
    public static void main()
    {
        int[] n;
            n = new int[] { 128, 256, 512, 1024, 2048, 4096, 8192, 16384, 32768, 65536 };

        //two decimal places

        Stopwatch s;

        //for loop #1

        for (int x = 0; x < 10; x++)
        {
            int[,] A = new int[n[x], n[x]];
            int[,] B = new int[n[x], n[x]];
            int[,] C = new int[n[x], n[x]];


            //Initialize matrices using 0

            for (int i = 0; i < n[x]; i++)
            {
                for (int j = 0; j < n[x]; j++)
                {
                    A[i, j] = 0;
                    B[i, j] = 0;
                }
            }
            //Using Version 1 of the problem

            s = Stopwatch.StartNew();

            for (int i = 0; i < n[x]; i++)
            {
                for (int j = 0; j < n[x]; j++)
                {
                    C[i, j] = A[i, j] + B[i, j];
                }
            }

            s.Stop();
                Console.WriteLine("Time taken: " + s.ElapsedMilliseconds + "ms");

            //Using Version 2 of the problem

            s = Stopwatch.StartNew();
            for (int j = 0; j < n[x]; j++)
                for (int i = 0; i < n[x]; i++)
                    C[i, j] = A[i, j] + B[i, j];

            s.Stop();
                Console.WriteLine("Time taken: " + s.ElapsedMilliseconds + "ms");
                Console.WriteLine("-------------------------------------------------\n\n");

        }

    }
}
