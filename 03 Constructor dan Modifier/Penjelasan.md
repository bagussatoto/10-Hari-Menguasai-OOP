<h1>Hari 3</h1>
<h2>Construktor dan Modifier</h2>

<br>
<h2>1. Tujuan </h2>
<p>1. Mahasiswa dapat mengontrol akses anggota class </p>
<p>2. Mahasiswa mengerti cara menginisiasi object menggunakan constructor</p>


<br>
<h2>2. Dasar Teori</h2>
<b>Akses modifier<b>
<p>Semua tipe dan tipe anggota memiliki tingkat aksesibilitas, yang mengontrol apakah
mereka dapat digunakan dari kode lain di package Anda atau package lain. Anda dapat
menggunakan pengubah akses berikut untuk menentukan aksesibilitas tipe atau anggota ketika
Anda mendeklarasikannya:</p>

<ul>
<br>
<b>Public<b>
<p>Jenis atau anggota dapat diakses oleh kode lain dalam rakitan yang sama atau rakitan lain
yang merujuknya.</p>

<br>
<b>Private</b>
<p>Jenis atau anggota hanya dapat diakses oleh kode di kelas atau struct yang sama.</p>

<br>
<b>Protected<b>
<p>Jenis atau anggota hanya dapat diakses oleh kode di kelas yang sama, atau di kelas yang
berasal dari kelas itu.</p>

<br>
<b>Internal<b>
<p>Jenis atau anggota dapat diakses oleh kode apa pun di rakitan yang sama, tetapi tidak dari
rakitan lain.</p>

<br>
<b>Constructor sebuah class</b>
<p>Setiap kali kelas atau struct dibuat, constructor-nya disebut. Kelas atau struct dapat
memiliki beberapa constructor yang mengambil argumen yang berbeda. Constructor
memungkinkan programmer untuk menetapkan nilai default, membatasi instantiation, dan
menulis kode yang fleksibel dan mudah dibaca.</p>

<br>
<b>Sintaks constructor</b>
<p>constructor adalah method yang namanya sama dengan nama class. Cara penulisanya hanya
mencakup nama method dan daftar parameternya; tidak termasuk tipe pengembalian. Contoh
berikut memperlihatkan konstruktor untuk kelas yang bernama Person.</p>

```
public class Person
{
    private string last;
    private string first;
    public Person(string lastName, string firstName)
    {
        last = lastName;
        first = firstName;
    }
      // Remaining implementation of Person class.
}
```

<br>
<b>Fluent Builder Pattern</b>
<p>Fluent Builder pattern merupakan salah satu pendekatan untuk membangun object baru
yang terdiri atas beberapa object lainnya. Seperti anda memiliki Komputer, terdiri atas beberapa
komponen utama seperti Ram, Processor, Vga dan beberapa komponen tambahan seperti
Printer dan Monitor. Dengan Fluent Builder Pattern, kita bisa memilah mana komponen yang
wajib ditambahkan serta komponen apa saja yang hanya bersifat opsional. Cara penulisannya
berantai seperti berikut.</p>

```
Computer computer = new
Computer.Builder(samsungRam,nvdiaVga,intelProcessor)//parameter wajib
                .withMonitor(lgMonitor)//parameter opsional
                .withPrinter(hpPrinter)//parameter opsional
                .build();
```
</ul>

<h2>3. Latihan</h2>

1. Buatlah project baru dengan nama TheSuperComputer. Tambahkan enam buah file
masing-masing diberi nama Computer.cs, Monitor.csm Printer.cs, Processor.cs,
Program.cs, Ram.cs dan Vga.cs

2. Ubahlah setiap class yang telah Anda buat dengan code sebagai berikut kemudian
jalankan.

<br>
<p>Monitor.cs</p> 

 ```
using System;
    
namespace TheSuperComputer
{
        class Monitor
        {
            //resolution, supporthdmi, size
            private String resolution;
            private Boolean supportHdmi;
            private double size;
            public Monitor(String resolution, Boolean supportHdmi, double size){
            this.resolution = resolution;
            this.supportHdmi = supportHdmi;
            this.size = size;
        }
            private String getResolution(){
            return this.resolution;
        }
            private Boolean isSupportHdmi(){
            return this.supportHdmi;
        }
            private double getSize(){
            return this.size;
        }
            public override string ToString()
        {
            return $"Monitor resolution: {resolution} ; Monitor support hdmi :
            {supportHdmi}; Monitor dimensi : {size} inch ";
        }
    }
}    
```    
 
<br>
<p>Printer.cs</p>
  
```
using System;
    
namespace TheSuperComputer
{
    class Printer
    {
        private String brand;
        private String series;
        private int ppm;
        public Printer(String brand,String series,int ppm){
        this.brand = brand;
        this.series = series;
        this.ppm = ppm;
    }
        public String getBrand(){
        return this.brand;
    }
        public String getSeries(){
        return this.series;
    }
        public int getPpm(){
        return this.ppm;
    }
        public override string ToString()
    {
        return $"Printer brand : {this.brand} ; Printer series :
        {this.series} ; Printer paper per minutes (ppm) : {this.ppm}";
    }
  }
}
```
    
<br>
<p>Processor.cs</p>
    
```
using System;
    
namespace TheSuperComputer
{
        class Processor

        {
            //processor : series, core, cache
            private String series;
            private int core;
            private int cache;
            public Processor(){
        }
            public void setSeries(String series){
            this.series = series;
        }
            public String getSeries(){
            return this.series;
        }
            public void setCore(int core){
            this.core = core;
        }
            public int getCore(){
            return this.core;
        }
            public void setCache(int cache){
            this.cache = cache;
        }
            public int getCache(){
            return this.cache;
        }
            public override string ToString()
        {
            return $"Processor series:{this.series}; Processor core: {this.core}
            ; Processor cache:{this.cache}";
        }
   }
}
```        

<br>
<p>Ram.cs</p>

```
using System;

namespace TheSuperComputer
{
        class Ram
        {
            //type, speed, memorySize
            private String type;
            private int speed;
            private int memorySize;
            public Ram(String type,int speed,int memorySize){
            this.type = type;
            this.speed = speed;
            this.memorySize = memorySize;
        }
            public String getType(){
            return this.type;
        }
            public int getSpeed(){
            return this.speed;
        }
            public int getMemorySize(){
            return this.memorySize;
        }
            public override string ToString()
        {
            return $"Ram type : {this.type} ; Ram speed : {this.speed} ; Ram
            size :{this.memorySize}";
        }
    }
}
```    

<br>
<p>Vga.cs</p>

```
using System;
    
namespace TheSuperComputer
{
        class Vga
        {
            //brand,graphics clock, memory clock
            private String brand;
            private int graphicsClock;//Mhz
            private int memoryClock;//Mhz
            public Vga(String brand,int graphicsClock, int memoryClock ){
            this.brand = brand;
            this.graphicsClock = graphicsClock;
            this.memoryClock = memoryClock;
        }
            public String getBrand(){
            return this.brand;
        }
            public int getGraphicsClock(){
            return this.graphicsClock;
        }
            public int getMemoryClock(){
            return this.memoryClock;
        }
            public override string ToString()
        {
            return $"Vga brand : {this.brand} ; Vga clock graphics :
            {this.graphicsClock} ; Vga clock memory : {this.memoryClock} ";
        }
    }
}
```

<br>
<p>Computer.cs</p>    
    
```
using System;
    
namespace TheSuperComputer
{
        class Computer
        {
            private Monitor monitor;
            private Printer printer;
            private Processor processor;
            private Ram ram;
            private Vga vga;

            private Computer(Builder builder){
            this.monitor = builder.monitor;
            this.processor = builder.processor;
            this.printer = builder.printer;
            this.ram = builder.ram;
            this.vga = builder.vga;
        }
            public override string ToString()
        {
            return $"Monitor spec :{this.monitor} \n"+
            $"Processor spec : {this.processor} \n"+
            $"Printer spec : {this.printer} \n"+
            $"Vga spec : {this.vga} \n"+
            $"Ram spec : {this.ram}";
        }
            public class Builder{
            public Monitor monitor;
            public Printer printer;
            public Processor processor;
            public Ram ram;
            public Vga vga;
            public Builder(Ram ram,Vga vga, Processor processor){
            this.ram = ram;
            this.vga = vga;
            this.processor = processor;
        }
            public Builder withMonitor(Monitor monitor){
            this.monitor = monitor;

            return this;
        }
            public Builder withPrinter(Printer printer){
            this.printer = printer;
            return this;
        }
            public Computer build(){
            return new Computer(this);
        }
      }
   }
}    
```    
    
<br>
<p>Program.cs</p>
    
```    
using System;
    
namespace TheSuperComputer
{
        class Program
        {
            static void Main(string[] args)
        {
            Monitor lgMonitor = new Monitor("1200x600",true,32);
            Printer hpPrinter = new Printer("HP","MP102",50);
    
            Vga nvdiaVga = new Vga("Nvidia",2054,2054);
            Ram samsungRam = new Ram("DDR4",5000,8000);
            Processor intelProcessor = new Processor();
            intelProcessor.setCache(254);
            intelProcessor.setCore(8);
            intelProcessor.setSeries("CORE i7 8th Gen");
    
            Computer computer = new
            Computer.Builder(samsungRam,nvdiaVga,intelProcessor)//parameter wajib
            .withMonitor(lgMonitor)//parameter opsional
            .withPrinter(hpPrinter)//parameter opsional
            .build();
            Console.WriteLine(computer.ToString());
        }
    }
}    
```    
    
    
    
