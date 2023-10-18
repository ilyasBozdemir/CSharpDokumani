# İstisnalar ve Hata Yönetimi

Bu bölüm, C# programlamasında hata yönetimi ve istisnaların nasıl ele alınacağını anlatır.

## İstisna Nedir?

- **İstisna Kavramı**: İstisna, bir programın normal akışının dışında meydana gelen olağan dışı bir durumu temsil eder. Bu bölüm, istisnaların neden meydana geldiğini ve nasıl ele alınması gerektiğini açıklar.

```csharp
try
{
    int[] dizi = { 1, 2, 3 };
    Console.WriteLine(dizi[4]); // Dizi sınırlarının dışında bir elemanı erişmeye çalışmak istisna yaratır.
}
catch (Exception ex)
{
    Console.WriteLine("Hata yakalandı: " + ex.Message);
}

```

## Try-Catch Blokları

- **Try-Catch İfadesi**: Try-Catch blokları, bir kod parçasının çalışması sırasında meydana gelebilecek istisnaları ele alır. Bu bloklar sayesinde programın çökmesi önlenir.


```csharp
try
{
    int sayi = 10;
    int sifir = 0;
    int sonuc = sayi / sifir; // Bölme işlemi sırasında bir istisna meydana gelir.
}
catch (DivideByZeroException ex)
{
    Console.WriteLine("Sıfıra bölme hatası: " + ex.Message);
}

```


## Özel İstisnalar Oluşturma

- **Özel İstisna Sınıfları**: Programcılar, kendi özel istisna sınıflarını oluşturabilirler. Bu, belirli hataları daha iyi tanımlamak ve ele almak için kullanışlıdır.

```csharp
public class GecersizYasIstisnasi : Exception
{
    public GecersizYasIstisnasi(string mesaj) : base(mesaj)
    {
    }
}

public class Ogrenci
{
    private int yas;

    public int Yas
    {
        get { return yas; }
        set
        {
            if (value < 0 || value > 150)
            {
                throw new GecersizYasIstisnasi("Geçersiz yaş değeri: " + value);
            }
            yas = value;
        }
    }
}


```

## finally Bloğu

- **finally Bloğu**: Finally bloğu, bir try-catch bloğundan bağımsız olarak çalışır. Kaynakları serbest bırakmak ve temizlemek için kullanılır.

```csharp

FileStream dosya = null;
try
{
    dosya = new FileStream("dosya.txt", FileMode.Open);
    // Dosya üzerinde işlemler yapılır.
}
catch (IOException ex)
{
    Console.WriteLine("Hata: " + ex.Message);
}
finally
{
    if (dosya != null)
    {
        dosya.Close(); // Dosyayı kapat
    }
}

```

## Hata Ayıklama Teknikleri

- **Hata Ayıklama Araçları**: C# geliştirirken hataları ayıklamak için kullanabileceğiniz araçları tanır. Visual Studio gibi entegre geliştirme ortamları (IDE) bu süreci kolaylaştırır.

İstisnaların doğru bir şekilde ele alınması, yazılımın daha güvenilir ve sağlam olmasına yardımcı olur. Bu bölüm, istisnaları nasıl yakalayacağınızı, ele alacağınızı ve hata ayıklama tekniklerini kullanacağınızı öğretir.

