# sortowanie-babelkowe-c-


using System;
 
namespace App
{
    class Program
    {
        static void Main(string[] args)
        {
            while (true)
            {
                Console.WriteLine("Podaj liczbe");
                string numberStr = Console.ReadLine();
 
                uint[] numbers = new uint[numberStr.Length];
                int iter = 0;
                foreach(var character in numberStr)
                {
                    uint number;
                    if(!uint.TryParse(character.ToString(), out number))
                    {
                        Console.WriteLine("Niepoprawna liczba");
                        break;
                    }
                    numbers[iter++] = number;
                }
 
                // sortowanie babelkowe
                for(int i = 0; i < numbers.Length; i++)
                {
                    for (int j = 0; j < numbers.Length - 1; j++)
                    {
                        if(numbers[j] < numbers[j+1])
                        {
                            var temp = numbers[j + 1];
                            numbers[j + 1] = numbers[j];
                            numbers[j] = temp;
                        }
                    }
                }
 
                foreach(var number in numbers)
                    Console.Write(number);
                Console.WriteLine();
            }
        }
    }
}
