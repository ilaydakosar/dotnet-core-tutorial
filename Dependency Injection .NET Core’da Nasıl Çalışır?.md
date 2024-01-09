.NET Core'da Dependency Injection (DI), nesne oluşturma ve bağımlılık yönetimi sürecini soyutlayarak, sınıflar arası bağımlılıkları azaltır ve modüler, test edilebilir kod yazmayı kolaylaştırır.

<h3>Dependency Injection'ın Temel Prensipleri</h3>
Bağımlılıkların Yönetimi: DI, bir sınıfın diğer sınıflara veya servislere olan bağımlılıklarını dışarıdan sağlar. Bu, sınıfların birbirine sıkı sıkıya bağlanmasını (tight coupling) önler.<br>
<br>
Inversion of Control (IoC) Prensibi: IoC, uygulamanın akış kontrolünün geliştiriciden alınıp bir çerçeveye (framework) verilmesidir. DI, IoC'nin bir uygulamasıdır; burada nesne oluşturma ve 
bağımlılık çözümleme görevleri çerçeveye devredilir.
<br><br>
Servis Konteyneri: .NET Core, bir servis konteyneri (örneğin, IServiceCollection) kullanarak bağımlılıkları yönetir. Geliştiriciler, bu konteynerde uygulamada kullanılacak servisleri tanımlar ve kaydeder.

<h3>Dependency Injection'ın Uygulanması</h3>
Servis Kaydı: Geliştiriciler, uygulamanın ihtiyaç duyduğu servisleri Startup sınıfının ConfigureServices metodunda tanımlar ve kaydeder. Bu servisler daha sonra uygulama boyunca kullanılabilir.
<br><br>
Yaşam Döngüsü Seçenekleri: Servisler, singleton, scoped veya transient olarak kaydedilebilir. Singleton servisler uygulama boyunca tek bir örnek olarak kalır, scoped servisler her istek için yeniden oluşturulur,
transient servisler ise her kullanımda yeni bir örnek olarak üretilir.
<br><br>
Bağımlılıkların Enjekte Edilmesi: DI, bağımlılıkları nesnelere, genellikle yapıcı metotlar (constructors) aracılığıyla otomatik olarak enjekte eder. Bu, sınıfların bağımlılıklarını dışarıdan almasını ve daha 
modüler yapıda olmasını sağlar.

Test Edilebilirlik: DI, mock nesneleri veya test çiftleri kullanarak birim testlerinin kolaylıkla yazılabilmesini sağlar. Gerçek bağımlılıklar, test sırasında bu sahte nesnelerle değiştirilebilir.


Dependency Injection, .NET Core'da uygulama geliştirme sürecini basitleştiren ve kod kalitesini artıran önemli bir özelliktir. Bağımlılıkların dışarıdan enjekte edilmesi sayesinde, sınıflar arasındaki 
bağlantı azalır ve sistem daha esnek hale gelir. Bu yaklaşım, büyük ve karmaşık uygulamaların yönetimini kolaylaştırır ve yazılımın genel bakımını ve test edilebilirliğini iyileştirir.

Adım 1: Servis Arayüzü ve Uygulaması
İlk olarak, bir loglama servisi arayüzü ve bu arayüzü uygulayan bir sınıf oluşturun:

![image](https://github.com/ilaydakosar/dotnet-core-tutorial/assets/55831435/a65825ef-a6c6-4364-a603-e0c8511a31fb)

Adım 2: Startup.cs'te Servisi Kaydetme
Startup.cs dosyasında, ConfigureServices metodunu kullanarak bu servisi DI konteynerine kaydedin:

![image](https://github.com/ilaydakosar/dotnet-core-tutorial/assets/55831435/95231632-edae-4d9c-977a-15128b3bd10d)

Bu örnekte, ConsoleLoggingService'i ILoggingService olarak geçici (transient) bir servis olarak kaydediyoruz. Bu, ILoggingService tipinde bir bağımlılık istendiğinde her seferinde ConsoleLoggingService'in yeni bir örneği oluşturulacağı anlamına gelir.

![image](https://github.com/ilaydakosar/dotnet-core-tutorial/assets/55831435/95ea43dd-d7ed-4d58-b35c-106ce2f1900b)

Bu controller sınıfında, ILoggingService türünde bir bağımlılık enjekte edilmiş ve Index aksiyonu içinde kullanılmıştır. .NET Core, bu controller örneği oluşturulduğunda ILoggingService bağımlılığını otomatik olarak enjekte eder.

