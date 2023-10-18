# Operatörler

Operatörler, C# programlamasında farklı türde işlemler yapmak için kullanılan sembollerdir. C# dilinde birçok operatör türü bulunur ve bunlar, aritmetik işlemler, atama işlemleri, mantıksal işlemler, karşılaştırma işlemleri gibi farklı amaçlar için kullanılırlar.

## Aritmetik Operatörler

Aritmetik operatörler, matematiksel işlemler yapmak için kullanılır. İşte bazı aritmetik operatörler:

- **Toplama (`+`)**: İki sayıyı toplar.
- **Çıkarma (`-`)**: İki sayıyı çıkarır.
- **Çarpma (`*`)**: İki sayıyı çarpar.
- **Bölme (`/`)**: İki sayıyı böler.
- **Modülüs (Kalan) (`%`)**: Bir sayının diğer sayıya bölünmesinden kalanı verir.
- **Artırma (`++`)**: Bir değişkenin değerini bir birim artırır.
- **Azaltma (`--`)**: Bir değişkenin değerini bir birim azaltır.

## Atama Operatörleri

Atama operatörleri, değişkenlere değer atamak için kullanılır. İşte bazı atama operatörleri:

- **Atama (`=`)**: Bir değişkene değer atar.
- **Toplama ile Atama (`+=`)**: Bir değişkeni belirtilen değerle toplar ve sonucu değişkene atar.
- **Çıkarma ile Atama (`-=`)**: Bir değişkeni belirtilen değerle çıkarır ve sonucu değişkene atar.
- **Çarpma ile Atama (`*=`)**: Bir değişkeni belirtilen değerle çarpar ve sonucu değişkene atar.
- **Bölme ile Atama (`/=`)**: Bir değişkeni belirtilen değerle böler ve sonucu değişkene atar.

## Mantıksal Operatörler

Mantıksal operatörler, mantıksal ifadeleri değerlendirmek için kullanılır. İşte bazı mantıksal operatörler:

- **VE (`&&`)**: İki koşulu kontrol eder ve her iki koşul da doğru olduğunda `true` döner.
- **VEYA (`||`)**: İki koşulu kontrol eder ve en az bir koşul doğru olduğunda `true` döner.
- **DEĞİL (`!`)**: Bir koşulu tersine çevirir.

## Karşılaştırma Operatörleri

Karşılaştırma operatörleri, iki değeri karşılaştırmak için kullanılır. İşte bazı karşılaştırma operatörleri:

- **Eşittir (`==`)**: İki değeri karşılaştırır ve değerler eşitse `true` döner.
- **Eşit Değildir (`!=`)**: İki değeri karşılaştırır ve değerler farklı ise `true` döner.
- **Daha Büyük (`>`)**: Sol tarafındaki değer, sağ tarafındaki değerden daha büyükse `true` döner.
- **Daha Küçük (`<`)**: Sol tarafındaki değer, sağ tarafındaki değerden daha küçükse `true` döner.
- **Büyük Eşit (`>=`)**: Sol tarafındaki değer, sağ tarafındaki değere eşit veya daha büyükse `true` döner.
- **Küçük Eşit (`<=`)**: Sol tarafındaki değer, sağ tarafındaki değere eşit veya daha küçükse `true` döner.

Bu bölümde, C# programlamasında kullanılan temel operatörleri öğrendiniz. Operatörler, farklı türde işlemler yapmak için kullanılır ve programlarınızı daha güçlü hale getirmenize yardımcı olur.


### Örnekler

```csharp

int sayi1 = 10;
int sayi2 = 5;
int toplam = sayi1 + sayi2; // toplam şimdi 15
int fark = sayi1 - sayi2; // fark şimdi 5
int carpim = sayi1 * sayi2; // carpim şimdi 50
int bolum = sayi1 / sayi2; // bolum şimdi 2
int kalan = sayi1 % sayi2; // kalan şimdi 0


sayi = 20;// `sayi` değişkenine 20 değerini ata
// atama işlemi sağdan sola olur.

string Ad = "ilyas";
string Soyad = "bozdemir";

string AdSoyad = Ad +" "+ Soyad; // "ilyas bozdemir" cıktısı verir.

```

`++sayi` ve   `sayi++` ifadeleri C# dilinde kullanılan artırma operatörleridir ve farklı sonuçlar üretebilirler. İşte bu iki ifade arasındaki fark:

`sayi++` (Postfix Artırma Operatörü): Değişkenin mevcut değerini kullanır ve sonra artırır.

Örnek kullanım:
```csharp

int sayi = 5;
int sonuc = sayi++; // sonuc = 5, sayi şimdi 6

```
`sayi` değişkenin değeri önce sonuc içine atandı, ardından sayi artırıldı.

`++sayi` (Prefix Artırma Operatörü): Değişkeni önce artırır, sonra değerini kullanır.

Örnek kullanım:

```csharp

int sayi = 5;
int sonuc = ++sayi; // sonuc = 6, sayi şimdi 6

```

## Atama Operatörler


- Atama (`=`): Bir değişkene değer atar.
Örnek kullanım:
```csharp

int sayi = 10;
sayi = 20; // sayi şimdi 20

```

- Toplama ile Atama (`+=`): Bir değişkeni belirtilen değerle toplar ve sonucu değişkene atar.
Örnek kullanım:
```csharp

int sayi = 10;
sayi += 5; // sayi şimdi 15

```

- Çıkarma  ile Atama (`-=`): Bir değişkeni belirtilen değerle toplar ve sonucu değişkene atar.
Örnek kullanım:
```csharp

int sayi = 20;
sayi -= 7; // sayi şimdi 13

```

- Çarpma   ile Atama (`*=`): Bir değişkeni belirtilen değerle çarpar ve sonucu değişkene atar.
Örnek kullanım:
```csharp

int sayi = 5;
sayi *= 4; // sayi şimdi 20

```
- Bölme    ile Atama (`/=`): Bir değişkeni belirtilen değerle böler ve sonucu değişkene atar.
Örnek kullanım:
```csharp

int sayi = 30;
sayi /= 3; // sayi şimdi 10

```
