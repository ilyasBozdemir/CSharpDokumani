# Karar Yapıları (if, else if, else, switch)

Karar yapları, belirli koşullara göre programın farklı yolları izlemesini sağlar. C# programlamasında yaygın olarak kullanılan karar yapları şunlardır: `if`, `else if`, `else` ve `switch`. Bu bölümde bu karar yaplarını ayrıntılı olarak öğreneceksiniz.

## if İfadesi

`if` ifadesi, belirli bir koşulu kontrol eder ve koşul doğru olduğunda belirli bir kod bloğunu çalıştırır. İşte basit bir örnek:

```csharp

int yas = 18;

if (yas >= 18)
{
    Console.WriteLine("Ehliyet alabilirsiniz.");
}

```
Bu örnekte, if ifadesi, yas değişkeninin 18 veya daha büyük olup olmadığını kontrol eder. Koşul doğru ise "Ehliyet alabilirsiniz." mesajı görüntülenir.

## else if İfadesi

`else if` ifadesi, bir if ifadesiyle başlayan bir koşulu kontrol eder ve ilk koşul yanlışsa ikinci bir koşulu kontrol eder. İşte bir örnek:

```csharp

int puan = 75;

if (puan >= 90)
{
    Console.WriteLine("Aldığınız not: A");
}
else if (puan >= 80)
{
    Console.WriteLine("Aldığınız not: B");
}


```
Bu örnekte, ilk `if` ifadesi puanın 90 veya daha büyük olup olmadığını kontrol eder. Eğer bu koşul yanlışsa, ikinci bir `else if` ifadesi puanın 80 veya daha büyük olup olmadığını kontrol eder.

## else İfadesi

`else` ifadesi, bir `if` ifadesi veya bir dizi `if` ve `else if` ifadesi yanlışsa çalıştırılacak kod bloğunu belirler. İşte bir örnek:
```csharp

int not = 60;

if (not >= 50)
{
    Console.WriteLine("Geçtiniz.");
}
else
{
    Console.WriteLine("Kaldınız.");
}

```
## switch İfadesi

`switch` ifadesi, bir değişkenin değerini kontrol eder ve bu değere göre farklı kod bloklarını çalıştırır. İşte bir örnek:

```csharp

int secim = 2;

switch (secim)
{
    case 1:
        Console.WriteLine("Birinci seçenek seçildi.");
        break;
    case 2:
        Console.WriteLine("İkinci seçenek seçildi.");
        break;
    default:
        Console.WriteLine("Geçersiz seçenek.");
        break;
}


```