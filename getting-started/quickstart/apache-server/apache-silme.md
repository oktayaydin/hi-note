---
description: >-
  Oracle Linux veya Centos üzerinde Apache HTTP Server'ı (httpd) tamamen
  kaldırmak için aşağıdaki adımları takip edebilirsiniz:
icon: server
---

# Apache Silme

#### 1. **Apache Hizmetini Durdurun**

Öncelikle Apache hizmetini durdurun:

```bash
sudo systemctl stop httpd
```

***

#### 2. **Apache'yi Devre Dışı Bırakın**

Apache'nin sistem başlangıcında otomatik olarak çalışmasını devre dışı bırakın:

```bash
sudo systemctl disable httpd
```

***

#### 3. **Apache Paketini Kaldırın**

Apache HTTP Server'ı paket yöneticisi ile kaldırın:

```bash
sudo yum remove httpd -y
```

***

#### 4. **Konfigürasyon Dosyalarını Silin**

Apache'nin kaldırılması sırasında konfigürasyon dosyaları silinmeyebilir. Bunları manuel olarak kaldırabilirsiniz:

```bash
sudo rm -rf /etc/httpd
```

***

#### 5. **Log Dosyalarını Silin**

Apache tarafından oluşturulan log dosyalarını da temizlemek için:

```bash
sudo rm -rf /var/log/httpd
```

***

#### 6. **Bağımlılıkları Temizleyin**

Apache'yi yüklerken yüklenen kullanılmayan bağımlılıkları kaldırmak için:

```bash
sudo yum autoremove

```

***

#### 7. **Doğrulama**

Apache'nin tamamen kaldırıldığından emin olmak için:

```bash
httpd -v
```





