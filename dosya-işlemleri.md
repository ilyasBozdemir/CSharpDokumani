# 9. Dosya İşlemleri

## Dosya Okuma
Dosya okuma işlemi, bir dosyadan veri okuma işlemidir. Aşağıda, bir metin dosyasını okuma işlemini gösteren bir örnek bulunmaktadır:

```csharp
using System;
using System.IO;

class Program
{
    static void Main()
    {
        string dosyaYolu = "metin.txt";

        if (File.Exists(dosyaYolu))
        {
            string metin = File.ReadAllText(dosyaYolu);
            Console.WriteLine("Dosya İçeriği: ");
            Console.WriteLine(metin);
        }
        else
        {
            Console.WriteLine("Dosya bulunamadı.");
        }
    }
}
```
## Dosya Yazma
Dosya yazma işlemi, bir dosyaya veri yazma işlemidir. Aşağıda, bir metin dosyasına veri yazma işlemini gösteren bir örnek bulunmaktadır:
```csharp
using System;
using System.IO;

class Program
{
    static void Main()
    {
        string dosyaYolu = "yeni_metin.txt";
        string metin = "Bu bir metin dosyasına yazılan veridir.";

        File.WriteAllText(dosyaYolu, metin);

        Console.WriteLine("Dosya yazma işlemi tamamlandı.");
    }
}
```
## Dosya Yönetimi
Dosya yönetimi, dosyaların oluşturulması, taşınması, silinmesi vb. işlemleri içerir. Aşağıda, bir dosyanın nasıl oluşturulduğunu ve silindiğini gösteren örnekler bulunmaktadır:
```csharp
string dosyaAdi = "yeni_dosya.txt";
File.Create(dosyaAdi);
Console.WriteLine("Dosya oluşturuldu: " + dosyaAdi);
```
# Dosya Yönetimi
Dosya yönetimi, dosyaların oluşturulması, taşınması, silinmesi vb. işlemleri içerir. Aşağıda, bir dosyanın nasıl oluşturulduğunu ve silindiğini gösteren örnekler bulunmaktadır:

## Dosya Oluşturma
```csharp
string dosyaAdi = "yeni_dosya.txt";
File.Create(dosyaAdi);
Console.WriteLine("Dosya oluşturuldu: " + dosyaAdi);
```
## Dosya Silme
```csharp
string dosyaAdi = "silinecek_dosya.txt";
if (File.Exists(dosyaAdi))
{
    File.Delete(dosyaAdi);
    Console.WriteLine("Dosya silindi: " + dosyaAdi);
}
else
{
    Console.WriteLine("Silinecek dosya bulunamadı.");
}
```
# Akışlar (Streams)
Akışlar, dosyalarla veya diğer kaynaklarla veri okuma ve yazma işlemleri için kullanılır. Aşağıda, bir dosyadan veri okuma ve dosyaya veri yazma işlemini gösteren örnekler bulunmaktadır:

## Dosyadan Veri Okuma
```csharp
using System;
using System.IO;

class Program
{
    static void Main()
    {
        string dosyaYolu = "metin.txt";

        using (FileStream fs = new FileStream(dosyaYolu, FileMode.Open))
        using (StreamReader reader = new StreamReader(fs))
        {
            string satir;
            while ((satir = reader.ReadLine()) != null)
            {
                Console.WriteLine(satir);
            }
        }
    }
}
```

## Dosyaya Veri Yazma
```csharp
using System;
using System.IO;

class Program
{
    static void Main()
    {
        string dosyaYolu = "yeni_metin.txt";
        string metin = "Bu bir metin dosyasına yazılan veridir.";

        using (FileStream fs = new FileStream(dosyaYolu, FileMode.Create))
        using (StreamWriter writer = new StreamWriter(fs))
        {
            writer.Write(metin);
        }

        Console.WriteLine("Dosyaya yazma işlemi tamamlandı.");
    }
}
```
## Dosya İzinleri
```csharp
using System;
using System.IO;

class Program
{
    static void Main()
    {
        string dosyaYolu = "izin_verilen_dosya.txt";

        if (File.Exists(dosyaYolu))
        {
            File.SetAttributes(dosyaYolu, FileAttributes.Normal);
            Console.WriteLine("Dosya izinleri sıfırlandı.");
        }
        else
        {
            Console.WriteLine("Dosya bulunamadı.");
        }
    }
}
```

