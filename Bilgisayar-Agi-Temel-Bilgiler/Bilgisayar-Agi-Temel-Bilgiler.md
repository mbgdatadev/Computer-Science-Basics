# Bilgisayar Ağı Temel Bilgiler

-[Protokol Nedir?](#protokol-nedir)
-[Mac ve Ip Adresi Nedir?](#mac-ve-ip-adresi-nedir)
-[NAT Nedir?](#nat-nedir)
-[Default Gateway Nedir?](#default-gateway-nedir)
-[Subnet Mask Nedir?](#subnet-mask-nedir)
-[DHCP Nedir?](#dhcp-nedir)
-[DHCP Nedir?](#dhcp-nedir)
-[Port Nedir?](#port-nedir)


## Protokol Nedir? 
Cihazların iletişim kurarken takip etmesi gereken belirli kurallar ve standartlardır. Bilgisayar ağlarında, cihazların veri iletimi ve alımı için belirli protokolleri kullanması gerekmektedir. İşte yaygın kullanılan bazı protokoller:

1. **TCP/IP (Transmission Control Protocol/Internet Protocol):** İnternet üzerinde veri iletişimini sağlayan temel protokoldür. Veri paketlerinin iletimini ve alımını düzenler.

2. **HTTP (Hypertext Transfer Protocol):** Web sayfalarının iletimi için kullanılan protokoldür. Tarayıcılar, web sunucularından sayfa istemek ve almak için HTTP kullanır.

3. **HTTPS (Hypertext Transfer Protocol Secure):** Güvenli iletişim için kullanılan HTTP türevidir. Veri şifreleme teknolojileriyle desteklenir ve daha güvenli bir iletişim sağlar.

4. **SMTP (Simple Mail Transfer Protocol):** E-posta iletimi için kullanılan protokoldür. E-posta sunucuları, SMTP protokolünü kullanarak e-postaları gönderir ve alır.

5. **FTP (File Transfer Protocol):** Dosyaların bir bilgisayardan diğerine transfer edilmesi için kullanılan protokoldür.

6. **SSH (Secure Shell):** Uzak sunuculara güvenli erişim için kullanılan bir protokoldür. Verilerin şifrelenerek iletilmesini sağlar.

7. **DNS (Domain Name System):** Alan adlarını IP adreslerine çeviren bir protokoldür. İnternette gezinirken, alan adlarının IP adreslerine dönüştürülmesini sağlar.

Bu protokoller, farklı iletişim amaçları için kullanılır ve belirli işlevleri yerine getirirler. 

## Mac ve Ip Adresi Nedir?
- **MAC Adresi (Media Access Control Address):** Her ağ bağlantılı cihazın donanımının benzersiz bir kimliğidir. MAC adresi, ağ kartlarına veya ağ arabirimlerine atanır ve genellikle on altılık sayılarla (00:1A:2B:3C:4D:5E gibi) temsil edilir. Cihazın üretici, model ve seri numarasını içeren bu adres, ağdaki diğer cihazlarla iletişim kurarken kullanılır.

- **IP Adresi (Internet Protocol Address):** Ağdaki her cihazın tanımlanmasını sağlayan benzersiz bir sayıdır. IP adresleri, cihazların birbirleriyle iletişim kurması için kullanılır. IPv4 (örneğin, 192.168.1.1) ve IPv6 (örneğin, 2001:0db8:85a3:0000:0000:8a2e:0370:7334) olmak üzere farklı sürümleri vardır. IPv4 adresleri giderek tükenmekte olduğundan, IPv6 daha geniş bir adresleme alanı sunar.

## NAT Nedir?

- **NAT (Network Address Translation - Ağ Adresi Çevirisi):** NAT, bir ağda bulunan cihazların özel (yerel) IP adreslerini genel (geniş) IP adresine dönüştürmek için kullanılan bir yöntemdir. Özel IP adresleri, genellikle ev veya işyeri ağları gibi sınırlı bir alanda kullanılırken, genel IP adresi ise internete erişim sağlayan ana IP adresidir.

  - **Neden Kullanılır?** NAT, birden fazla cihazın aynı genel IP adresi üzerinden internete erişimini sağlar. Böylece ev veya işyeri ağındaki her cihaz, tek bir genel IP adresi kullanarak internete bağlanabilir.

  - **NAT Türleri:**
    - **IP Masquerading:** Ev ağında bulunan cihazların, genel IP adresi üzerinden internete erişimini sağlar.
    - **Port Address Translation (PAT):** Birden fazla özel IP adresinin aynı genel IP adresi üzerinden erişimini sağlar. Farklı port numaraları kullanılarak aynı genel IP adresi üzerinden iletişim mümkün olur.

  - **Avantajları:**
    - Güvenlik: NAT, ağdaki cihazların doğrudan internete erişimini kısıtlar ve gelen bağlantıları filtreler. Bu da ağ güvenliğini artırır.
    - IP Adres Yönetimi: Sınırlı sayıdaki genel IP adresi, çok sayıda cihazın internete bağlanmasını sağlar.

  - **Dezavantajları:**
    - NAT, bazı uygulamalar için problem yaratabilir. Özellikle P2P (peer-to-peer) bağlantılar veya bazı oyunlar NAT'ın getirdiği kısıtlamalar nedeniyle sorun yaşayabilir.
    - End-to-End Bağlantı: NAT, ağın içindeki cihazların doğrudan dış dünya ile bağlantı kurmasını engeller. Bu da bazı uygulamalar için sorun olabilir.

## Default Gateway Nedir?
- **Varsayılan Ağ Geçidi (Default Gateway):** Bir cihazın, bulunduğu ağdan dışarıya iletişim kurmak için kullandığı yol veya cihazdır. Bir ağa bağlı cihazlar, iletişim kurmak istediklerinde hedef adres aynı ağda değilse, veri paketlerini varsayılan ağ geçidi aracılığıyla gönderirler.

  - **Nasıl Çalışır?** Bir cihaz, veri paketini göndermek istediğinde, hedef IP adresi cihazın ağında değilse, bu veri paketi varsayılan ağ geçidine gönderilir. Varsayılan ağ geçidi, veri paketini doğru hedefe yönlendirmek için gereken bilgiyi içerir.

  - **Örnek:** Ev ağınızda bulunan bir bilgisayar, internete erişmek istediğinde veri paketlerini varsayılan ağ geçidi olan evdeki yönlendiriciye gönderir. Yönlendirici, bu paketleri internete göndermek için gereken bilgiye sahiptir ve internete erişimi sağlar.

  - **Önemi:** Varsayılan ağ geçidi, cihazların dış ağlara erişimini kolaylaştırır. Bu, cihazların genel internete veya başka ağlara bağlanmasını sağlar.

  - **IP Adresi:** Varsayılan ağ geçidi genellikle cihazın ağ yapılandırmasında belirtilen bir IP adresidir. Bu IP adresi, ağdaki diğer cihazlardan farklı olabilir ve genellikle yönlendirici veya gateway cihazın IP adresidir.
 
##  Subnet Mask Nedir?

  - **Alt Ağ Maskesi (Subnet Mask):** Alt ağ maskesi, bir IP adresinin hangi kısmının ağ kısmını ve hangi kısmının ev veya işyeri ağı içindeki cihazları temsil ettiğini belirten numaralardır. Bu maskeler, IP adresinin ağ kısmını ve host (ev sahibi) kısmını ayırmak için kullanılır.

  - **İşlevi:** Alt ağ maskesi, bir IP adresinin hangi bölümünün ağ kimliğini ve hangi bölümünün ev sahibi kimliğini tanımladığını belirler. Bu sayede, ağlar daha küçük alt ağlara bölünebilir.

  - **Örnek:** Örneğin, bir IPv4 adresi 192.168.1.100 ve alt ağ maskesi 255.255.255.0 ise, ilk üç oktet (192.168.1) ağ kimliğini belirtirken, sonuncu oktet (100) ev sahibi kimliğini belirtir.

  - **Önemi:** Alt ağ maskesi, ağların bölünmesini ve yönlendirme işlemlerini belirler. Ayrıca, IP adreslerinin ve alt ağların daha etkin yönetilmesini sağlar.

  - **Notasyon:** Alt ağ maskesi, genellikle on altılık sayılarla ifade edilir (örneğin, 255.255.255.0).  CIDR notasyonunda ise "/XX" formatında temsil edilir (örneğin, /24 alt ağ maskesi).

  - **Özel IP Adresleri ve Alt Ağ Maskeleri:** Belirli IP adresi aralıkları için belirli alt ağ maskeleri vardır. Örneğin, 192.168.0.0 ile 192.168.255.255 arasındaki IP adresleri için genellikle 255.255.0.0 (/16) alt ağ maskesi kullanılır.

## DHCP Nedir?
- **DHCP (Dynamic Host Configuration Protocol):** DHCP, ağdaki cihazlara otomatik olarak IP adresi, alt ağ maskesi, varsayılan ağ geçidi ve DNS sunucusu gibi ağ yapılandırma bilgilerini dağıtan bir ağ protokolüdür.

  - **İşlevi:** DHCP, ağa yeni bağlanan cihazlara (bilgisayarlar, akıllı telefonlar, tabletler vb.) dinamik olarak IP adresi ve diğer ağ yapılandırma bilgilerini sağlar. Bu sayede, cihazlar manuel olarak yapılandırma gereksinimi olmadan otomatik olarak ağa bağlanabilir.

  - **Çalışma Prensibi:** Bir cihaz ağa bağlandığında, DHCP sunucusu adı verilen bir cihaz, cihaza boşta olan bir IP adresi ve diğer ağ yapılandırma bilgilerini dinamik olarak atanmasını sağlar.

  - **Avantajları:** DHCP, ağ yöneticilerine IP adresi tahsisini kolaylaştırır ve hataları azaltır. Ayrıca, IP adresi çakışmalarını engeller ve IP adresi atama işlemini otomatikleştirir.

  - **Kullanım Alanları:** Ev ağlarından büyük kurumsal ağlara kadar geniş bir kullanım alanına sahiptir. Genellikle evlerdeki modem/router cihazları üzerinde bulunur ve ağdaki cihazların otomatik yapılandırılmasını sağlar.

  - **DHCP Süreci:**
    1. **Bağlanma (DHCP Discover):** Cihaz, ağa bağlandığında IP adresi almak için bir DHCP sunucusu arar.
    2. **IP Atama (DHCP Offer):** DHCP sunucusu, cihaza kullanılabilir bir IP adresi teklif eder.
    3. **Kabul (DHCP Request):** Cihaz teklifi kabul eder ve IP adresini kullanmaya başlar.
    4. **Onay (DHCP Acknowledgment):** DHCP sunucusu, cihazın IP adresini onaylar ve diğer ağ yapılandırma bilgilerini de gönderir.


## Port Nedir?
- **Port:** Bilgisayar ağlarında, bir cihazın dış dünya ile iletişim kurarken kullandığı numaralı kapıdır. Her bir port, belirli bir türdeki iletişim için ayrılmıştır. Örneğin, HTTP trafiği için genellikle 80. port, HTTPS trafiği için 443. port kullanılır. Portlar, iletişimde hangi türdeki verinin hangi uygulamaya veya hizmete yönlendirileceğini belirtir.

- **Port Yönlendirme (Port Forwarding):** Port yönlendirme, gelen bağlantıları belirli bir porttan alıp, ağdaki başka bir cihaza veya hizmete yönlendiren bir ağ yönlendirme tekniğidir. Bu genellikle ev ağlarında veya işyerlerinde kullanılır ve belirli bir port numarasına gelen trafiği belirli bir cihaza veya uygulamaya iletmek için yapılır.

  - **Neden Kullanılır?** Port yönlendirme, özellikle evdeki veya işyerindeki sunuculara dışarıdan erişim sağlamak veya belirli bir uygulamanın dış dünya ile iletişim kurmasını sağlamak için kullanılır. Örneğin, bir ev ağındaki bir cihazın oyun sunucusu veya web sunucusu gibi hizmetlerine dışarıdan erişim sağlamak için port yönlendirme yapılabilir.

  - **Nasıl Çalışır?** Bir yönlendirici veya firewall üzerinde yapılandırılan port yönlendirme kuralları, gelen bağlantıları belirli bir porttan alır ve bu bağlantıları ağdaki belirli bir cihaza veya hizmete yönlendirir.

  - **Örnek:** Bir evdeki IP kamerasına internetten erişim sağlamak istediğinizi varsayalım. IP kamerası belirli bir portta (örneğin, 8080) çalışıyorsa, yönlendiriciye yapılandırılan port yönlendirme kuralıyla, dış dünyadan belirli bir IP adresi ve port numarasına gelen istekler, evdeki IP kamerasına iletilir.
