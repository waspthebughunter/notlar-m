Tags : #web-vulns

Konu : Directory Listing zafiyeti

# Directory Listing Zafiyeti Nedir?
Directory Listing zafiyeti, bir web sunucusunun belirli bir dizindeki dosya ve klasörleri kullanıcıya görüntülemesidir. Saldırgan bu zafiyetten faydalanarak sunucu yapısı hakkında bilgi toplayabilmekte ve zaman zaman sunucudaki bazı önemli alanlar ifşa olabilmektedir.



# Directory Listing Zafiyeti Nasıl Tespit Edilir?

- Directory Listing zafiyetini tespit etmek için uygulamanın çalıştığı sunucuya belirli dizinler için GET requestinde bulunmamız gerekmektedir. 
- Web sitesinde bulunan dizinleri manuel olarak incelemek işe yarayabilmektedir.
	- Web sitesinin kullanıcı tarafındaki kaynak koduna bakarak objeleri çekerek önümüze getirdiği alanları kontrol etmek gerekmektedir.
- Belirli dizinlerin olduğu bir wordlist dosyası ile işleri otomatize ederek kontrol edilebilmektedir.
	- [Seclists](https://github.com/danielmiessler/SecLists) de bulunan wordlistler.
	- [fuzz.txt](https://github.com/Bo0oM/fuzz.txt) wordlisti.
	- [Assetnote](https://wordlists.assetnote.io/) da bulunan wordlistler.
	- [fuzzdb](https://github.com/fuzzdb-project/fuzzdb) de bulunan wordlistler.
- Otomatik tarama araçlarını (örn : [[Burp Suite]],[[OWASP ZAP]]) kullanarak tespit edilebilmektedir.


# Directory Listing Zafiyeti ile Nasıl Mücadele Edilir?
Directory listing zafiyetiyle mücadele etmek için aşağıdaki önlemleri alabilirsiniz:

1. **Sunucu Yapılandırması:**
    
    - Web sunucunuzun yapılandırmasını gözden geçirin ve dizin listeleme özelliğini devre dışı bırakın. Bu, genellikle sunucu konfigürasyon dosyalarında (örneğin, Apache'de `httpd.conf` veya Nginx'de `nginx.conf`) yapılır.
    
    Apache örneği (`.htaccess` ile de yapılabilir):    
    ```
    Options -Indexes
    ```
    
    Nginx örneği:    
    ```
    location /klasor/ {     
    autoindex off; 
    }
	```
    
2. **Dizin İndex Dosyası:**
    
    - Dizinlerin içeriğini açıkça göstermek yerine, her dizin için bir index dosyası oluşturun. Örneğin, `index.html`, `index.php` gibi dosyalar kullanarak dizin içeriğini gizleyebilirsiniz.
3. **Web Güvenlik Duvarları:**
    
    - Web uygulamanızın önüne bir web güvenlik duvarı (WAF) ekleyerek, istenmeyen dizin listeleme girişimlerini engelleyebilirsiniz.
4. **Otomatik Güvenlik Taramaları:**
    
    - Web uygulamanızı düzenli aralıklarla otomatik güvenlik tarama araçlarıyla tarayarak potansiyel zafiyetleri erken aşamada tespit edin.
5. **Yetkilendirme ve Kimlik Doğrulama:**
    
    - Web uygulamanıza erişim kontrolü ekleyin. Kullanıcıların sadece yetkili dizinlere erişebilmesini sağlamak için kimlik doğrulama ve yetkilendirme mekanizmalarını uygulayın.
6. **Güncel Yazılımlar:**
    
    - Web sunucu yazılımınızı ve kullanılan diğer yazılımları güncel tutun. Güncellemeler genellikle güvenlik açıklarını düzeltir.
7. **İzin Kontrolleri:**
    
    - Sunucu üzerindeki dosya ve dizinlere uygun izin kontrollerini uygulayın. Sadece gerekli kullanıcılara ve süreçlere gerekli erişim izinlerini verin.
8. **Güvenlik Politikaları ve Eğitim:**
    
    - Güvenlik politikalarını tanımlayın ve personelinizi düzenli olarak güvenlik eğitimlerine tabi tutun. Bilinçli kullanıcılar, güvenlik tehditlerine karşı daha iyi korunabilirler.

Bu önlemler, directory listing zafiyetiyle mücadele etmek için genel olarak etkili olacaktır.