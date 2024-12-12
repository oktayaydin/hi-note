---
description: >-
  Oracle Linux veya Centos üzerinde Apache HTTP Server'ı (httpd) kurmak için
  aşağıdaki adımları takip edebilirsiniz:
icon: server
---

# Apache Kurulum

1\. **Sistemi Güncelleyin**

Öncelikle sistemin güncel olduğundan emin olun:

```bash
sudo yum update -y
```

***

#### 2. **Apache HTTP Server'ı Yükleyin**

Apache'nin Oracle Linux üzerindeki adı "httpd" paketidir. Yüklemek için:

```bash
sudo yum install httpd -y
```

***

#### 3. **Apache'yi Başlatın**

Apache hizmetini başlatın:

```bash
sudo systemctl start httpd
```

***

#### 4. **Apache'yi Otomatik Başlatmaya Ayarlayın**

Apache'nin sistem yeniden başlatıldığında otomatik çalışmasını sağlamak için:

```bash
sudo systemctl enable httpd
```

***

#### 5. **Güvenlik Duvarını Yapılandırın**

Eğer sisteminizde bir güvenlik duvarı (firewalld) etkinse, Apache için gerekli portları açmanız gerekir:

```bash
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --permanent --add-service=https
sudo firewall-cmd --reload
```

***

#### 6. **Apache'nin Çalıştığını Doğrulayın**

Apache'nin doğru bir şekilde çalışıp çalışmadığını kontrol etmek için tarayıcınıza sunucunun IP adresini veya `localhost` yazın:

```arduino
http://localhost
```

Apache'nin varsayılan "It works!" sayfasını görmelisiniz.

***

#### 7. **Konfigürasyon Dosyalarını Düzenleyin**

Apache'nin ana konfigürasyon dosyası şurada bulunur:

```bash
/etc/httpd/conf/httpd.conf
```

