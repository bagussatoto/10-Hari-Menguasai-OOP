<h1> Hari 6</h2>
<h1> Pengenalan dan Penerapan Interface</h1>

<h2>1. Tujuan</h2>
<p>1. Mahasiswa mengerti penggunaan interface</p>
<p>2. Mahasiswa paham konsep Threading</p>

<h2>2. Dasar Teori</h2>

<p><code>Interface</code></p>
<p>Secara sederhana, Object Interface adalah sebuah ‘kontrak’ atau perjanjian implementasi
method.</p>

<p>Bagi class yang menggunakan object interface, class tersebut harus mengimplementasikan
ulang seluruh method yang ada di dalam interface. Dalam pemrograman objek, penyebutan
object interface sering disingkan dengan ‘Interface’ saja.</p>

<p><code>Threading</p></code>
<p>Thread adalah potongan kode yg independent (dari sebuah proses) yang di ekseskusi oleh
CPU yg penjadwalanya di lakukan oleh Operating sytem . Thread dibuat oleh programmer,
bagian mana saja yg akan dijadikan thread ditentukan oleh programmer. Setiap thread
mendapat jatah waktu dikerjakan CPU yg disebut quantum.</p>


<p><code>Perbedaan Multi-Tasking dan Multi-treading</code><p>
  
<p>Multitasking adalah beberapa proses aplikasi yang dijalankan secara paralel (sebenarnya sih
dijalankan bergantian secara cepat) oleh operating system contohnya anda menjalankan
program ms.excel sambil membuka program musik WinAmp . Kita merasakan program excel
dan winamp berjalan bersamaan , padahal sebenarnya CPU diperintahkan oleh OS
mengeksekusi program excel dan winamp secara bergantian dgn kecepatan tinggi.</p>
  
  
<p>Multi-treading adalah beberapa tread potongan program dlm satu proses yang dilaksana
secara paralel (sebenernya sih bergantian secara cepat( kecuali prosesornya multi core) dan
thread dibuat oleh programmer. Contohnya adalah sebuah program server misal chat server
maka ia harus melayani permintaan client yang datang hampir bersamaan secara paralel.
server akan membuat thread untuk melayani tiap client yg datang. setiap client dilayani oleh
satu thread. sehingga tidak ada antrian jika client yang datang banyak.</p>

<h2>3 Langkah-langkah</h2>
<p>1. Buat project baru dengan nama TheRestaurant.</p>
<p>2. Buatlah interface CookingListener.cs</p>

```
using System;
using System.Collections.Generic;
using System.Text;

namespace TheBreakfast
{
    interface CookListener
    {
        void onPreparation();
        void onCooking(String message);
        void onReady(String message);
    }
}
```

<p>3. Tambahkan class Egg.cs</p>

```
using System;
using System.Collections.Generic;
using System.Text;
using System.Threading;

namespace TheBreakfast
{
    class Egg
    {
        private CookListener listener;
        public Egg(CookListener listener)
        {
        this.listener = listener;
        }
        
        public void startCooking()
        {
            this.listener.onPreparation();
            ThreadStart cooking = new ThreadStart(cookingProcess);
            Thread childThread = new Thread(cooking);
            childThread.Start();
        }
        
        private void cookingProcess()
        {
            // do some work, like counting to 10 on other threads
            for (int counter = 10; counter >= 0; counter--)
        {
            Thread.Sleep(1000);
            this.listener.onCooking("cooking. wait for ..." + counter +
            " second.");
        }
        
        this.listener.onReady("Done. Egg ready to eat");
        }
    }
}
```

<p>4. Tambahkan Class EggCookingListener.cs pada file Program.cs</p>

```
using System;

namespace TheBreakfast
{
    class Program
    {
        static void Main(string[] args)
        {
        //....
        }
    }
    
    class EggCookingListener : CookListener
    {
    public void onCooking(string message)
      {
      Console.WriteLine(message);
      }
      public void onPreparation()
      {
      Console.WriteLine("prepared...");
      }

    public void onReady(string message)
      {
      Console.WriteLine(message);
      }
   }
}
```

<p>5. Ubahlah code Main pada Program.cs</p>

```
using System;

namespace TheBreakfast
{
    class Program
    {
      static void Main(string[] args)
    {
      Console.WriteLine("Welcome to the restaurant!");
      Egg egg = new Egg(new EggCookingListener());
      egg.startCooking();
      Console.WriteLine("Please wait. Enjoy your table");
    }
  }
  // other class...
}
```

<h2> 4 Pertanyaan dan Tugas</h2>

<p>1. Mengapa "Please wait. Enjoy your table" bisa dieksekusi lebih dahulu daripada
"Done. Egg ready to eat" ? Padahal egg.startCooking() dijalankan lebih dulu.</p>

<p>2. Carilah contoh lain dari penerapan Interface pada sebuah program!</p>

