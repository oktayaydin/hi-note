---
description: >-
  Oracle Linux veya Centos üzerinde Nginx kurmak için aşağıdaki adımları takip
  edebilirsiniz:
icon: server
---

# Nginx Kurulum

#### 1. **Sistemi Güncelleyin**

Sisteminizi güncellediğinizden emin olun:

```bash
sudo yum update -y
```

***

#### 2. **EPEL Deposu Ekleyin**

Nginx genellikle EPEL (Extra Packages for Enterprise Linux) deposunda bulunur. EPEL deposunu eklemek için:

```bash
sudo yum install epel-release -y
```

***

#### 3. **Nginx'i Yükleyin**

Nginx paketini yükleyin:

```bash
sudo yum install nginx -y
```

***

#### 4. **Nginx'i Başlatın**

Kurulumdan sonra Nginx hizmetini başlatın:

```bash
sudo systemctl start nginx
```

***

#### 5. **Nginx'i Otomatik Başlatmaya Ayarlayın**

Nginx'in sistem açılışında otomatik olarak başlamasını sağlayın:

```bash
sudo systemctl enable nginx
```

***

#### 6. **Güvenlik Duvarını Yapılandırın**

Oracle Linux'ta genellikle **firewalld** etkin durumdadır.&#x20;

HTTP ve HTTPS trafiğine izin vermek için:

```bash
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --permanent --add-service=https
sudo firewall-cmd --reload
```

***

#### 7. **Nginx'i Test Edin**

Nginx'in doğru bir şekilde çalışıp çalışmadığını kontrol etmek için sunucunun IP adresini veya `localhost`'u tarayıcınıza yazın:

```arduino
http://localhost
```

Varsayılan Nginx karşılama sayfasını görmelisiniz.

***

#### 8. **Nginx Konfigürasyonunu Düzenleyin**

Nginx'in ana konfigürasyon dosyası genellikle şu konumda bulunur:

```bash
/etc/nginx/nginx.conf
```

Ek site yapılandırmaları için `/etc/nginx/conf.d/` dizinini kullanabilirsiniz.

***

#### 9. **Nginx'i Yeniden Başlatın**

Konfigürasyon değişikliklerinden sonra Nginx'i yeniden başlatmayı unutmayın:

```bash
sudo systemctl restart nginx
```

***

#### 10. **Nginx Sürümünü Kontrol Edin**

Nginx'in doğru bir şekilde kurulduğunu ve çalıştığını doğrulamak için sürüm kontrolü yapabilirsiniz:

```bash
nginx -v
```
