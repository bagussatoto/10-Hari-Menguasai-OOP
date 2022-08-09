<h1> Hari 5</h1>
<h1> Dependencies</h1>

<h2>1. Tujuan </h2>
<p>1.1 Mahasiswa memahami konsep dependies</p>

<h2>2. Dasar Teori</h2>
<p>Dalam konsep OOP, dependency merupakan teknik di mana suatu object diinisasi dan
digunakan oleh class lain. Pada dasarnya ada tiga macam sebagai berikut.</p>
<ul>
<p>1. Constructor Injection. Sebuah class dimasukkan ke dalam class lain melalui constructor.</p>
<p>2. Setter Injection. Sebuah object dimasukkan ke dalam class lain melalui method setter
yang disediakan oleh class pengguna.</p>
<p>3. Interface Injection. Class pengguna (client) harus menyediakan interface yang
mengekspose method setter untuk memasukkan dependencies.</p>
</ul>

<h2>3. Latihan</h2>
<p>3.1. Buatlah project bernama TheAeroPlane.</p>
<p>3.2. Tambahkan class Logger.cs</p>


```
using System;

namespace TheAeroPlane
{
    class Logger
    {
        public void info(string message){
            Console.WriteLine("info : "+message);
        }
        public void warning(string message){
            Console.WriteLine("warning : "+message);
        }
        public void error(string message){
            Console.WriteLine("error : "+message);
        }
    }
}
```

<p>3.3 Tambahkan class Plane.cs</p>

```
using System;

namespace TheAeroPlane
{
   class Plane
   {
      private Logger logger;
      
      public Plane(Logger logger){
          this.logger = logger;
      }
      public void startEngine(){
          this.logger.info("mesin menyala");
      }
      public void takeOff(){
         this.logger.info("pesawat naik");
      }
      public void turbulance(){
         this.logger.warning("pesawat berguncang");
      }

   }
}
```

<p>3.4. Tuliskan pada Program.cs</p>

```
using System;

namespace TheAeroPlane
{
    class Program
    {
        static void Main(string[] args)
        {
            Logger logger = new Logger();
            Plane plane = new Plane(logger);
            plane.startEngine();
            plane.takeOff();
            plane.turbulence();
        }
    }
}
```









