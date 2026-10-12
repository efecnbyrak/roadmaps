# **Re**mote **D**ictionary **S**ervice Kelimelerinin Kısaltmasıdır

## REDIS CLI

> -> **C** ile yazılmıştır.
> -> Çıkış Noktası Hızdır. **HIZ**
> -> Key:Value şeklinde tasarlanmış bir NoSQL türünde Veri tabanıdır.
> -> In Memory Database yaklaşımı (Disk üzerine yazılabilme özelliği de opsiyonel)
> -> Redis gelişmiş bir key-value deposudur.

## Desteklenen Veri Türleri

> -> String
> -> Hash
> -> List
> -> Set
> -> Sorted Set
> -> Geospatial index
> -> HyperLogLog

## Nerelerde Kullanılabilir

> -> **Database** (Redis sakladığı veriyi disk üzerine de yazabilir (Persist))
> -> Caching Layer (Redis çok hızlıdır)
> -> Message Broker (Redis sadece key-value store olarak çalışmaz. RabbitMQ gibi kullanılabilir.)

## Ne değildir

> -> Relational Database (PostgreSQL MSSQL) yada Document bazlı Database sistemlerinin alternatifi **değildir**.
> -> Aksine bu DB türlerinin ilişkilierini tanımayalacak katman olarak kullanılabilir.
> -> En iyi kullanım alanı ise ; ön görülebilir DB bouyutuyla hızlı büyüyen veriler.

## Use Case (Kullanım Senaryoları)

> -> Cache Mekanizmalarında 
> -> Pub/Sub (Publish / Subs modelinin kullanılabileceğin çoğu yerde kullanılabilir.)
> -> Kuyrukların engellenmesi ve geciktirilmesinde kullanılabilir.
> -> Kısa canlı verilerde. (dolandırıcılık tespitlerinde, Layer 4'e kayan bir çalışma, hızlı bir şekilde response verilemesi gerken sistemlerde)
>> -> Fraud Detection (Dolandırıcılık Tespitlerinde)
>> -> Oturum Kontrollerinde
>> -> Filtrleme Servislerinde
> -> Yorum sayımlarında (aslında uzun kuyruklu verilerin burada tutulması çok iyi diye örnek veriyorum X adet yorum vardır bunun için DB kısmına yormaya gerke yok direkt Redis üzerinden çekilebilir.)
> -> Gerçek verilerin analizlerinde
> -> Her defasında **unique** bir verinin saklanmasında.

## Ne zaman kullanmalıyız?

> -> Çok yüksek hıza ihtiyaç olduğunda
> -> Key-Value çiftinden daha fazlası ihtiyacınız olduğunda.
> -> Dataset'in kritik olmadığı yerlerde.

## Dikkat Edilmesi Gerekenler

> -> Redis Bellek üzerinde veriler saklar, bundan dolayı çok fazla bellek kısıtlamaları vardır.
> -> Boş bir instance 1mb belle kaplar. 
> -> 1 Milyon küçük key-value (string) çifti 100mb bellek kullanır.
> -> 1 Milyon küçük key-value (5 field'dan oluşan hash) çifti 200mb bellek kullanır.

## Scaling (Ölçeklendirme)

> -> **Persistance**
>> -> Redis persistance için 2 farklı mekanizma sağlar.
>>> -> *RDB* (Redis database snapshots)
>>> -> *AOF* (Append only files)
> -> **Replication**
>> -> 1 Redis instance **master** olarak kullanılır. Diğer instance'ler ise Slave olarak gelir ve bunlar Master'ın kopyalarıdır.
>> -> Client bu slave veya master instance'lardan birine bağlanır.
>> -> Slave defaulf olarak sadece okuma işlemi yaparlar.
> -> **Partitioning** 
>> -> Veriyi bölebilir ve paylaştırabilirsiniz.
> -> **Faliover**
>> -> Manuel 
>> -> Otomatik (Redis Sentinel - master-slave topoloji için)
>> -> Otomatik (Redis Cluster - cluster topolojisi için)
