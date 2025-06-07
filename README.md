using System;


namespace TestTime

{

    public struct Time

    {

        private readonly int minutes;


        public Time(int hh, int mm)

        {

            this.minutes = 60 * hh + mm;

        }


        // Read-only property to get the hour part

        public int Hour

        {

            get { return minutes / 60; }

        }


        // Read-only property to get the minute part

        public int Minute

        {

            get { return minutes % 60; }

        }


        public override string ToString()

        {

            // Return the time in hh:mm format with leading zeros if needed

            return String.Format("{0:D2}:{1:D2}", Hour, Minute);

        }

    }


    class Program

    {

        static void Main(string[] args)

        {

            // Declare Time variables

            Time morningTime = new Time(10, 5);  // 10:05 AM

            Time earlyTime = new Time(0, 45);    // 00:45 AM

            Time noonTime = new Time(12, 0);     // 12:00 PM

            Time nightTime = new Time(23, 45);   // 11:45 PM


            // Print Time values

            Console.WriteLine("Morning time: " + morningTime);

            Console.WriteLine("Early time: " + earlyTime);

            Console.WriteLine("Noon time: " + noonTime);

            Console.WriteLine("Night time: " + nightTime);


            // You can also access Hour and Minute properties directly

            Console.WriteLine("Night time hour: " + nightTime.Hour);

            Console.WriteLine("Night time minute: " + nightTime.Minute);

        }

    }

}
