namespace RandomNumberGuessingGame
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Random random = new Random();
            int randomtoguess = random.Next(1, 101);
            double doublerandomtoguess = Convert.ToInt32(randomtoguess);
            int userguess = 0;
            int count = 0;


            while ((userguess == randomtoguess) == false)
            {
                if (count == 0)
                {
                    Console.WriteLine("Guess the random integer from 1 to 100.");
                }
                else
                {
                    Console.WriteLine("Try again.");
                }

                Console.WriteLine();
                double doubleuserguess = Convert.ToDouble(Console.ReadLine());
                userguess = Convert.ToInt32(doubleuserguess);

                if ((doubleuserguess % 1) != 0)
                {
                    Console.WriteLine("Invalid guess, the guess must be an integer.");
                }
                else if ((doubleuserguess > 100) || (doubleuserguess < 1))
                {
                    Console.WriteLine("Invalid guess, your number must be between 1 and 100 inclusive.");
                }
                else if (doubleuserguess != doublerandomtoguess)
                {
                    count = count + 1;
                    Console.WriteLine("This is a valid guess, but not the correct number.");
                }
                else
                {
                    count = count + 1;
                }
            }
            Console.WriteLine("Well done, the random number was " + randomtoguess + " and you found it in " + count + " guesses!");
        }
    }
}
