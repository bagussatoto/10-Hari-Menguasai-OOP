<h1>Hari 7 </h1>

<h1>Pengenalan Konsep Inheritance</h2>

<h2>1 Tujuan</h2>
<p>1.1. Mahasiswa memahami konsep Inheritance</p>

<h2>2 Dasar Teori</h2>

<p> <code> Inheritance</code> adalah turunan atau pewarisan suatu class ke class baru dengan mewakili
semua function yang ada di class utama (parent class). Inheritance sering sekali digunakan
di dalam promgraman berorientasi objek atau OOP. Dengan kata lain, class utama (parent
class) dengan classes turunannya berhubungan satu sama lain.</p> 
<p>Contohnya seperti Gambar, baik duck, cuckoo maupun ostrich merupakan hewan keturunan burung. Semua
memiliki sayap dan dua kaki.</p>

<img width="706" alt="Visualisasi konsep turunan pada Burung" src="https://user-images.githubusercontent.com/87259393/189796132-5ceb57a8-a8bb-452e-94a4-af03858b79fc.png">

<h2>3 Latihan</h2> 
<p>1. Buatlah project baru “TheVehicles”</p>
<p>2. Buatlah class baru “Vehicle.cs” dengan code sebagai berikut</p>

```
using System;
using System.Collections.Generic;
using System.Text;

namespace TheVehicles
{
  class Vehicle
  {
    public void go()
    {
      Console.WriteLine("i am driving");
    }
  }
}
```

<p>3. Buatlah class StreetRacer.cs sebagai turunan dari vehicle, dengan code sebagai
berikut.</p>

```
using System;
using System.Collections.Generic;
using System.Text;

namespace TheVehicles
{
  class StreetRacer : Vehicle
  {
  }
}
```

<p>4. Inisiasi object StreetRacer dari Main Program.</p>

```
using System;

namespace TheVehicles
{
     class Program
    {
       static void Main(string[] args)
    {
      StreetRacer streetRacer = new StreetRacer();
      streetRacer.go();
    }
  }
}
```
<p>Catatan : Jalankan program tersebut. Meskipun class StreetRacer tidak nampak memiliki
method go(), namun program tetap bisa berjalan. Hal ini disebabkan karena class StreetRacer
merupakan turunan dari class Vehicle sehingga mewarisi method-methodnya.</p>

<h2>5. Hasilnya akan muncul pada command line sebagai berikut.</h2>

```
i am driving
```

<h2>6. Buatlah class FormulaOne.cs sebagai turunan dari vehicle, dengan code sebagai
berikut.</h2>

```
using System;
using System.Collections.Generic;
using System.Text;

namespace TheVehicles
{
  class FormulaOne: Vehicle
  {
  }
}
```

<h2>7. Inisiasi object FormulaOne dari Main Program.</h2>

```
using System;

namespace TheVehicles
{
    class Program
    {
      static void Main(string[] args)
      {
        StreetRacer streetRacer = new StreetRacer();
        FormulaOne formulaOne = new FormulaOne();
        streetRacer.go();
        formulaOne.go();
      }
    }
}
```
<p>Catatan : Jalankan program tersebut. Meskipun class FormulaOne tidak nampak memiliki
method go(), namun program tetap bisa berjalan. Hal ini disebabkan karena class FormulaOne
merupakan turunan dari class Vehicle sehingga mewarisi method-methodnya.</p>

<p>8. Hasilnya akan muncul pada command line sebagai berikut</p>

```
i am driving
i am driving
```

<p>9. Buatlah class Helicopter.cs sebagai turunan dari vehicle, dengan code sebagai berikut.
(Helikopter merupakan bagian dari kendaraan)</p>

```
using System;
using System.Collections.Generic;
using System.Text;

namespace TheVehicles
{
    class Helicopter: Vehicle
    {
    }
}
```

<p>10. Inisiasi object Helicopter dari Main Program.</p>

```
using System;

namespace TheVehicles
  {
      class Program
      {
        static void Main(string[] args)
      {
        StreetRacer streetRacer = new StreetRacer();
        FormulaOne formulaOne = new FormulaOne();
        Helicopter helicopter = new Helicopter();
        streetRacer.go();
        formulaOne.go();
        helicopter.go();
      }
  }
}
```

<p>11. Hasilnya akan muncul pada command line sebagai berikut</p>

```
i am driving
i am driving
i am driving
```

<h2>Tugas/Pertanyaan</h2>

<p>1. Apa pelajaran Inheritance yang dapat anda petik dari contoh kasus diatas (StreetRacer
dan FormulaOne) ?</p>
<p>2. Perhatikan langkah ke sembilan. Memang betul, Helikopter merupakan salah satu jenis
kendaraan namun apakah benar helikopter berjalan (driving) ? apabila kurang tepat,
bagaimana code Helicopter seharusnya ?</p>
<p>3. Dalam dunia pewayangan, terdapat seratus kawanan keluarga yang disebut Kurawa.
Kita buat logic sederhana permainan perang Baratayudha, dengan membuat object
keluarga Kurawa. Semua anggota kurawa merupakan seperguruan sehingga gaya
menyerang, bertahan dan mati-nya relatif sama. Perhatikan contoh main program
berikut.</p>

```
static void Main(string[] args)
{
    Duryodana duryodana = new Duryodana();
    Dursasana dursasana = new Dursasana();
    Karna karna = new Karna();
    Bima bima = new Bima();
    duryudana.hit()
    dursasana.kick();
    karna.defend();
    bima.dead();
}
```

<p>Apabila dijalankan, Main Program Kurawa diatas menghasilkan keluaran pada
command line seperti berikut.</p>

```
Kurawa is hitting
Kurawa is kick
Kurawa is defend
```



































