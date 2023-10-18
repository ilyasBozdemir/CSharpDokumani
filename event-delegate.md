## Etkinlikler (Events)

Etkinlikler, C#'ın nesne yönelimli programlama modelinde önemli bir rol oynar. Etkinlikler, bir nesnenin belirli bir durumunda veya olayında başka kodun tetiklenmesine izin verir. Kullanıcı etkileşimleri, düğme tıklamaları veya dosya değişiklikleri gibi senaryolarda yaygın olarak kullanılırlar. Etkinlikleri tanımlamak, abone olmak ve etkinlikleri tetiklemek için C# dilinin sunduğu sözdizimini ve nesne modelini açıklar.



```csharp
using System;

public class Dugme
{
    // Etkinlik tanımı
    public event Action Tiklandi;

    public void TiklandiMi()
    {
        // Etkinliği tetikle
        Tiklandi?.Invoke();
    }
}

public class Program
{
    public static void Main()
    {
        Dugme btn = new Dugme();

        // Etkinlik dinleyicisi ekleyin
        btn.Tiklandi += () => Console.WriteLine("Düğmeye tıklandı!");

        // Düğmeye tıklanınca etkinlik tetiklenir
        btn.TiklandiMi();
    }
}

```


## Delegeler

Delegeler, C# programlamasında işlevleri bir nesne gibi temsil etmek için kullanılır. Delegeler, bir metodu başka metotlara parametre olarak iletmek, dinamik olarak metotları çağırmak veya olayları ele almak için kullanışlıdır. Delegelerin nasıl tanımlandığı, nasıl kullanıldığı ve olay işleme için nasıl kullanılabileceği açıklanır.

```csharp

using System;

public class HesapMakinesi
{
    public delegate int HesapMetodu(int x, int y);

    public int Topla(int a, int b)
    {
        return a + b;
    }

    public int Carp(int a, int b)
    {
        return a * b;
    }
}

public class Program
{
    public static void Main()
    {
        HesapMakinesi hesapMakinesi = new HesapMakinesi();

        HesapMakinesi.HesapMetodu hesapla = hesapMakinesi.Topla;
        int sonuc = hesapla(5, 3);
        Console.WriteLine("Toplam: " + sonuc);
    }
}

```

## Asenkron Programlama

Asenkron programlama, uzun süre çalışan işlemleri bloke etmeden yürütmek için C#'ın modern özelliklerinden biridir. Asenkron metotlar, ağ çağrıları, dosya işlemleri ve diğer yoğun işlem gerektiren görevleri işlemek için idealdir. C#'da asenkron programlama için kullanılan anahtar kavramlar, `async` ve `await` anahtar kelimeleri ve asenkron programlamanın nasıl uygulandığı anlatılır.



```csharp

using System;
using System.Threading.Tasks;

public class Program
{
    public static async Task Main()
    {
        Console.WriteLine("Başlangıç.");

        await Task.Delay(2000); // 2 saniye boyunca işlem durur

        Console.WriteLine("Bekleme sona erdi.");

        await Task.Run(() =>
        {
            // Uzun sürecek işlemi simüle et
            Task.Delay(3000).Wait();
        });

        Console.WriteLine("Uzun işlem tamamlandı.");
    }
}


```

## C# 9 ve Sonraki Sürümler

C#, sürekli olarak geliştirilen bir programlama dili olarak devam eder. Her yeni sürüm, dilin yeteneklerini genişletir, hata ayıklama ve performans iyileştirmeleri sağlar. C# 9 ve sonraki sürümlerde tanıtılan yeni özellikler, dilin gelişen yüzünü anlatır ve bu özelliklerin nasıl kullanılacağını açıklar.


## Event ve Delegate Kullanımı Windows Forms Uygulamalarında

Windows Forms, masaüstü uygulamaları geliştirmek için kullanılan bir teknolojidir ve kullanıcı etkileşimlerini işlemek için olaylara (events) dayalı bir model sunar. `event` ve `delegate` yapıları, Windows Forms uygulamalarında olay işleme (event handling) için önemlidir. İşte bu yapıların kullanımının öne çıktığı bazı noktalar:

- **Olay İşleme:** Windows Forms uygulamaları, kullanıcı etkileşimlerini işlemek için olayları kullanır. Örneğin, bir düğmeye tıklama işlemi bir olaydır. `event` ve `delegate` yapıları, bu olayları dinlemek ve işlemek için kullanılır. Olaylar, kullanıcının uygulama ile etkileşimde bulunmasını sağlar.

- **Özel Olaylar (Custom Events):** Windows Forms geliştiricileri özel olaylar tanımlayabilir. Özel olaylar, uygulamanın özel durumlarını veya kullanıcı etkileşimlerini işlemek için kullanılır. Bu, uygulamanın daha fazla kontrol ve esneklik sağlar.

- **Olay İşleyiciler (Event Handlers):** Olaylar, bu olayları dinlemek ve işlemek için olay işleyicilerine ihtiyaç duyar. Olay işleyicileri, belirli bir olayın tetiklendiğinde gerçekleşecek eylemleri tanımlar.

- **Çoklu İş Parçacığı (Multithreading):** Windows Forms uygulamaları genellikle çoklu iş parçacığı kullanır. Bu durumda, `Invoke` ve `BeginInvoke` gibi yöntemlerle olay işleyicileri ana iş parçacığına iletilir.

Windows Forms uygulamalarının kullanıcı arayüzü etkileşimlerini işlemek için `event` ve `delegate` yapıları, geliştiricilere güçlü bir araç seti sunar. Bu yapılar, uygulamaların kullanıcılarla etkileşimde bulunmasını ve daha iyi bir kullanıcı deneyimi sağlamasını kolaylaştırır.


örnek kodlama

```csharp
using System;

public class Otomobil
{
    public string Marka { get; set; }
    public string Model { get; set; }
    public int Hiz { get; private set; }

    // Hız limiti için bir olay tanımlama
    public event EventHandler HizAsimi;

    public Otomobil(string marka, string model)
    {
        Marka = marka;
        Model = model;
        Hiz = 0;
    }

    public void HiziArtir(int artisMiktari)
    {
        Hiz += artisMiktari;

        // Hız limitini kontrol et
        if (Hiz > 120)
        {
            Console.WriteLine($"{Marka} {Model}, hız sınırını aştı!");
            // Hız limiti aşıldığında HizAsimi olayını tetikle
            OnHizAsimi();
        }
    }

    protected virtual void OnHizAsimi()
    {
        // HızAsimi olayına abone olan bir normal method
        HizAsimiHandler();
    }

    // HizAsimi olayına abone olan normal method
    private void HizAsimiHandler()
    {
        Console.WriteLine("Hız sınırı aşıldı!");
    }
}

public class Program
{
    public static void Main()
    {
        Otomobil otomobil = new Otomobil("Audi", "A3");

        // HızAsimi olayına abone ol
        otomobil.HizAsimi += otomobil.HizAsimiHandler;

        otomobil.HiziArtir(100);
        otomobil.HiziArtir(30);
        otomobil.HiziArtir(10);
    }
}


```

şimdi de windows form application içinde ki bir evente benzer yapı yazalım.

```csharp
using System;
using System.Windows.Forms;

public class MainForm : Form
{
    private Button myButton;

    public MainForm()
    {
        myButton = new Button();
        myButton.Text = "Tıkla";
        myButton.Click += new EventHandler(Button_Click); // Olaya abone ol

        Controls.Add(myButton);
    }

    private void Button_Click(object sender, EventArgs e)
    {
        MessageBox.Show("Butona tıklandı!");
    }

    [STAThread]
    public static void Main()
    {
        Application.EnableVisualStyles();
        Application.SetCompatibleTextRenderingDefault(false);

        Application.Run(new MainForm());
    }
}

```
bu kod örneğinin temelinde event ve delegate vardır.