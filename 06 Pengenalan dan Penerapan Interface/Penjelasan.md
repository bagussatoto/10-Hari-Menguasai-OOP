<h1> Hari 6</h2>
<h1>6. Pengenalan dan Penerapan Interface</h1>

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


















