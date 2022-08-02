<h1>Hari 1</h1> 
<h2>Penengenalan Object Oriented Programming</h2> 

<br>
<h2>1. Tujuan</h2>
<p>a. Mahasiswa Memahami OOP</p>
<p>b. Mahasiswa mengerti environment C#</p>

<br>
<h2>2. Dasar Teori</h2>
<p>Paradigma Pemrograman</p>
<p>Object Oriented Programming (OOP) merupakan salah satu dari sekian banyak pendekatan
atau paradigma (pola) dalam membuat perangkat lunak. Dalam dunia industri, dikenal beberapa
paradigma selain OOP, seperti functional programming, procedural programming, logic
programming dan mathematical programming. Beberapa bahasa pemrograman hanya bisa
digunakan untuk satu paradigma saja (seperti Smalltalk untuk OOP, Haskell untuk functional
programming). Sedangkan beberapa bahasa pemrograman dirancang untuk kompatibel dengan
berbagai paradigma seperti Object Pascal, C++, Java, C#, Scala, Visual Basic, PHP, Python,
Ruby.</p>

<p>Apa itu Object?<p>
<p>Object dalam konteks pembuatan perangkat lunak, bisa dimaknai sebagaimana kita melihat
benda-benda disekitar. Sebagai contoh, dalam kehidupan sehari-hari kita menjumpai mobil dan pesawat. Mobil memiliki state dan behavior yang berbeda dengan pesawat meskipun sama- sama alat transportasi. Mobil bergerak dengan cara melaju sedangkan pesawat dengan cara terbang, merupakan salah satu contoh behavior.</p>


<p>Apa itu Class?</p>
<p>Class merupakan kerangka untuk memodelkan state dan behavior dari sebuah Object. Misalnya, sebuah mobil Lamborgini memiliki warna merah, transmisi manual dengan kecepatan
maksimal 250km/jam. Color, transmission state dan speed pada object mobil tersebut merupakan state dari mobil Lamborgini. Apabila dimodelkan oleh sebuah class, tampak seperti
berikut.</p>

```
Class Car{
String color : "red";
Int transmissionState:0;
Double speedMax:250;
Double speedCurrent:0;
}
```

<h2>3. Latihan</h2>
<p>3.1. Buka Visual Studio, buatlah new project dengan memilih Console App (.NET Core)</p>
<p>3.2. By default, Visual Studio akan memberikan template standar Hello World. Pastikan project
        ini bisa di run dengan cara menekan CTRL + F5 atau menu debug > Start Without
        Debugging. Sampai pada langkah ini, akan muncul jendela baru berupa console bertuliskan
        Hello World.
<p>3.3. Melalui jendela Solution Explorer, tambahkan new class dengan cara klik kanan.
Tambahkan class Car dengan rincian sebagai berikut.</p>

```
using System;
using System.Collections.Generic;
using System.Text;

namespace Project1TheSuperCar
{
    class Car
    {
        String color = "red";
        int transmissionState = 0;
        Double speedMax = 250;
        public Double speedCurrent = 0;
        
        public void go()
        {
                speedCurrent += 10;
        }
    }
}
```

<p>3.4. Buka file Program.cs kemudian ubahlah sesuai contoh berikut.</p>

```
using System;

namespace Project1TheSuperCar
{
        class Program
        {
                static void Main(string[] args)

            {
        
                Console.WriteLine("Hello The Super Car!");
                Car lamborgini = new Car();
                Console.WriteLine("current speed : "+lamborgini.speedCurrent);
                lamborgini.go();
                Console.WriteLine("current speed : "+lamborgini.speedCurrent);
                lamborgini.go();
                Console.WriteLine("current speed : "+lamborgini.speedCurrent);
                lamborgini.go();
                Console.WriteLine("current speed : "+lamborgini.speedCurrent);
            }
        }
}
```

<p>3.4. Apabila kode Anda benar, program akan mengeluarkan hasil sebagai berikut</p>

```
Hello The Super Car!
current speed : 0
current speed : 10
current speed : 20
current speed : 30
Press any key to continue . . .
```

<br>
<h2>4. Tugas</h2>
<p>Buatlah class Motor supaya program utama ini bisa berjalan, dengan ketentuan apabila motor dipanggil fungsi go maka kecepatannya akan bertambah 10 sedangkan bila dipanggil fungsi turnLeft() kecepatanya turun sebanyak 2.</p>

```
namespace Project1TheSuperCar
{
        class Program
        {
                static void Main(string[] args)
                {
                MotorSport motorSport = new MotorSport();
                Console.WriteLine("current speed : " +
                motorSport.speedCurrent);
                motorSport.go();//speed = 10
                Console.WriteLine("current speed : " +
                motorSport.speedCurrent);
                motorSport.turnLeft();//speed = 8
                Console.WriteLine("current speed : " +
                motorSport.speedCurrent);
                motorSport.go();//speed = 18
                Console.WriteLine("current speed : " +
                motorSport.speedCurrent);
                }
        }
}
```
