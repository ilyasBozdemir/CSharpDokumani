# Fonksiyonlar ve Metodlar

Bu bölümde, C# programlamasında fonksiyonlar ve metotlar hakkında detaylı bilgi bulacaksınız.

## Metot Tanımlama ve Çağırma

- **Metot Tanımlama**: Metotlar, belirli bir işlemi veya işlevi gerçekleştirmek için kullanılır. Bu bölüm, metotların nasıl tanımlanacağını ve yapılacağını anlatır.

- **Metot Çağırma**: Tanımlanan metotlar, programın başka bölümlerinde çağrılabilir. Bir metot nasıl çağrılır ve çağrılırken nasıl argümanlar iletilir açıklanır.

## Parametreler ve Argümanlar

- **Parametre Tanımlama**: Metotlar, parametreler aracılığıyla giriş verilerini alabilirler. Bu bölüm, metotlara nasıl parametre ekleyeceğinizi gösterir.

- **Argümanlar**: Metotları çağırırken, belirli değerler veya ifadeler iletilir. Bu değerler, metotun parametreleri ile eşleşmelidir.

## Dönüş Değerleri

- **Dönüş Değeri**: Metotlar, genellikle bir değer döndürürler. Bu bölüm, metotların nasıl bir dönüş değeri verebileceğini açıklar.

## Metot Aşırı Yükleme (Overloading)

- **Metot Aşırı Yükleme**: Aynı isme sahip farklı parametre listelerine sahip birden fazla metot tanımlayabilirsiniz. Bu, metotların aşırı yüklendiği anlamına gelir.

## Yerel Değişkenler ve Kapsam

- **Yerel Değişkenler**: Metotlar içinde tanımlanan değişkenlere "yerel değişkenler" denir. Bu değişkenler sadece metot içinde kullanılabilir.

- **Kapsam (Scope)**: Bir değişkenin kullanılabilirliği kapsam ile sınırlıdır. Bu bölüm, değişkenlerin nasıl kapsamlarını belirlediğinizi açıklar.

Metotlar, C# programlamasında önemli bir rol oynar ve kodunuzu daha modüler ve okunaklı hale getirmenize yardımcı olur. Bu bölümde metotların tanımlanması, çağrılması ve kullanılması hakkında ayrıntılı bilgi edineceksiniz.


##  Metot Tanımlama ve Çağırma

```csharp
public class HesapMakinesi
{
    public int Topla(int sayi1, int sayi2)
    {
        return sayi1 + sayi2;
    }
}

class Program
{
    static void Main()
    {
        HesapMakinesi hesapMakinesi = new HesapMakinesi();
        int sonuc = hesapMakinesi.Topla(5, 3);
        Console.WriteLine("Toplam: " + sonuc);
    }
}
```

## Parametreler ve Argümanlar

```csharp
public void SelamVer(string isim)
{
    Console.WriteLine("Merhaba, " + isim + "!");
}

class Program
{
    static void Main()
    {
        SelamVer("Ahmet");
    }
}

```
## Dönüş Değerleri

```csharp
public int KareAl(int sayi)
{
    return sayi * sayi;
}

class Program
{
    static void Main()
    {
        int sonuc = KareAl(4);
        Console.WriteLine("Kare: " + sonuc);
    }
}
```
## Metot Aşırı Yükleme (Overloading)

```csharp
public int Topla(int sayi1, int sayi2)
{
    return sayi1 + sayi2;
}

public double Topla(double sayi1, double sayi2)
{
    return sayi1 + sayi2;
}
```
## Yerel Değişkenler ve Kapsam

```csharp
public void KapsamOrnegi()
{
    int x = 10;  // x, sadece KapsamOrnegi metodu içinde erişilebilir.
    
    if (true)
    {
        int y = 20;  // y, bu if bloğu içinde tanımlanmıştır.
        Console.WriteLine(x);  // x kullanılabilir.
        Console.WriteLine(y);  // y kullanılabilir.
    }
    
    Console.WriteLine(x);  // x hala kullanılabilir.
    // Console.WriteLine(y);  // y burada kullanılamaz; kapsam dışında.
}

class Program
{
    static void Main()
    {
        KapsamOrnegi();
    }
}

```