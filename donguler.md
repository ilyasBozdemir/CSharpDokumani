# Döngüler

Döngüler, C# programlamasında belirli bir işlemi tekrarlamak için kullanılan yapılardır. C# dilinde yaygın olarak kullanılan dört tür döngü bulunur: `for`, `while`, `do-while` ve `foreach`. İşte her bir döngü türünün açıklamaları ve örnekleri:

## for Döngüsü

`for` döngüsü, belirli bir koşul sağlandığı sürece bir kod bloğunu tekrarlar. Ayrıca bir sayacı artırarak veya azaltarak kullanılır. İşte bir örnek:

```csharp
for (int i = 0; i < 5; i++)
{
    Console.WriteLine("Döngü İterasyonu #" + i);
}
```

## do  Döngüsü

`while` döngüsü, belirli bir koşul sağlandığı sürece bir kod bloğunu tekrarlar. İşte bir örnek: İşte bir örnek:

```csharp
int sayac = 0;
do
{
    Console.WriteLine("Döngü İterasyonu #" + sayac);
    sayac++;
} while (sayac < 5);

```

## do while  Döngüsü

`do-while` döngüsü, bir kod bloğunu en az bir kez çalıştırmak istediğinizde kullanılır. Kod bloğu çalıştırıldıktan sonra koşul kontrol edilir ve koşul sağlandığı sürece döngü tekrarlanır.  İşte bir örnek:

```csharp
int sayac = 0;
do
{
    Console.WriteLine("Döngü İterasyonu #" + sayac);
    sayac++;
} while (sayac < 5);

```
## do while  Döngüsü

`do-while` döngüsü, bir kod bloğunu en az bir kez çalıştırmak istediğinizde kullanılır. Kod bloğu çalıştırıldıktan sonra koşul kontrol edilir ve koşul sağlandığı sürece döngü tekrarlanır.  İşte bir örnek:

```csharp
int sayac = 0;
do
{
    Console.WriteLine("Döngü İterasyonu #" + sayac);
    sayac++;
} while (sayac < 5);

```
## foreach  Döngüsü

`foreach` döngüsü, bir koleksiyonun (dizi, liste vb.) her elemanı için bir kod bloğunu   İşte bir örnek:

```csharp
string[] meyveler = { "Elma", "Armut", "Muz" };
foreach (string meyve in meyveler)
{
    Console.WriteLine("Meyve: " + meyve);
}
```
Bu örnekte, foreach döngüsü, meyveler dizisindeki her meyve için bir iterasyon yapar ve meyveleri ekrana yazdırır.

Döngüler, C# programlamasının temel bir parçasıdır ve öğrenmeleri önemlidir.