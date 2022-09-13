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
  





































