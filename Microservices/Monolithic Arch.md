# Monolithic Arch

## Monolitik Mimari

> -> Monolit Mimari, bir yazılım uygulamasının kullanıcılara sunduğu özellikleri örnek olarak, Giriş Yapma İşlemleri, Ödeme İşlemleri gibi temel bileşenleri tek bir uygulama içerisinde toplayıp geliştirilip dağıtım yapılan yöntemdir.
> -> Monolitik mimarinin **dezavantajı**, Giriş Yapma İşlemlerinde yapılmış olunan bir revize işlemi diğer fonksiyonları etkileyebilir. Aynı şekilde sistemin tekradan bütün fonksiyonları veya işlemleri ile ayağıya kaldırılması demektir.
> -> Fakat monolit mimari her zaman dezavantaj değildir kimi zaman aslında çok daha hızlı test süreçleri dağıtım süreçlerinin çok daha yapılabildiği bir mimaridir. Çünkü aralarında en az veri yükü taşıcak veya en az bakım gerektiricek olan potansiyonel olarak budur.

### Presentation Layer

> -> Son kullıcının gördüğü ve kodları oluturduğumuz bölüm **GUI** kısmımız aslında.

### Business Layer

> -> Mantıksal işlemlerin yapıldığı temel kısım aslında.
> -> Bu kısımda bizim kodlarımızın büyük bir çoğunluğu burada olur.
> -> Aslında GUI ile DB arasında ki birer çok ciddi bir köprü görevi görür.
> -> Kullanıcının girdiğin bilgileri POST DELETE PUT/PATCH GET işlemelerinden hangisi ise bunlar ile server tarafında bir filtrelemeden geçirip DB kısmından alınması gereken doğru veriyi alır ve sonrasında bir response değer döndürür GUI tarafına yani kullanıcı tarafına. (Tabii ki de bu kısım sadece kullanıcı tarafına veri döndürmek için değildir.)

### Data Access Layer

> -> Mantıksal işlemler Business Layer'da işlendikten sonra PostgreSQL gibi veya MSSQL gibi buna benzer birden fazla DB içerisinde kendi kullandıkları SQL dilleri ile bizim istediğimiz doğru veriyi Server tarafına yine bir format da geri dönüşünü yapıyor.

## Advantage - Disadvantages

### Advantage

> -> Geliştirilmesi - **Kolay**
> -> Test Edirebilirliği - **Kolay**
> -> Deployment - **Kolay**
> -> Ölçeklendirmek oldukça kolay. Yatay olarak mimarinin kopyasını Load Balancer arkasında çalıştırabilirsiniz. - **Kolay** (Yatay : Sunucuyu Duplicate ederek çalıştırabilmek aslında.) (Dikey : var olan sununcunun gereksinimlerini arttırmak.)

### Disadvantages

> -> Bakımı proje büyüdükçe zorlaşır. (Sürdürebilirlik) - **Zor**
> -> Uygulamanın boyutu başlama süresini yavaşlatırı. - **Zor** (Uzun süreler beklemek)
> -> Uygulama güncelleneceği zaman tüm uygulamaları tekrardan deploy etmemiz gerekicek. - **Zor**
> -> Monolitik uygulamalar ölçeklendirmeler yapılırken daha fazla sorun çıkartabilir - **Zor**
> -> Ölçeklendirme tüm proje genelinde yapılır. Bütün projeyi aslında kopyalamış oluyor yani odaklı bir ölçeklendirme yapmak pek mümkün değil - **Zor**
> -> Güvenirillik / Sağlamlık / Dayanıklılık - **Zor**