<h1>Temperature mean</h1>

<h2>Description</h2>
This program results in a user fiding a temperature mean
<br />


<h2>Used to create:</h2>

- <b>Visual Studios</b> 

<img src="https://i.imgur.com/y8S6lhp.png" height="80%" width="80%" alt="]"/>


Code:
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Lab5
{
    class Program
    {
        static void Main(string[] args)
        {
            const int Sentinal = 999; //Const variable
            int count = 0;
            double temp = 0,
            sum = 0;
            string temp1;
            bool AccurateTemp;
            double mean;

            Console.WriteLine("Enter temperatures from -20 to 130 (Write 999 to stop)");//Writes out temps to user, displays 999 is to stop



            while (true) //if boolean is true
            {
                Console.WriteLine("Enter temperature: "); //Writes out Enter Temperature to user
                temp1 = Console.ReadLine(); //User temp input
                AccurateTemp = double.TryParse(temp1, out temp);

                if (AccurateTemp)
                {
                    temp = Convert.ToDouble(temp1);
                    if (temp >= -20 && temp <= 130)
                    {
                        count++;
                        sum = sum + temp; //Sum is += to temp

                    }
                    else if (temp == Sentinal) break;
                    else Console.WriteLine("Valid temperatures ranges from -20 to 130. Please reenter temperature");
                }
                else
                    Console.WriteLine("Valid temperatures ranges from -20 to 130. Please reenter temperature");
            }
            mean = sum / count; //sum/count is equal to mean

            Console.WriteLine("You entered " + count + " Valid temperatures");

            Console.WriteLine("The mean temp is " + mean + " degrees fahrenheit");

            Console.WriteLine("Press any key to continue...");

            Console.ReadLine();








        }
    }
}
