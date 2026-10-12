# Service Oriented Arch (SOA)

## SOA

> -> Servislerin birbirlerinden ayrı ayrı tasarlanıp (bazı zamanlarda çok ufak da olsa ortaklaşa yerler olabiliyor.) bir yapı oluşturulmasını sağlar.
> -> Yapılar genel itibariyle bu kısımda birbirlerinden bağımsız çalışırlar. (Loose Coupling)
> -> Birden çok sistem yer aldığı yapılarda genellikle kullanılır.
> -> Kendi içerisinde bir çok bileşene sahiptirler ;
>> -> Policies, Contracts, Services ve çok daha fazlası
> -> Dağıtık yazılım sistemlerinin kalitelerini arttırmayı hedefler çok daha iyi bir kod yazımı veya çok daha yüksek güvenilirli bir sistem inşaat ediyorsak aslında bu kısımda bize çok daha fazla yardımcı olur.
>> -> Uyumluluk, Tekrar Kullanabilirlik, Bakım Yeteneği
>> -> Türk Telekom Örn ;
>>> -> CRM, Accounting, Marketing.

### Enterprise Bus Service

> -> Gelen istekleri kontrol eden bir sistem, Validate eden. aslında Router gibi çalışan bir sistem. 
> -> SOAP, WDSL

## Advantage - Disadvantages

### Advantage

> -> Servisler tekrar kullanabilir. Resuable. - **Kolay**
> -> Bakım ve onarım süreçleri kolaydır. - **Kolay**
> -> Güvenilirlik ve Dayanıklılık. - **Kolay**
> -> Up Time olayıları yüksektir, Ulaşılabilirlik - **Kolay**
> -> Yatay ve Dikey Ölçeklendirebilirlik Rahattır. - **Kolay**
> -> Platform Bağımsızdır. - **Kolay**
> -> Üretkenlik Artar. - **Kolay**
> -> Ekipe yeni katılan biri zorunlu bir şekilde o Framework diline hakim olmak zorunda kalmaz tekrarndan takıma adapte olması çok daha hızlı bir süreç olur. - **Kolay**

### Disadvantages

> -> Overload. - **Zor**
> -> Yüksek Maaliyet. - **Zor**
> -> Yüksek Bant Genişliği. - **Zor**
