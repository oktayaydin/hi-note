---
description: >-
  Oracle Linux veya Centos üzerinde Nginx'i tamamen kaldırmak istiyorsanız
  aşağıdaki adımları izleyebilirsiniz:
icon: server
---

# Nginx Silme

#### 1. **Nginx Hizmetini Durdurun**

Öncelikle, Nginx çalışıyorsa hizmetini durdurun:

```bash
sudo systemctl stop nginx
```

#### 2. **Nginx'i Devre Dışı Bırakın**

Nginx'in sistem başlangıcında otomatik olarak başlamasını devre dışı bırakın:

```bash
sudo systemctl disable nginx
```

#### 3. **Nginx Paketini Kaldırın**

Nginx'i paket yöneticisi aracılığıyla kaldırın:

```bash
sudo yum remove nginx
```

#### 4. **Nginx Konfigürasyon Dosyalarını Silin**

Nginx'in kaldırılması sırasında yapılandırma dosyaları silinmez. Bunları manuel olarak temizleyebilirsiniz:

```bash
sudo rm -rf /etc/nginx
```

#### 5. **Log Dosyalarını Silin**

Nginx log dosyaları varsa bunları da temizlemek için:

```bash
sudo rm -rf /var/log/nginx
```

#### 6. **Bağımlılıkları Temizleyin**

Sistem üzerinde kullanılmayan bağımlılıkları temizlemek için:

```bash
sudo yum autoremove
```

#### 7. **Doğrulama**

Nginx'in tamamen kaldırıldığından emin olmak için:

```bash
nginx -v
```

Bu komut "command not found" döndürüyorsa Nginx başarıyla kaldırılmıştır.

