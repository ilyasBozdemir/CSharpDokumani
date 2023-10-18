# Nesne Yönelimli Programlama

Bu bölüm, C# programlamasında nesne yönelimli programlamanın temel kavramlarını ve ileri düzey konularını içerir.

## Sınıf ve Nesne Tanımlama

- **Sınıf Tanımlama**: Sınıflar, nesnelerin şablonlarını tanımlar. Bu bölüm, sınıfların nasıl tanımlandığını ve içerdikleri özellikleri ve metotları nasıl belirttiğinizi açıklar.

- **Nesne Oluşturma**: Sınıfın bir örneği olan nesneler, gerçek dünyadaki varlıkları temsil eder. Bu bölüm, sınıfın nesnelerini nasıl oluşturacağınızı gösterir.


```csharp
public class Araba
{
    public string Marka { get; set; }
    public string Model { get; set; }

    public void Calistir()
    {
        Console.WriteLine("Araba çalışıyor.");
    }
}

class Program
{
    static void Main()
    {
        Araba araba1 = new Araba();
        araba1.Marka = "Toyota";
        araba1.Model = "Corolla";

        araba1.Calistir();
    }
}

```

## Kalıtım (Inheritance)

- **Kalıtım Kavramı**: Kalıtım, bir sınıfın başka bir sınıftan özelliklerini ve metotlarını devralmasıdır. Bu, sınıflar arasında bir "is-a" ilişkisi oluşturur. Bu bölüm, kalıtımın nasıl kullanılacağını ve uygulanacağını açıklar.

```csharp
public class EvcilHayvan
{
    public string Ad { get; set; }

    public void SesCikar()
    {
        Console.WriteLine("Evci hayvan sesi");
    }
}

public class Kedi : EvcilHayvan
{
    public Kedi()
    {
        Ad = "Minnoş";
    }

    public void Miyavla()
    {
        Console.WriteLine("Miyav!");
    }
}

class Program
{
    static void Main()
    {
        Kedi kedi = new Kedi();
        Console.WriteLine(kedi.Ad);
        kedi.Miyavla();
        kedi.SesCikar();
    }
}
```


## Kapsülleme (Encapsulation)

- **Kapsülleme İlkesi**: Kapsülleme, sınıfın iç verilerini ve işlevselliğini dış dünyadan gizlemeyi amaçlar. Bu, güvenli ve düzenli bir kod geliştirmeye yardımcı olur. Bu bölüm, kapsüllemenin nasıl uygulanacağını anlatır.

```csharp

```


## Polimorfizm (Polymorphism)

- **Polimorfizm Kavramı**: Polimorfizm, farklı sınıfların aynı arayüzü veya metotları kullanarak aynı işlevi gerçekleştirmesini sağlar. Bu, kodun daha esnek ve genişletilebilir olmasını sağlar. Bu bölüm, polimorfizmin nasıl çalıştığını gösterir.


```csharp

public class Sekil
{
    public virtual void Ciz()
    {
        Console.WriteLine("Şekil çizildi.");
    }
}

public class Daire : Sekil
{
    public override void Ciz()
    {
        Console.WriteLine("Daire çizildi.");
    }
}

public class Kare : Sekil
{
    public override void Ciz()
    {
        Console.WriteLine("Kare çizildi.");
    }
}

class Program
{
    static void Main()
    {
        Sekil sekil1 = new Daire();
        Sekil sekil2 = new Kare();

        sekil1.Ciz();  // Daire çizildi.
        sekil2.Ciz();  // Kare çizildi.
    }
}

```


## Arabirimler (Interfaces)

- **Arabirimlerin Kullanımı**: Arabirimler, farklı sınıfların aynı metotları uygulamasını sağlayan bir sözleşmedir. Bu, kodun sık kullanılan işlevleri paylaşmasına olanak tanır. Bu bölüm, arabirimlerin nasıl tanımlandığını ve uygulandığını açıklar.

Nesne yönelimli programlama, karmaşık yazılımlar geliştirmek için güçlü bir paradigmadır. Bu bölümde bu paradigmanın temel kavramlarını ve kullanımını öğreneceksiniz.

```csharp

public interface IDosya
{
    void DosyaAc();
    void DosyaKaydet();
}

public class MetinEditoru : IDosya
{
    public void DosyaAc()
    {
        Console.WriteLine("Metin dosyası açıldı.");
    }

    public void DosyaKaydet()
    {
        Console.WriteLine("Metin dosyası kaydedildi.");
    }
}

class Program
{
    static void Main()
    {
        IDosya editor = new MetinEditoru();
        editor.DosyaAc();
        editor.DosyaKaydet();
    }
}


```

## Abstract Sınıflar
Abstract sınıflar, bir sınıfın soyut (abstract) methodları içerebildiği sınıflardır. Bir abstract sınıf, kendisinden türetilen sınıflar için bir temel sınıf (base class) görevi görür. İşte abstract sınıfların temel özellikleri:

- Soyut sınıflar soyut methodlar (gövdesiz methodlar) içerebilir.
- Abstract sınıflardan nesne oluşturulamaz, yani abstract sınıfların örneği (instance) alınamaz.
- Bir sınıf sadece bir abstract sınıfı kalıtım alabilir (inherit).
- Abstract sınıflar, kalıtım alan sınıflara, soyut methodları uygulama (override) zorunluluğu getirebilir.
Örnek bir abstract sınıf tanımı:

```csharp
public abstract class Sekil
{
    public abstract double AlanHesapla();
}


```

## Sealed Class (Mühürlü Sınıf)
Sealed classlar, başka sınıfların bu sınıfı miras almasını (inherit) önleyen sınıflardır. Sealed classlar genellikle kalıtımı (inheritance) sınırlamak ve sınıflarınızın kontrolünü sağlamak için kullanılır.

Örnek bir abstract sınıf tanımı:

```csharp
public sealed class MuhurluSinif
{
    // ...
}
```
## Partial Class (Kısmi Sınıf)
Partial classlar, sınıfın tanımını birden çok dosyada paylaşmanıza olanak tanır. Bu, büyük sınıfları daha yönetilebilir ve okunabilir hale getirir. Genellikle otomatik kod oluşturma araçlarıyla kullanılırlar.

Partial Class Windows Form App üzerinde de vardır 

Örnek bir abstract sınıf tanımı:

```csharp
public partial class KismiSinif
{
    // ...
}

public partial class KismiSinif
{
    // ...
}

```

