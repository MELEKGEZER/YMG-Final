

# Melek Gezer HTML Server - Docker ile Nginx Web Sunucu

## Proje Açıklaması
Bu proje, Docker kullanarak Nginx üzerinden basit bir HTML statik web sunucusu oluşturur. Proje, **Melek Gezer**'in kişisel web sayfası için HTML dosyalarını içerir ve Jenkins Pipeline ile otomatik olarak Docker imajı oluşturulup çalıştırılmasını sağlar.

## Özellikler
- **Docker ile Web Sunucu:** HTML dosyaları, Docker container'ı içinde çalışan Nginx sunucusuyla sunulur.
- **Jenkins Pipeline:** Proje, Jenkins kullanılarak otomatik CI/CD işlemlerine sahiptir.
- **Statik Web Sayfası:** `index.html` dosyası, Melek Gezer'in hizmetlerini tanıtan içerikle gelir.
- **Kolay Erişim:** Web sayfasına `localhost:4444` üzerinden erişilebilir.

## Kullanılan Teknolojiler
- **Docker** (Containerization için)
- **Nginx** (Web sunucu olarak)
- **Jenkins** (Sürekli Entegrasyon ve Sürekli Dağıtım - CI/CD)
- **HTML** (Web sayfası içeriği)

## Kurulum ve Çalıştırma

1. **Docker'ın Yüklü Olduğundan Emin Olun:** Docker'ı [buradan](https://www.docker.com/get-started) indirip kurabilirsiniz.
2. **Jenkins'in Yüklü ve Yapılandırılmış Olması Gerekiyor:** Jenkins'i [buradan](https://www.jenkins.io/download/) indirip kurabilirsiniz.

### 1. Projeyi Klonlayın

```bash
git clone https://github.com/username/melekgezer-html-server.git
cd melekgezer-html-server
```

### 2. Docker İmajını Oluşturun

```bash
docker build -t melekgezer-html-server .
```

### 3. Docker Container'ı Çalıştırın

```bash
docker run -d --name melekgezer-container -p 4444:80 melekgezer-html-server
```

### 4. Web Sayfasına Erişim

Uygulamayı çalıştırdıktan sonra, web sayfanıza aşağıdaki URL'den erişebilirsiniz:

```
http://localhost:4444
```

## Jenkins ile Sürekli Entegrasyon (CI/CD)

Proje, Jenkins ile sürekli entegrasyon için yapılandırılmıştır. Aşağıdaki adımları izleyerek Jenkins pipeline'ını çalıştırabilirsiniz:

1. Jenkins sunucusunda yeni bir pipeline oluşturun.
2. Pipeline'ı bu projedeki `Jenkinsfile` ile ilişkilendirin.
3. Pipeline çalıştırıldığında, Docker imajı oluşturulacak ve container başlatılacaktır.

## Yapılandırma

Eğer Nginx yapılandırmasında değişiklik yapmak isterseniz, `nginx.conf` dosyasını düzenleyebilirsiniz. Değişiklik yaptıktan sonra aşağıdaki adımları takip edin:

1. `nginx.conf` dosyasındaki gerekli değişiklikleri yapın.
2. Docker imajını yeniden oluşturun:
   ```bash
   docker build -t melekgezer-html-server .
   ```
3. Container'ı yeniden başlatın:
   ```bash
   docker restart melekgezer-container
   ```

## Katkıda Bulunma

Bu projeye katkı sağlamak isterseniz, aşağıdaki adımları takip edebilirsiniz:

1. Projeyi **fork**'layın.
2. Değişikliklerinizi yapın ve bir **pull request** gönderin.
3. Geri bildirim ve katkılar her zaman memnuniyetle karşılanır!



