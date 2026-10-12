# Microservices Arch

## Mikroservis Mimari

> -> SOA'nın yorumudur.
> -> Her bir servis kendine ait bir dünyada çalışır. (Server Stack).
> -> Kendine ait bir veritabanı vardır.
> -> Sadece 1 küçük işi çok iyi düzeyde yapmaktır. 
> -> Api GW üzerinden dış ve iç dünyaya açılırlar. (GW - Gateway)
> -> Böylece herhangi bir teknoloji ve dile ait bir kısıtlama olmaz.
> -> Stateless yapılardır. Dosya bağımlılığı olmamalı.
> -> Kolay Ölçeklenebilirler (Yatay, dikey'e gerek yok.)

### Api Gateway

Örnek veriyorum Server:3000'de benim post isteklerim var o zaman bu Server:3000 kısmına gidiyor ve oradan post isteklerini alabiliyor. Diyelim ki bizim Users isteklerimiz fonksiyonlarımız Server:9091'de o zaman oraya gidiyor ve alıp geliyor aslında olay tam olarak bu. Api Gateway içerisinde.
Aslında burada Reverse Proxy'de işe yarar çünkü Gateway /posts/1234 bilgisini aslında şuna çeviriyor : https://server:3000/posts/1234
Bize JSON verisin gönderiyor ve Api Gateway ise yani GUI Api Gateway ise bunları görsele çeviriyo ve Client'a sunuyor.

## Advantage - Disadvantages

### Advantage

> -> Çok dilli mimari - **Kolay**
> -> Kolay Ölçeklendirme - **Kolay**
> -> Daha iyi bir takım yönetimi - **Kolay**
> -> Yenilik yapmak daha kolay - **Kolay**
> -> Daha odaklı (Yapı, Ölçeklendirme)
> -> İmplemente edilirken diğer servisler etkilenmezler. - **Kolay**

### Disadvantages

> -> Implementasyon kolay değildir. (Network Calls, Service Discovery) - **Zor**
> -> Debug kolay değildir. - **Zor** 
> -> Fault Management (Hata Yönetimi) kolay değildir. - **Zor**