<h1>Hari 2</h1>
<h2>Class dan Object</h2>

<br>
<h2>1. Tujuan </h2>
<p>a. Mahasiswa dapat mendefinisikan class dan method</p>
<p>b. Mahasiswa dapat membaca class diagram (termasuk setter-getter)</p>

<br>
<h2>2. Dasar Teori</h2>
<b>Deklarasi Class</b>
<p>Dengan cara paling sederhana, class dapat dibentuk dengan pola sebagai berikut.</p>

```
class NamaClass {
  //deklarasi variabel atau
  //deklarasi method
}
```

<p>Penamaan class menggunakan model CamelCase diikuti dengan sepasang tanda kurung
kurawal. Diantara kurung kurawal ini kita dapat mendeklarasikan berbagai variabel atau
method.</p>

<br>
<b>Deklarasi Variabel</b>
<p>Terdapat tiga macam variabel yaitu (1) variabel yang terdapat didalam class, (2) variabel yang
terdapat didalam method (variabel lokal) dan (3) variabel yang terdapat pada deklarasi method
atau parameter. Variabel diawali dengan tipe data diikuti oleh nama variabel, seperti berikut.</p>

```
class NamaClass{
  int age = 0;
  string name = “”;
  
      void method1() {
      int speed;//local variabel
      }
      
          void method2(string name) {
          //variabel seabgai parameter
          }

}
```


<br>
<b>Deklarasi Method</b>
<p>Method merupakan fungsi tertentu yang terdapat didalam class. Sebuah method tidak dapat
berdiri sendiri tanpa class. Pada umumnya, sebuah method memiliki enam komponen, yaitu</p>

 1. Modifier seperti public, private (akan dijelaskan pada pertemuan berikutnya)
 2. Nilai kembalian, atau jika tidak memiliki kembalian biasanya ditandai dengan void
 3. Nama method, dengan mengikuti pola camelCase
 4. Parameter, variabel yang terdapat diantara tanda kurung. Sebuah method bisa memiliki
 banyak parameter.
 5. Exception, atau standar kembalian untuk menangani kegagalan sistem
 6. Method Body yang terletak diantara tanda kurung kurawal termasuk didalamnya
terdapat variabel lokal.

```
public boolean buildCar(String door, int maxSpeed, boolean isMatic){
// deklarasi lainnya
}
```

<br>
<b>Class Diagram</b>
<p>Class diagram merupakan salah satu bagian dari UML untuk menggambarkan secara visual
sebuah class dengan standarisasi tertentu. Sebuah class diagram terdiri atas tiga bagian,(1)
nama class, (2) variabel, dan (3) method.</p>

<table>
<img width="1002" alt="Class Diagram" src="https://user-images.githubusercontent.com/87259393/182534130-12d03559-8162-4b97-a004-db41ece4b159.png">
</table>

<h2>Latihan</h2>

<br>
<p>Hafsya senang bermain bola. Di rumahnya ada bola berwarna-warni berjumlah 9 buah. Supaya
rapi, hafsya selalu memasukan ke dalam keranjang selesai bermain. Tak lupa, Dia selalu
menghitung kembali setelah semua bola masuk ke dalam keranjang. Bagaimana kita bisa
mengubah cerita diatas menjadi sebuah program?</p>

<br>
<p>Langkah-langkah percobaan.</p>
<p>1. Buatlah new console apps project dengan nama TheBalls</p>
<p>2. Buatlah dua buah class baru, masing masing diberi nama Bucket.cs dan Ball.cs</p>

<p>Berikut kode untuk Balls.cs</p>

```
using System;

namespace TheBalls
{
      class Ball
      {
          private string color="";
          public void setColor(string color){
          this.color = color;
      }
          public string getColor(){
          return this.color;
      }
   }
}
```





