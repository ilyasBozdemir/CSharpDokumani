# Diziler (Arrays)

Diziler, C# programlamasında aynı türde veri öğelerini içeren koleksiyonlardır. Diziler, birden çok öğeyi depolamak ve bu öğelere indeksler aracılığıyla erişmek için kullanılır. İşte diziler hakkında bilmeniz gereken temel kavramlar:

## Dizi Tanımı

Dizi tanımı, bir dizi değişkenin oluşturulmasını içerir. Dizi oluşturulurken, dizinin boyutu ve türü belirtilmelidir. Örnek bir dizi tanımı:

```csharp
int[] sayilar = new int[5];
```
Bu örnekte, 5 elemanlı bir tamsayı dizisi (int) oluşturulur. Dizi, varsayılan değerlerle başlatılır (0'lar).

## Dizi Elemanlarına Erişim
Dizi elemanlarına erişim için endeksler kullanılır. Dizi endeksleri 0'dan başlar. Örneğin, dizinin ilk elemanına erişmek için sayilar[0] kullanılır.

```csharp
int ilkEleman = sayilar[0];
```
## Dizi İndeksleri
Dizi indeksleri, 0'dan başlar ve dizinin boyutuna (eleman sayısına) kadar gider. Örneğin, 5 elemanlı bir dizi için indeksler 0, 1, 2, 3 ve 4 olabilir.
## Dizi İnitilizasyonu
Diziye başlangıç değerleri atamak için dizi inisiyasyonu kullanılabilir. Örneğin:

```csharp
int[] sayilar = new int[] { 1, 2, 3, 4, 5 };
```
Bu örnekte, 5 elemanlı bir tamsayı dizisi oluşturulur ve elemanlara sırasıyla 1, 2, 3, 4 ve 5 değerleri atanır.
## Dizi Uzunluğu
Dizi uzunluğunu belirlemek için Length özelliği kullanılır. Örneğin:
```csharp
int uzunluk = sayilar.Length;
```
Bu örnekte, uzunluk değişkeni, sayilar dizisinin eleman sayısını içerecektir.
## Dizi Döngüleri
Döngüler, dizinin tüm elemanları üzerinde işlem yapmak için kullanılır. Örneğin, for döngüsü kullanarak tüm dizi elemanlarını yazdırmak için:
```csharp
for (int i = 0; i < sayilar.Length; i++)
{
    Console.WriteLine(sayilar[i]);
}
```
Bu döngü, dizinin her elemanını endeksleri kullanarak sırayla yazdırır.

Diziler, aynı türdeki verileri gruplamak ve işlemek için kullanışlı veri yapılarıdır. Çeşitli işlemlerde kullanılırlar ve programların veri yönetiminde önemli bir rol oynarlar.
