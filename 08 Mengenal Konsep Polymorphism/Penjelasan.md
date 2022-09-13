<h1> Hari 8</h1> 
<h1>Mengenal Konsep Polymorphism</h1>
  
  <h2>1 Tujuan</h2>
  <p>Mahasiswa memahami konsep Polymorphism dan penerapannya pada OOP</p>
  
<h2>2 Dasar Teori</h2>
<p> <code>Apa itu Polimorfisme?</code> <p>
  
<p>Polimorfisme adalah salah satu prinsip pemrograman berorientasi objek. "Poli" berarti banyak dan "morf" berarti bentuk karenanya nama polimorfisme. Polimorfisme juga disebut sebagai satu nama banyak bentuk atau memiliki satu nama dengan banyak fungsi. Dengan kata-kata sederhana, Anda dapat menggunakan nama metode yang sama dengan tanda tangan berbeda atau tanda tangan yang sama tetapi di kelas yang berbeda. Jadi,tergantung pada tipe data, ia memproses objek secara berbeda dan kemampuan untukmendefinisikan kembali metode untuk kelas turunan.</p>
  
<p> <code>Apa jenis Polimorfisme?</code> </p>
<p>Pada dasarnya ada dua jenis polimorfisme di c # i.e.</p>  
  
<p> <code>Polimorfisme statis</code> <p>
<p>Polimorfisme statis juga disebut sebagai polimorfisme Waktu Kompilasi. Dalam metode
polimorfisme statis kelebihan beban dengan nama yang sama tetapi memiliki tanda tangan
yang berbeda. Jadi itu disebut sebagai metode kelebihan beban.</p>
  
  
<p> <code>Polimorfisme yang dinamis</code> </p>
<p> Polimorfisme dinamis juga disebut sebagai Run Time polimorfisme. Dalam jenis ini metode
polimorfisme memiliki nama yang sama, tanda tangan yang sama tetapi berbeda dalam
implementasinya.</p>
<p>Dalam metode polimorfisme Dinamis ditimpa sehingga juga disebut sebagai metode menimpa.
Selama waktu berjalan, penggantian metode dapat dicapai dengan menggunakan prinsip
pewarisan dan menggunakan kata kunci "virtual" dan "override". jadi jenis polimorfisme ini juga
bisa disebut sebagai ikatan yang terlambat.</p>
<p>Pada akhir pengikatan kompiler tidak tahu metode apa yang harus dipanggil dan mana yang
dapat dicapai hanya selama run time.so disebut sebagai polimorfisme run time.  </p>
  
<h2>3 Langkah Percobaan</h2>
  
<p> <code>Percobaan 1.</code> </p>
<p>1 Buatlah project berjudul BursaMobil.</p>
<p>2 Buatlah class Avanza.cs dengan method sebagai berikut.</p>
  
```  
using System;
using System.Collections.Generic;
using System.Text;

namespace BursaMobil
{
   class Avanza
   {
        public void checkAccu()
      {
        Console.WriteLine("checkup accu");
      }
        public void checkRadiator()
      {
        Console.WriteLine("checkup radiator");
      }
        public void checkFuel()
      {
        Console.WriteLine("checkup fuel");
      }
        public void startEngine()
      {
        Console.WriteLine("startEngine...");
      }
  }
}  
```  
  
<p>3 Ubahlah pada program utama Program.cs lalu jalankan program.
using System;</p>

```
namespace BursaMobil
{
    class Program
    {
        static void Main(string[] args)
        {
            Avanza avanza = new Avanza();
            avanza.checkAccu();
            avanza.checkFuel();
            avanza.checkRadiator();
            avanza.startEngine();
        }
    }
}
```

<p>Catatan :</p>
</p>Agar mesin pada mobil avanza dapat dinyalakan, harus melalui serangkaian proses mulai dari cek kondisi aki, radiator hingga bensin. Apabila prosedur selesai dikerjakan, baru bisa dinyalakan mesinnya menggunakan method startEngine(). Bayangkan apabila mobilnya banyak (misal Anda membuat Game dan ada 100 object mobil) maka masing-masing harus diinisiasi dengan cara yang sama (memerlukan 5 buah baris mulai dari new () hingga startEngine) sebanyak 100 macam object mobil. Wow!</p>
  
<p>Percobaan 2.</p>
<p>1 Masih dalam project yang sama, tambahkan class baru bernama Car.cs</p>

```
using System;
using System.Collections.Generic;
using System.Text;

namespace BursaMobil
{
    class Car
    {
        private void checkAccu()
        {
          Console.WriteLine("checkup accu");
        }
          private void checkRadiator()
        {
          Console.WriteLine("checkup radiator");
        }
          public void checkFuel()
        {
          Console.WriteLine("checkup fuel");
        }
          public virtual void startEngine()
        {
          checkAccu();
          checkRadiator();
          checkFuel();
        }
    }
}
```
  
<p>2 Buatlah class Mobilio.cs dengan mewariskan object Car.</p>

```
using System;
using System.Collections.Generic;
using System.Text;

namespace BursaMobil
{
    class Mobilio : Car
    {
        public override void startEngine()
        {
            Console.WriteLine("Mobilio preparation....");
            base.startEngine();
            lockTheDoor();
        }
            private void lockTheDoor()
        {
            Console.WriteLine("Mobilio lock the door");
        }
    }
}
```
  
<p>3 Ubahlah class Program.cs lalu jalankan program.</p>

```
using System;

namespace BursaMobil
{
    class Program
    {
        static void Main(string[] args)
        {
            Avanza avanza = new Avanza();
            avanza.checkAccu();
            avanza.checkFuel();
            avanza.checkRadiator();
            avanza.startEngine();
            Car mobilio = new Mobilio();
            mobilio.startEngine();
        }
    }
}
```

<p>Catatan :</p>

<p>Mesin 100 buah mobil dapat dinyalakan dengan prosedur yang sama, berurutan mulai dari <code>checkAccu(), checkRadiator(), checkFuel() </code> dan <code>startEngine()</code>. Hal ini bisa kita ringkas dengan cara membuat satu object Car sebagai parent semua jenis mobil. Object Car memiliki default logic atau prosedur untuk menyalakan mobil. Dalam hal ini, diwakili dengan virtual method <code>startEngine().</code></p>

```
public override void startEngine()
    {
        Console.WriteLine("Mobilio preparation....");
        base.startEngine();//memanggil default prosedur dari Car
        lockTheDoor();
    }
```

<p>Kemudian method startEngine() diwariskan (overriding) kepada object turunannya (dalam hal ini object Mobilio). Dengan cara demikian, setiap kali method startEngine() pada object Mobilio dipanggil, secara otomatis akan memicu pula rangkaian startEngine() yang terdapat pada object parent.</p>

<p>Percobaan 3.</p>
<p>1 Buatlah class Xpander.cs dengan mewariskan object Car</p>

```
using System;
using System.Collections.Generic;
using System.Text;

namespace BursaMobil
{
    class Xpander : Car
    {
        public override void startEngine()
        {
            Console.WriteLine("Xpander preparation....");
            base.startEngine();
            turnOnSpotify();
        }
            private void turnOnSpotify()
        {
            Console.WriteLine("Xpander turn on the music via spotify");
        }
    }
}
```

<p>2 Ubahlah class Program.cs lalu jalankan program.</p>

```
using System;

namespace BursaMobil
{
  class Program
  {
      static void Main(string[] args)
      {
          Avanza avanza = new Avanza();
          avanza.checkAccu();
          avanza.checkFuel();
          avanza.checkFuel();
          avanza.startEngine();
          
          Car mobilio = new Mobilio();
          mobilio.startEngine();
          Car xpander = new Xpander();
          xpander.startEngine();
      }
  }
}
```

<p>Catatan :</p>
<p>Dengan cara perobaan 2 dan percobaan 3, maka prosedur yang sama bisa dikumpulkan menjadi default prosedur. Bahkan kita bisa saja memodifikasi prosedur dengan cara menambahkan logic didalam method override startEngine pada class Xpander maupun Mobilio. Tampak pada percobaan 3, prosedur pada Xpander ditambahi dengan menyalakan musik turnOnSpotify().</p>

<p>Tugas</p>
<p>1. Apa beda method overriding dengan method overloading ?</P
<p>2. Bilamana harus menggunakan Static Polymorphism dan Dynamic Polymorphism?</p>

<h2>3 Referensi</h2>
<p>https://www.onlinebuff.com/article_oops-principle-polymorphism-in-c-with-an-example_17.html</p>




















