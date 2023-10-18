## Asenkron Programlama ve Task

### Asenkron Programlama Nedir?

Asenkron programlama, bir işlemin tamamlanmasını beklemek yerine, işlemin sonucunu beklerken başka işlemlerin yapılmasına olanak tanır. Bu, uygulamaların daha hızlı ve etkili bir şekilde çalışmasını sağlar, özellikle uzun süren işlemlerle başa çıkmak için idealdir. Asenkron programlama, C#'ın modern sürümlerinde Task ve Await anahtar kelimeleri ile kolayca uygulanır.

### Task ve Await

- **Task:** Task, .NET Framework tarafından sunulan bir asenkron işlemi temsil eder. Task, bir işlemin sonucunu beklerken ana iş parçacığının başka işleri yapmasını sağlar.

- **Await:** Await anahtar kelimesi, bir Task'in sonucunu beklemek için kullanılır. Bir Task sonuçlandığında, Await anahtar kelimesi işlemi devralır ve sonucu elde eder.

Örnek:

```csharp
async Task MyMethodAsync()
{
    // Asenkron bir işlem yapılıyor
    await SomeOtherAsyncMethod();
    // İşlem tamamlandığında burası çalışır
}
```
### Paralel Programlama
Paralel programlama, birden fazla işlemi aynı anda çalıştırma yeteneğini ifade eder. C# ve .NET, paralel programlama için Task Parallel Library (TPL) gibi araçlar sunar. Bu sayede işlemci çekirdeklerinin daha etkili bir şekilde kullanılması sağlanır.

## Task Nedir?
Task, C#'ın asenkron programlamayı desteklemek için sunduğu bir yapıdır. Task, bir işlemi temsil eder ve bu işlemin sonucunun tamamlanması beklenirken başka işlemleri devam ettirmenize olanak tanır. Task, .NET Framework ve .NET Core gibi platformlarda kullanılır.
### Task.Run
```csharp
Task.Run(() =>
{
    // Asenkron olarak çalıştırılacak işlem
});
```
Task.Run metodu, bir işlemi asenkron bir şekilde başlatır ve bu işlemi yeni bir Task içinde yürütür.

### Task.Factory.StartNew
```csharp
Task.Factory.StartNew(() =>
{
    // İşlem
});
```
### async/await
```csharp
async Task MyMethodAsync()
{
    // Asenkron olarak çalıştırılacak işlem
}
```
### Task Sonuçları ve Hataları İzleme
```csharp
Task<int> task = Task.Run(() =>
{
    return 42;
});

task.ContinueWith(completedTask =>
{
    int result = completedTask.Result;
    Console.WriteLine("Sonuç: " + result);
});
```
Task sonucunu izlemek için ContinueWith yöntemi kullanılabilir. Bu örnekte, sonucu almak için Result özelliği kullanılır.
Hataları İzleme
```csharp
Task<int> task = Task.Run(() =>
{
    throw new Exception("Bir hata oluştu");
});

task.ContinueWith(completedTask =>
{
    if (completedTask.IsFaulted)
    {
        Console.WriteLine("Hata: " + completedTask.Exception.InnerException.Message);
    }
}, TaskContinuationOptions.OnlyOnFaulted);
```
Hataları izlemek için IsFaulted özelliği kullanılabilir. Hata mesajını almak için Exception.InnerException.Message kullanılır.

Task'lar, asenkron programlama, paralel işlemler ve çoklu iş parçacığı programlaması için güçlü bir araçtır. İş parçacıklarının eşzamanlı olarak çalıştırılmasını sağlamak için kullanılır ve büyük ölçüde işlemci çekirdeklerini etkili bir şekilde kullanmanıza yardımcı olur.