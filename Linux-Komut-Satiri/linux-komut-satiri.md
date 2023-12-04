# Linux Komut Satiri ve Crontab
- [Linux Temel Komutlari](#linux-temel-komutlari)
- [Degiskenler](#degiskenler)
- [PATH Degiskeni](#path-degiskeni)
- [grep ile regex](#grep-ile-regex)
- [Dosya ve Klasor Islemleri](#dosya-ve-klasor-islemleri)
- [sed Komutu](#sed-komutu)
- [Pipe Nedir](#pipe-nedir)
- [Direction Nedir](#direction-nedir)
- [Compression-gzip](#compression-gzip)
-  [Archive-tar](#archive-tar)

## Linux Temel Komutlari

`pwd:` "Print Working Directory" kısaltmasıdır ve kullanıcıyı bulunduğu dizinin tam yolunu gösterir.
```bash
 pwd
/home/kullanici/adim
```
`ls` komutunun kullanımı için pek çok bayrak ve seçenek mevcuttur. Bu bayraklar ve seçenekler, dosyaları ve dizinleri farklı biçimlerde listelemek veya ek bilgilerle birlikte görüntülemek için kullanılır.

Bunlardan bazıları şunlardır:

- -l: Dosyaları detaylı bir şekilde listeler.
- -a: Gizli dosyaları da (`.` ile başlayan dosyaları) listeler.
- -h: Dosya boyutlarını insan okunabilir formatta gösterir.
- -R: Alt dizinler de dahil olmak üzere tüm dizin ağacını listeler.
- -t: Dosyaları değiştirilme zamanına göre sıralar.
- -r: Ters sırada listeler.
Bu sadece bazıları, ancak daha fazla bayrak ve seçenek bulunmaktadır. Her biri ls komutunu farklı şekillerde kullanmanızı sağlar.

Her bir bayrağın veya seçeneğin ayrıntılı açıklamasını ve kullanımını öğrenmek için terminalde man ls komutunu kullanabilirsiniz. Bu komut, ls komutunun manuel sayfasını (manual page) gösterir ve tüm kullanılabilir seçenekleri listeleyecektir.




`ls:` "List" komutudur ve dizindeki dosya ve klasörleri listeler.
```bash
 ls
belge1.txt belge2.txt klasor1 klasor2
```
ls -l, Linux/Unix terminalinde dosya ve dizinleri detaylı bir şekilde listelemek için kullanılan bir komuttur.

`ls -l:` Dosyaları ve klasörleri listeler. `-l:` Bu bayrak, "long format" olarak adlandırılan detaylı bir liste görüntülemek için kullanılır. Bu detaylar dosyaların/klasörlerin izinleri, sahibi, grup, boyutu, değiştirilme tarihi ve ismi gibi bilgileri içerir.
```bash
 ls -l
-rw-r--r-- 1 kullanici kullanici 1024 Jan 1 12:00 belge1.txt
-rw-r--r-- 1 kullanici kullanici 2048 Jan 1 12:00 belge2.txt
drwxr-xr-x 2 kullanici kullanici 4096 Jan 1 12:00 klasor1
drwxr-xr-x 2 kullanici kullanici 4096 Jan 1 12:00 klasor2
```

`ls -lh:` Bu komut, dosya/dizinleri detaylı bir biçimde listeler (-l bayrağı), ancak boyutları insan okunabilir formatta (KB, MB, GB gibi) gösterir (-h bayrağı).
```bash
 ls -lh
-rw-r--r-- 1 kullanici kullanici 1.5K Jan 1 12:00 belge1.txt
-rw-r--r-- 1 kullanici kullanici 2.0M Jan 1 12:00 belge2.txt
drwxr-xr-x 2 kullanici kullanici 4.0K Jan 1 12:00 klasor1
drwxr-xr-x 2 kullanici kullanici 4.0K Jan 1 12:00 klasor2
```

`ls -lr:` Bu komut, dosya/dizinleri ters sıra ile listeler (-r bayrağı). Yani, en son değiştirilen dosya en üstte listelenir.
```bash
 ls -lr
klasor2 klasor1 belge2.txt belge1.txt
```

`ls -la` komutu, dosyaları ve dizinleri detaylı bir şekilde listelemek için kullanılırken aynı zamanda gizli dosyaları da (`.` ile başlayan dosyaları) listelemek için kullanılan bir komuttur.
```bash
 ls -la
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
 ls -lt
-rw-r--r-- 1 kullanici kullanici  3771 Jan  1 12:00 belge1.txt
-rw-r--r-- 1 kullanici kullanici 24576 Jan  1 12:00 belge2.txt
drwxr-xr-x 2 kullanici kullanici  4096 Jan  1 12:00 klasor1
drwxr-xr-x 2 kullanici kullanici  4096 Jan  1 12:00 klasor2
-rw-r--r-- 1 kullanici kullanici   220 Jan  1 12:00 .bashrc
```

`history:` Kullanıcının daha önce çalıştırdığı komut geçmişini gösterir.
```bash
 history
1  ls
2  pwd
3  cd klasor1
```
`cd:` "Change Directory" komutudur ve kullanıcıyı başka bir dizine taşır.
```bash
 cd klasor1
```
`alias:` Kullanıcının kendi kısaltmalarını veya komutları tanımlamasını sağlar.
```bash
 alias lsl="ls -l"
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

## grep ile regex

`grep`, Linux sistemlerinde metin tabanlı verilerde belirli bir deseni veya kelimeyi aramak için kullanılan bir komuttur. Genellikle metin dosyalarında veya komut çıktılarında belirli bir deseni veya kelimeyi bulmak için kullanılır.

Temel kullanımı şu şekildedir:
```bash
grep "aranacak_kelime" dosya_adı
```
Bu komut, `dosya_adı` içinde `aranacak_kelime` desenini arar

`grep` ayrıca birçok seçeneğe ve kullanım varyasyonuna sahiptir. Örneğin:

- `-i` seçeneği: Büyük/küçük harf duyarlılığını yok sayarak arama yapar.
 ```bash
  grep -i "HATA" logdosyasi.txt
  ```
- `-r` seçeneği: Belirtilen dizinler altındaki dosyalarda rekurzif olarak arama yapar.
 ```bash
  grep -r "hata" /home/kullanici/dizin
  ```
- `-n` seçeneği: Eşleşen satırların numaralarını gösterir.
 ```bash
  grep -n "hata" logdosyasi.txt
  ```
- `-v` seçeneği: Eşleşmeyen satırları gösterir.
 ```bash
  grep -v "hata" logdosyasi.txt
  ```
- `-E` seçeneği: Düzenli ifadeleri kullanmanızı sağlar.
 ```bash
  grep -E "pattern1|pattern2" dosya.txt
  ```
####  regular expressions` veya regex
`regular expressions` veya kısaca `regex` (Düzenli ifadeler), metin tabanlı verilerde belirli desenleri tanımlamak için kullanılan özel bir dil ve yapıdır. `grep` gibi arama işlemlerinde, belirli bir deseni veya kalıbı tanımlamak için kullanılırlar. Örneğin, `grep` komutunu düzenli ifadelerle kullanarak daha karmaşık arama işlemleri gerçekleştirebilirsiniz.

- Rakam Arama: Metin içinde rakamları bulmak için regex kullanımı.
  ```bash
  grep "[0-9]" dosya.txt
  ```
   Bu ifade, `dosya.txt`  içinde herhangi bir rakamı bulur.

- Kelime Başlangıcı ve Bitişi: Bir metinde belirli bir kelimenin başlangıcını veya bitişini bulmak için regex kullanımı.
  ```bash
  grep "\<pattern" dosya.txt
  ```
   Bu ifade, `dosya.txt` içinde pattern ile başlayan kelimeleri bulur.

  ```bash
  grep "pattern\>" dosya.txt
  ```
   Bu ifade ise `dosya.txt` içinde pattern ile biten kelimeleri bulur.

- Birden Fazla Karakter Arama: Belirli bir deseni içeren birden fazla karakteri bulmak için regex kullanımı.
  ```bash
  grep "a.*b" dosya.txt
  ```
  Bu ifade, `dosya.txt` içinde "a" ile başlayıp "b" ile biten herhangi bir karakter dizisini bulur.

- Özel Karakterlerin Kaçışı: Özel karakterlerin aranması için kaçış karakteri kullanımı.
  ```bash
  grep "\." dosya.txt
  ```
   Bu ifade, `dosya.txt` içinde nokta karakterini bulur. Nokta normalde herhangi bir karakteri temsil eder, ancak \ ile birlikte kullanılarak özel anlamından 
   çıkartılır ve gerçek nokta karakterini arar.

- Belirli Karakter Sayısını Arama: Belirli bir karakter sayısını aramak için {} kullanımı.
  ```bash
  grep "a\{3\}" dosya.txt
  ```
   Bu ifade, `dosya.txt` içinde üç ardışık `a` karakterini bulur.

- Satır Başlangıcı ve Bitişi: Bir metinde satır başlangıcı veya bitişini belirtmek için ^ ve $ kullanımı.
  ```bash
  grep "^pattern" dosya.txt
  ```
   Bu ifade, `dosya.txt` içindeki satırlarda `pattern` ile başlayanları bulur.

  ```bash
  grep "pattern$" dosya.txt
  ```
  Bu ifade, `dosya.txt` içindeki satırlarda `pattern` ile bitenleri bulur.

Bu örnekler, `grep` komutuyla kullanılan farklı `regex` örneklerindendir. Düzenli ifadeler çok çeşitli kullanımlara sahip olduğundan, daha karmaşık aramalar ve desenler oluşturabilirsiniz.


## Dosya ve Klasor Islemleri

#### Dosya Oluşturma
Yeni bir dosya oluşturmak için `touch` komutunu kullanabilirsiniz:
 ```bash
touch yeni_dosya.txt
  ```
#### Dosya Silme
Dosya silmek için `rm` komutunu kullanabilirsiniz:
 ```bash
  rm dosya.txt
  ```
#### Dosya Güncelleme
Metin tabanlı dosyaları güncellemek için `echo`echo komutunu ve `>` operatörünü kullanabilirsiniz:
 ```bash
echo "Yeni metin" > dosya.txt
  ```
Bu komut, `dosya.txt` dosyasına `Yeni metin` içeriğini yazar.

#### Dosya İsmi Güncelleme
```bash
mv eski_dosya.txt yeni_dosya.txt
```
Yukarıdaki komut, `eski_dosya.txt` adlı dosyanın ismini `yeni_dosya.txt` olarak değiştirir.

#### Dosya Taşıma
Dosyaları taşımak için `mv` komutunu kullanabilirsiniz:
```bash
mv dosya.txt hedef_klasor/
```
Bu komut, `dosya.txt` dosyasını `hedef_klasor` adlı klasöre taşır.

#### Dosya Kopyalama
Dosyaları kopyalamak için `cp` komutunu kullanabilirsiniz:
```bash
cp dosya.txt hedef_klasor/
```
Bu komut, `dosya.txt` dosyasını `hedef_klasor` adlı klasöre kopyalar.

#### Dosya İçeriği İşlemleri
Bu komutlar, Linux sistemlerinde dosya içeriğini görüntülemek, incelemek veya işlemek için kullanılan temel komutlardır.

- `cat` komutu, dosyanın tamamını terminalde göstermek için kullanılır.
   ```bash
   cat dosya.txt
   ```
- `more` komutu, dosyanın içeriğini sayfa sayfa görüntülemek için kullanılır. Eğer dosya çok büyükse, sayfa başına uzun bir metin varsa veya ekran kaplayacak 
   kadar büyükse, `more` komutu kullanışlı olabilir.
   ```bash
   more dosya.txt
   ```
- `less`  komutu, `more`'un geliştirilmiş bir versiyonudur. Sayfa sayfa dosya içeriğini görüntülemek için kullanılır. `less` daha esnek ve kullanımı daha kolaydır.
    ```bash
   less dosya.txt
   ```
   
- `head`  komutu, bir dosyanın baş kısmını (varsayılan olarak ilk 10 satırını) görüntülemek için kullanılır. İsteğe bağlı olarak kaç satırın görüntüleneceğini        belirlemek için -n bayrağı kullanılabilir.
   ```bash
   head dosya.txt
   ```
    ```bash
     head -n 15 dosya.txt  # İlk 15 satırı gösterir
    ```
 - `tail`  komutu, bir dosyanın son kısmını (varsayılan olarak son 10 satırını) görüntülemek için kullanılır. İsteğe bağlı olarak kaç satırın görüntüleneceğini        belirlemek için -n bayrağı kullanılabilir.
   ```bash
   tail dosya.txt
   ```
    ```bash
     tail -n 15 dosya.txt  # Son 15 satırı gösterir
    ```

#### Klasör Oluşturma
`mkdir`, "Make Directory" kısaltmasıdır ve yeni bir dizin oluşturmak için kullanılır. Yeni bir klasör/dizin oluşturmak istediğinizde `mkdir` komutunu kullanırsınız.

```bash
 mkdir yeni_klasor
```
#### Klasör Silme
Klasör silmek için `rm` komutunu ve `-r` (recursive - rekurzif) bayrağını kullanarak tüm içeriği ile birlikte silinebilir:

```bash
rm -r klasor
```

#### Klasör İsmi Güncelleme
```bash
mv eski_klasor/ yeni_klasor/
```
Bu komut, `eski_klasor` adlı klasörün ismini `yeni_klasor` olarak değiştirir. 
`mv` komutu, aslında dosyaları veya klasörleri taşımak için kullanılsa da, aynı anda isimlerini değiştirmek için kullanılabilir. Bu komutun kullanımı oldukça esnektir ve dosya/klasörlerin taşınması veya yeniden adlandırılması için yaygın olarak kullanılır.

#### Klasör Kopyalama
Klasörleri kopyalamak için `cp` komutunu kullanabilirsiniz. `-r` bayrağı, klasörleri rekurzif olarak (içerikleriyle birlikte) kopyalamak için gereklidir.

```bash
cp -r kaynak_klasor/ hedef_klasor/
```
Bu komut, `kaynak_klasor`'ü `hedef_klasor`'e kopyalar.

#### Klasör Taşıma
Klasörleri taşımak için mv komutunu kullanabilirsiniz.

```bash
mv kaynak_klasor/ hedef_klasor/
```
Bu komut, `kaynak_klasor`'ü `hedef_klasor`'e taşır.

## sed Komutu
`sed`, Linux sistemlerinde metin işleme için kullanılan bir komuttur. `Stream Editor`ın kısaltmasıdır ve metinleri okur, belirli düzenlemeleri yapar ve çıktıyı verir. `sed` komutu genellikle metin dosyalarını okuyarak metin değişiklikleri yapmak için kullanılır. Temelde, metin akışı üzerinde arama yapma, eşleşen metni değiştirme, metin kesme veya filtreleme gibi işlemler gerçekleştirebilir.

Örnek kullanımlarından biri şu şekildedir:
```bash
sed 's/old_word/new_word/' dosya.txt
```
Bu komut, `dosya.txt` içindeki her bir `old_word`'ü `new_word` ile değiştirir. Ancak bu değişiklik dosyayı değiştirmez, yalnızca çıktı olarak değiştirilmiş metni gösterir. `sed` komutu, metin işlemlerinde oldukça güçlüdür ve `regex` (düzenli ifadeler) kullanarak metin üzerinde çeşitli işlemler yapabilir. Satırları ekleme, çıkarma, değiştirme, filtreleme gibi birçok işlemi gerçekleştirebilir. Kullanımı oldukça esnektir ve metin işlemlerinde çokça tercih edilen bir araçtır. Ancak karmaşık düzenli ifadelerle kullanıldığında öğrenmesi biraz zaman alabilir.

#### Dosyanın Üzerine Yazmak
`sed` komutunun çıktısını aynı dosyanın üzerine yönlendirebilirsiniz. Ancak bu, dikkatli olunması gereken bir işlemdir, çünkü dosya içeriği kalıcı olarak değişecektir ve geri alınamaz bir hale gelebilir.

Örnek:
```bash
sed -i 's/old_word/new_word/' dosya.txt
```
`-i` bayrağı, orijinal dosyayı değiştirme işlemini gerçekleştirir. Ancak bu işlem, değişikliklerin kalıcı olarak kaydedilmesine ve geri alınamaz olmasına yol açabilir.


## Pipe Nedir
Pipe `|`, Linux tabanlı işletim sistemlerinde kullanılan önemli bir operatördür. İki komutun çıktısını birbirine bağlar ve bir komutun çıktısını bir diğer komutun girdisi olarak kullanmanızı sağlar. Bu şekilde, komutlar arasında veri akışını kolayca sağlayabilir ve birbirleriyle iletişim kurabilirler.

Örneğin, `ls -l` komutunun çıktısını `grep` komutunun girdisi olarak kullanarak belirli dosya veya dizinleri filtrelemek istediğinizi düşünelim:
```bash
ls -l | grep ".txt"
#output
-rw-r--r-- 1 kullanici kullanici  3771 Jan  1 12:00 belge1.txt
-rw-r--r-- 1 kullanici kullanici 24576 Jan  1 12:00 belge2.txt
```
Bu komut, `ls -l` komutunun çıktısını alır ve `grep` komutunun girdisi olarak gönderir. `grep` komutu, ".txt" kelimesini içeren dosyaları veya dizinleri filtreleyerek sadece bu kriteri sağlayanları gösterecektir.

## Direction Nedir

`Standart Çıktı (stdout):` Bir komutun normal çalışma durumunda ürettiği çıktıdır. Örneğin, bir komutun işlem sonuçlarını veya beklenen çıktıları standart çıktıya gönderir. Genellikle bu çıktı, terminalde veya başka bir programda görüntülenir.
`Hata Çıktısı (stderr)`: Bir komutun hata durumlarında veya istisnai durumlarda ürettiği çıktıdır. Örneğin, bir komut hatalı bir dosya yoluyla çalışıyorsa veya işlem yaparken bir problemle karşılaşıyorsa, hata mesajları hata çıktısına yönlendirilir. Bu çıktı da genellikle terminalde veya başka bir programda görüntülenir.

`Direction` (Yönlendirme)  ise bu çıktıları farklı yerlere veya dosyalara yönlendirmek için kullanılan bir işlemdir. Unix ve Linux sistemlerinde, komutların çıktılarını işlemek için farklı yönlendirme operatörleri bulunur:

`>`  operatörü, bir dosyaya veri yazarken, eğer hedef dosya zaten varsa, mevcut içeriği siler ve yeni çıktıyı yazar. Yani, eğer dosya.txt zaten varsa ve siz > 
     operatörünü kullanarak bir komutun çıktısını bu dosyaya yönlendirirseniz, dosyanın içeriği silinip yerine yeni çıktı yazılır.
```bash
ls > dosya.txt
```
`ls` çıktsını `dosya.txt` içerisine yazar.

`>` Standart çıktıyı belirtilen bir dosyaya yönlendirir.
```bash
> dosya.txt
```
bu işlem `dosya.txt` dosyasının içeriğini siler.
 
`>>` operatörü, mevcut dosyanın içeriğini korur ve yeni çıktıyı dosyanın sonuna ekler.
```bash
echo "yeni satir" >> dosya.txt
```
"yeni satir` çıktsını `dosya.txt` içerisine ekler.

`2>` veya `&>`Hata çıktısını belirtilen bir dosyaya yönlendirir.
```bash
ls qwe 2> dosya.txt
```
Bu komut dosya içerisine var içeriği siler ve bu hatayı `ls: cannot access 'wqe': No such file or directory` yazar 

`2>>` veya `&>>` operatörü, mevcut dosyanın içeriğini korur ve hata çıktısını belirtilen bir dosyanın sonuna ekler.
```bash
ls qwe &>> dosya.txt
```
Bu komut dosya içerisine  bu hatayı `ls: cannot access 'wqe': No such file or directory` ekler 

## Compression-gzip
`gzip`, Linux sistemlerinde sıkıştırma ve arşivleme işlemleri için kullanılan bir komut ve aynı zamanda bir dosya formatıdır. Genellikle dosyaların boyutunu azaltmak veya birden fazla dosyayı tek bir dosyada saklamak için kullanılır.

- Bir Dosyayı Sıkıştırmak
```bash
gzip dosya.txt
```
Bu komut, `dosya.txt` dosyasını sıkıştırır ve `dosya.txt.gz` adında sıkıştırılmış bir dosya oluşturur. Orijinal dosya silinmez, sadece sıkıştırılmış versiyonu eklenir.

- Birden Fazla Dosyayı Sıkıştırmak
  ```bash
   gzip dosya1.txt dosya2.txt dosya3.txt
  ```
Bu komut, `dosya1.txt`, `dosya2.txt` ve `dosya3.txt` dosyalarını sıkıştırır ve her biri için ayrı sıkıştırılmış dosyalar oluşturur (`dosya1.txt.gz, dosya2.txt.gz, dosya3.txt.gz`).

- Bir Klasör İçinde Birden Fazla Dosyayı Sıkıştırmak
    ```bash
   gzip -r yeni_Klasor/
  ```
  `yeni_klasor` dizininde bulunan her dosyayı sıkıştırır.
  
- Sıkıştırılmış Bir Dosyayı Açmak
```bash
gunzip dosya.txt
```
```bash
gzip -d dosya.gz
```

`gunzip` veya `gzip -d` komutu, `dosya.txt.gz` adlı sıkıştırılmış dosyayı açar ve `dosya.txt` adında orijinal dosyayı oluşturur.


## Archive-tar








