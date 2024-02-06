
Asenkron programlama, bir programın birden fazla işlemi aynı anda yapmasına olanak tanır. .NET Core'da bu, async ve await anahtar kelimeleri ile gerçekleştirilir.
Async bir metodun asenkron olduğunu belirtirken, await ise asenkron bir işlemin tamamlanmasını bekler.

Async ve Await Kullanımı
Bir metodu asenkron yapmak için, metod imzasına async anahtar kelimesi eklenir ve dönüş tipi genellikle Task veya Task< T > olur. Örnek:

![image](https://github.com/ilaydakosar/dotnet-core-tutorial/assets/55831435/4412c689-735d-4961-b192-a068a2f303af)

await anahtar kelimesi, asenkron bir işlemin tamamlanmasını beklemek için kullanılır. Örnek:

![image](https://github.com/ilaydakosar/dotnet-core-tutorial/assets/55831435/603d6504-db5a-48ac-9021-ce875725f4da)

Asenkron Metodların Oluşturulması

Asenkron metodlar, ağ çağrıları, dosya işlemleri veya uzun süren herhangi bir işlem için kullanılabilir. Örnek olarak bir dosyadan veri okuma işlemi:

![image](https://github.com/ilaydakosar/dotnet-core-tutorial/assets/55831435/ed86a077-622b-4e2b-b352-1bbf6f3d84a2)

Hata Yönetimi
Asenkron programlamada hata yönetimi, senkron programlamaya benzer şekilde yapılır. Ancak, try-catch blokları asenkron metodlar içinde kullanılmalıdır:

![image](https://github.com/ilaydakosar/dotnet-core-tutorial/assets/55831435/368c556e-c07d-4af2-a74a-2d599e7c8857)

NET Core'da asenkron programlama, uygulamalarınızın performansını ve tepki süresini önemli ölçüde iyileştirebilir. async ve await kullanımı, kodun okunabilirliğini ve bakımını kolaylaştırırken,
kaynak kullanımını da optimize eder. Bu rehber, asenkron programlamanın temel prensiplerini ve .NET Core'daki kullanımını kapsamaktadır.Uygulamalarınızda bu yöntemleri etkili bir şekilde kullanarak, daha hızlı ve
verimli yazılımlar geliştirebilirsiniz.
