# Modularizaci-n

```csharp
using System;
using System.Collections.Generic;

class program
{ 
    //---------------------------------------------------------------------------------------
   static double Line1(String num1)
    {
    Console.WriteLine(num1);
    if (!double.TryParse(Console.ReadLine(), out double Valido))
    {
        Console.WriteLine("Número no válido");
        return Line1(num1);
    }
    return Valido;
    }
//---------------------------------------------------------------------------------------

    static double Suma(double num1, double num2)
    {
        return num1 + num2;
    }
    static double Resta(double num1, double num2)
    {
    return num1 - num2;
    }
    static double Multi(double num1, double num2)
    {
    return num1 * num2;
    }
    static double Div(double num1, double num2)
    {
    return num1 / num2;
    }
    static void CalculadoraBasica()
    {
    Console.WriteLine("Calculadora Básica");
    double num1 = Line1("Ingrese el primer número: ");
    double num2 = Line1("Ingrese el segundo número: ");

    Console.WriteLine("Ingrese la operación a realizar: ");
    Console.WriteLine("1: Suma");
    Console.WriteLine("2: Resta");
    Console.WriteLine("3: Multiplicación");
    Console.WriteLine("4: División");
    string operacion = Console.ReadLine();
    switch (operacion)
        {
        case "1":
            Console.WriteLine($"El resultado de la suma es: {Suma(num1,num2)}");
            break;
        case "2":
            Console.WriteLine($"El resultado de la resta es: {Resta(num1, num2)}");
            break;
        case "3":
            Console.WriteLine($"El resultado de la multiplicación es: {Multi(num1, num2)}");
            break;
        case "4":
            Console.WriteLine($"El resultado de la división es: {Div(num1, num2)}");
            break;
        default:
            Console.WriteLine("Operación no válida");
            break;
        }
    }
//---------------------------------------------------------------------------------------
    static void ValidacionContrasena()
    {
        string Pass = "1514297";
        string Passc;
        Console.WriteLine("Validación de Contraseña");
                
        do
        { 
            Console.WriteLine("Ingrese la contraseña Correcta: ");
            Passc = Console.ReadLine();
            if (Passc != Pass)
            {
                Console.WriteLine("Contraseña Incorrecta. Intente nuevamente.");
            }
        }
        while (Passc != Pass);

        Console.WriteLine("Contraseña Correcta");
    }
//---------------------------------------------------------------------------------------
    static bool primo(int num)
    {
    bool primo = true;
    for  (int i = 2; i < num; i++)
    {
        if (num % i == 0)
        {
            primo = false; break;
        }
    }
    return primo;
    }
    static void NumerosPrimos()
    {
    Console.WriteLine("Números Primos");
    int num1 = (int)Line1("Ingrese un primer número: ");
      
    if (primo(num1))
    {
        Console.WriteLine("El número es primo");
    }
    else
    {
        Console.WriteLine("El número no es primo");
    }
    }
//---------------------------------------------------------------------------------------

    static void SumaNumerosPares()
    { 
    int i, N1, Sument=0;
    i = 0;

    N1 = (int)Line1("Ingrese un número: ");
   
    while (N1 != 0)
    {
        Console.WriteLine("Ingrese un numero: ");
        N1 = Convert.ToInt32(Console.ReadLine());
        Sument = Sument + N1;
        i ++;
    }
    Console.WriteLine($"La Suma de todos los enteros antes ingresar 0 es: {Sument} ");
    }
//---------------------------------------------------------------------------------------

    static double celcius(double num1)
    {
    return (num1 * 9 / 5) + 32;
    }
    static double fahrenheit(double int1)
    {
    return (int1 - 32) * 5 / 9;
    }
    static void ConversionTemperatura()
    {
    double num1;
    Console.WriteLine("Conversión de Temperatura");
    Console.WriteLine("Seleccione la Conversión deseada: ");
    Console.WriteLine("1. Celsius a Fahrenheit");
    Console.WriteLine("2. Fahrenheit a Celsius");
    int sel = Convert.ToInt32(Console.ReadLine());

    num1 = Line1("Ingrese la temperatura: ");

        switch (sel)
        {
        case 1:
            Console.WriteLine($"La Convercion a Fahrenheit es: {celcius(num1)}");
            break;
        case 2:
            Console.WriteLine($"La Convercion a Celius es: {fahrenheit(num1)}");
            break; 
        default:
            Console.WriteLine("Opción no válida");
            break;
        }
    }
//---------------------------------------------------------------------------------------
    static void ContadorVocales()
    {
    string cadena;
    int contador = 0;
    Console.WriteLine("Ingrese una cadena de texto: ");
    cadena = Console.ReadLine();
    for (int i = 0; i < cadena.Length; i++)
        {
        if (cadena[i] == 'a' || cadena[i] == 'e' || cadena[i] == 'i' || cadena[i] == 'o' || cadena[i] == 'u')
        {
            contador++;
        }
        }
        Console.WriteLine($"La cantidad de vocales en la cadena es: {contador}");
    }
//---------------------------------------------------------------------------------------
    static void CalculoFactoriales()
    {
         int num1;
        int factorial = 1;
        Console.WriteLine("Cálculo de Factoriales");
        num1 = (int)Line1("Ingrese un número: ");
        for (int i = 1; i <= num1; i++)
        {
        factorial = factorial * i;
        }
        Console.WriteLine($"El factorial de {num1} es: {factorial}");
    }
//---------------------------------------------------------------------------------------

    static void JuegoAdivinanza()
        {
         Random rnd = new Random();
        int num = rnd.Next(1, 100);
        int intentos = 0;
        int num2;
        Console.WriteLine("Juego de Adivinanza");
        Console.WriteLine("Adivina el número entre 1 y 100");
        do
        {
        num2 = (int)Line1("");
        if (num2 > num)
        {
            Console.WriteLine("Muy Alto ...");
        }
        else if (num2 < num)
        {
            Console.WriteLine("Muy Bajo ...");
        }
        intentos++;
        }
        while (num2 != num);
        Console.WriteLine($"Felicidades, adivinaste el número en {intentos} intentos");
        }
//---------------------------------------------------------------------------------------
    static void Intercambiar(ref int a, ref int b)
        {
            int temp = a;
            a = b;
            b = temp;
        }

    static void PasoPorReferencia()
    {
        int num1 = (int)Line1("Ingrese el primer número: ");
        int num2 = (int)Line1("Ingrese el primer número: ");

        Console.WriteLine($"\nValores antes del intercambio: num1 = {num1}, num2 = {num2}");

        Intercambiar(ref num1, ref num2);

        Console.WriteLine($"\nValores después del intercambio: num1 = {num1}, num2 = {num2}");
    }
//---------------------------------------------------------------------------------------
    static void TablaMultiplicar()
    {
    int num1 = (int)Line1("Ingrese un número que desea ver su tabla: ");
    for (int i = 1; i <= 10; i++)
    {
        Console.WriteLine($"{num1} x {i} = {num1 * i}");
    }
    }
    //---------------------------------------------------------------------------------------

    static void Main(string[] args)
    {
        while (true)
        {
            Console.Clear();
            Console.WriteLine("---------------Selecciona el Ejercicio--------------- ");
            Console.WriteLine("\n1. Calculadora básica \n2. Validación de contraseña \n3. Números primos \n4. Suma de números pares \n5. Conversión de temperatura \n6. Contador de vocales");
            Console.WriteLine("7. Cálculo de factoriales \n8. Juego de adivinanza \n9. Paso por referencia \n10. Tabla de multiplicar \n11. Salir del programa ...");
            int selec = (int)Line1("\nSeleccione una opción: ");

            switch (selec)
            {
                case 1:
                    CalculadoraBasica();
                    break;
                case 2:
                    ValidacionContrasena();
                    break;
                case 3:
                    NumerosPrimos();
                    break;
                case 4:
                    SumaNumerosPares();
                    break;
                case 5:
                    ConversionTemperatura();
                    break;
                case 6:
                    ContadorVocales();
                    break;
                case 7:
                    CalculoFactoriales();
                    break;
                case 8:
                    JuegoAdivinanza();
                    break;
                case 9:
                    PasoPorReferencia();
                    break;
                case 10:
                    TablaMultiplicar();
                    break;
                case 11:
                    Console.WriteLine("Saliendo de los ejercicios ...");
                    return;
                default:
                    Console.WriteLine("Opción no válida");
                    break;
            }
            Console.WriteLine("Presione una tecla para continuar...");
            Console.ReadKey();
        }
    }
}
