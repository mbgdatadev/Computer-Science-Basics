# Linux Komut Satiri ve Crontab
- [Linux Temel Komutlari](#linux-temel-komutlari)
- [Degiskenler](#degiskenler)
- [PATH Degiskeni](#path-degiskeni)


## Linux Temel Komutlari

`mkdir`, "Make Directory" kısaltmasıdır ve yeni bir dizin oluşturmak için kullanılır. Yeni bir klasör/dizin oluşturmak istediğinizde `mkdir` komutunu kullanırsınız.

```bash
$ mkdir yeni_klasor

```

`pwd:` "Print Working Directory" kısaltmasıdır ve kullanıcıyı bulunduğu dizinin tam yolunu gösterir.
```bash
$ pwd
/home/kullanici/adim
```
`ls` komutunun kullanımı için pek çok bayrak ve seçenek mevcuttur. Bu bayraklar ve seçenekler, dosyaları ve dizinleri farklı biçimlerde listelemek veya ek bilgilerle birlikte görüntülemek için kullanılır.

Bunlardan bazıları şunlardır:

- -l: Dosyaları detaylı bir şekilde listeler.
- -a: Gizli dosyaları da (. ile başlayan dosyaları) listeler.
- -h: Dosya boyutlarını insan okunabilir formatta gösterir.
- -R: Alt dizinler de dahil olmak üzere tüm dizin ağacını listeler.
- -t: Dosyaları değiştirilme zamanına göre sıralar.
- -r: Ters sırada listeler.
Bu sadece bazıları, ancak daha fazla bayrak ve seçenek bulunmaktadır. Her biri ls komutunu farklı şekillerde kullanmanızı sağlar.

Her bir bayrağın veya seçeneğin ayrıntılı açıklamasını ve kullanımını öğrenmek için terminalde man ls komutunu kullanabilirsiniz. Bu komut, ls komutunun manuel sayfasını (manual page) gösterir ve tüm kullanılabilir seçenekleri listeleyecektir.




`ls:` "List" komutudur ve dizindeki dosya ve klasörleri listeler.
```bash
$ ls
belge1.txt belge2.txt klasor1 klasor2
```
ls -l, Linux/Unix terminalinde dosya ve dizinleri detaylı bir şekilde listelemek için kullanılan bir komuttur.

`ls -l:` Dosyaları ve klasörleri listeler. `-l:` Bu bayrak, "long format" olarak adlandırılan detaylı bir liste görüntülemek için kullanılır. Bu detaylar dosyaların/klasörlerin izinleri, sahibi, grup, boyutu, değiştirilme tarihi ve ismi gibi bilgileri içerir.
```bash
$ ls -l
-rw-r--r-- 1 kullanici kullanici 1024 Jan 1 12:00 belge1.txt
-rw-r--r-- 1 kullanici kullanici 2048 Jan 1 12:00 belge2.txt
drwxr-xr-x 2 kullanici kullanici 4096 Jan 1 12:00 klasor1
drwxr-xr-x 2 kullanici kullanici 4096 Jan 1 12:00 klasor2
```

`ls -lh:` Bu komut, dosya/dizinleri detaylı bir biçimde listeler (-l bayrağı), ancak boyutları insan okunabilir formatta (KB, MB, GB gibi) gösterir (-h bayrağı).
```bash
$ ls -lh
-rw-r--r-- 1 kullanici kullanici 1.5K Jan 1 12:00 belge1.txt
-rw-r--r-- 1 kullanici kullanici 2.0M Jan 1 12:00 belge2.txt
drwxr-xr-x 2 kullanici kullanici 4.0K Jan 1 12:00 klasor1
drwxr-xr-x 2 kullanici kullanici 4.0K Jan 1 12:00 klasor2
```

`ls -lr:` Bu komut, dosya/dizinleri ters sıra ile listeler (-r bayrağı). Yani, en son değiştirilen dosya en üstte listelenir.
```bash
$ ls -lr
klasor2 klasor1 belge2.txt belge1.txt
```

`ls -la` komutu, dosyaları ve dizinleri detaylı bir şekilde listelemek için kullanılırken aynı zamanda gizli dosyaları da (`.` ile başlayan dosyaları) listelemek için kullanılan bir komuttur.
```bash
$ ls -la
total 40
drwxr-xr-x  5 kullanici kullanici  4096 Jan  1 12:00 .
drwxr-xr-x 15 kullanici kullanici  4096 Jan  1 12:00 ..
-rw-r--r--  1 kullanici kullanici   220 Jan  1 12:00 .bashrc
-rw-r--r--  1 kullanici kullanici  3771 Jan  1 12:00 belge1.txt
-rw-r--r--  1 kullanici kullanici 24576 Jan  1 12:00 belge2.txt
drwxr-xr-x  2 kullanici kullanici  4096 Jan  1 12:00 klasor1
drwxr-xr-x  2 kullanici kullanici  4096 Jan  1 12:00 klasor2
```
Bu çıktıda, tüm dosyalar ve dizinler listelenirken, `.` ve `..` ile başlayan gizli dosyalar da (-a seçeneği sayesinde) görüntülenir. `-l` seçeneği ile de her dosya/dizin için detaylı bilgiler sağlanır. Total kısmı toplam dosya boyutunu verirken, diğer sütunlar dosya izinleri, sahibi, grubu, boyutu, değiştirilme tarihi ve ismini gösterir.


`ls -lt` komutu, dosyaları ve dizinleri detaylı bir şekilde listelerken aynı zamanda bu listeyi dosyaların değiştirilme zamanına göre sırala
```bash
$ ls -lt
-rw-r--r-- 1 kullanici kullanici  3771 Jan  1 12:00 belge1.txt
-rw-r--r-- 1 kullanici kullanici 24576 Jan  1 12:00 belge2.txt
drwxr-xr-x 2 kullanici kullanici  4096 Jan  1 12:00 klasor1
drwxr-xr-x 2 kullanici kullanici  4096 Jan  1 12:00 klasor2
-rw-r--r-- 1 kullanici kullanici   220 Jan  1 12:00 .bashrc
```

`history:` Kullanıcının daha önce çalıştırdığı komut geçmişini gösterir.
```bash
$ history
1  ls
2  pwd
3  cd klasor1
```
`cd:` "Change Directory" komutudur ve kullanıcıyı başka bir dizine taşır.
```bash
$ cd klasor1
```
`alias:` Kullanıcının kendi kısaltmalarını veya komutları tanımlamasını sağlar.
```bash
$ alias lsl="ls -l"
```
## Degiskenler

Linux ve diğer Unix tabanlı işletim sistemlerinde değişkenler, geçici verileri saklamak veya işlem sırasında bilgi depolamak için kullanılır. Birçok komut veya betik dosyası içinde değişkenler kullanılarak bilgi taşınabilir veya saklanabilir.

`env` komutu ile var olan değişkenleri görebililirz.


- Tanımlama: Bir değişken tanımlanırken, ismi ve değeri belirtilir. Linux'da değişken isimleri büyük/küçük harfe duyarlıdır ve genellikle büyük harfle tanımlanır. Değişken ataması için = işareti kullanılır. Örneğin:
```bash
ISIM="Burak"
YAS=30
```

- Kullanım: Tanımlanan değişkenler, $ işareti ile birlikte kullanılır. Örneğin:
 ```bash
echo "Merhaba, $ISIM. Yaşınız $YAS."
```

- Değişken Silme: unset komutuyla bir değişken silinebilir:
 ```bash
unset ISIM
```

`export`, Unix/Linux tabanlı işletim sistemlerinde bir ortam değişkeni tanımlamak veya mevcut bir değişkeni başka alt süreçlere aktarmak için kullanılan bir komuttur.

Genellikle, bir değişkeni sadece o anki kabuk (shell) oturumu için değil, alt süreçlerde veya diğer kabuk oturumlarında da kullanılabilir hale getirmek için export kullanılır.

Örnek kullanımı şu şekildedir:
```bash
export ISIM="Burak"
```
## PATH Degiskeni
Linux tabanlı işletim sistemlerinde, kullanıcıların veya sistemdeki programların çalıştırılabilir dosyalarını bulmak için arama yaparken kullanılan bir ortam değişkenidir. Bu değişken, sistemdeki dizinleri içerir ve komutların çalıştırılabilir dosyalarını bulmak için bu dizinleri tarar.

`which:` Kullanıcıların terminalde belirli bir komutun hangi dosya yolunda olduğunu bulmalarını sağlar. Örneğin:
```bash
which ls
/bin/ls
```
Bu çıktı, `ls` komutunun `/bin/ls` dosyasında olduğunu gösterir. Yani, `ls` komutu `/bin` dizini içinde yer alan `ls` dosyasından çalıştırılır.

`type:` Bu komut, bir komutun türünü belirtir. Örneğin, bir komutun bir yerleşik komut, bir shell fonksiyonu, bir harici komut veya bir `alias` olduğunu gösterir.
```bash
type ls
ls is aliased to `ls --color=auto'
```
Bu çıktıda, ls komutunun bir alias olduğunu ve `ls --color=auto` komutunu çağırdığını belirtir.

Bu komutlar, terminalde belirli bir komutun hangi dosya veya komut tipiyle ilişkilendirildiğini bulmak için kullanılır. PATH değişkeni, bu komutların çalıştırılabilir dosyalarını bulmak için belirli bir sırayla dizinleri tarar ve komutların yerel olarak nerede olduğunu belirler.
