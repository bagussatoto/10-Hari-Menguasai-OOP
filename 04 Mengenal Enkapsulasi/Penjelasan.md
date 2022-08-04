<h1> Hari 4 <h1>
<h1> Mengenal Enkapsulasi</h1>

<h2>1. Tujuan<h2>
<p> 1.1. Mahasiswa dapat memahami class diagram</p>
<p> 1.2. Mahasiswa memahami konsep enkapsulasi</p>
  
<h2>2. Dasar Teori</h2>
<p><code>Pengertian Enkapsulasi</code></p>
<p>Membuat kopi sebenarnya pekerjaan yang cukup rumit memerlukan beberapa langkah,
mulai dari menyiapkan biji kopi, gridding, memanaskan air hingga menyeduh bubuk kopi
dengan air panas. Namun bila Anda pernah melihat mesin kopi di Indomaret, Anda cukup
menyentuh satu tombol pada mesin, dalam waktu singkat maka kopi siap diminum. Mesin kopi
merupakan contoh nyata konsep enkapsulasi, yakni mengemas beberapa proses dan state
  menjadi satu kesatuan sehingga dari sisi lain pengguna relatif lebih mudah mengoperasikan.</p>
  
  <br>
  <p>Konsep dasar enkapsulasi adalah menyembunyikan kompleksitas didalam object dan
menyediakan antarmuka yang sederhana supaya bisa berinteraksi dengan object atau class
    lainnya.</p>
  
<h2>3. Latihan </h2>
<p>Pengantar<p>
  <p>● Sebuah cup kopi terbuat dari komposisi campuran 250ml air dan 25mg bubuk kopi.</p>
  <p>● Sebuah mesin kopi terdiri atas satu buah galon air berkapasitas 1000ml dan satu
    wadah bubuk kopi berkapasitas 100mg.</p>
<p>● Setiap kali kopi dibuat, kapasitas air dan bubuk kopi akan berkurang sesuai porsinya. </p> 
  
  
<br>  
<p>3.1. Buatlah project baru dengan nama TheCoffeMechine. Tambakan 3 buah class dengan
  mengikuti rancangan class diagram sebagai berikut</p>  
  
  <img width="1000" alt="Class Diagram" src="https://user-images.githubusercontent.com/87259393/182807138-16796071-8045-4f2f-b3b0-3eeb80bc8c0f.png">
 
<br>  
<h2>3.2. Ubahlah class utama Program.cs seperti pada Lampiran, sehingga hasilnya keluar seperti
  berikut</h2>  

```
check the water :1000 and the coffe powder : 100
result Yey! your coffe is ready
check the water :750 and the coffe powder : 75
result Yey! your coffe is ready
check the water :500 and the coffe powder : 50
result Yey! your coffe is ready
check the water :250 and the coffe powder : 25
result Yey! your coffe is ready
check the water :0 and the coffe powder : 0
result Sorry, the water is empty
check the water :0 and the coffe powder : 0
result Sorry, the water is empty  
check the water :0 and the coffe powder : 0  
```  

<br>
<h2>4. Lampiran</h2>  
  
<br>
<p>CoffePowder.cs</p>  
  
```  
using System;
  
namespace TheCoffeMechine
{
    class CoffePowder
    {
        private int netto=0;
        private int oneCupCoffe = 25;
        public CoffePowder(int netto){
        this.netto = netto;
    }
        public Boolean isAvailable(){
        return this.netto >= this.oneCupCoffe;
    }
        public void makeOneCup(){
        this.netto = this.netto - oneCupCoffe;
    }
        public int getNetto(){
        return this.netto;
    }
  }
}  
```  
  
  
  
  
  
  
  
  
  
  
<ul>  
  <br>
  <h2>5. Tugas</h2>
<p>1. Apabila sudah selesai mengerjakan latihan ini, tambahkan satu buah fugnsionalitas
dalam mesin kopi sehingga bisa membuat kopi Cappucino, yakni campuran antara air
panas, bubuk kopi dan susu (clue : tambahkan class Milk, satu cup kopi cukup
  menggunkan 100ml susu).</p>
<p>2. Dalam laporan, silakan membahas lebih detail tentang terapan konsep enkapsulasi
  pada kasus ini.</p>
  
