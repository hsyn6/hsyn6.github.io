---
layout: post
title: Linux
---

Updatedb: locate komutu bir dosyayı dizini aramada kullanılır. Bu aramayı mlocate.db altında arama yapar. Bu db güncellenmezse o an aradığımız dosya/dizini bulamaz. Bunun için updatedb komutuyla bu veritabanı güncellenir. (updatedb sudo yetkisiyle çalışır.)
Find ile locate arasındaki fark da bundan kaynaklanır. Find gerçek zamanlı belirtilen dizin ve altındaki bütün dizinlerde arama yapar. Locate ise kataloglanmış veritabanında arama yaptığı için find komutuna göre daha hızlı cevap verir. 

find  /var   -type f -perm 777 -exec chmod 644 {}  \ ; -> bu komut /var dizini altında ki izinleri 777 olan dosyları(-type f , dizin için d) bulur ve bu dosyaların izinlerini 644 olarak değiştirir.
Umask: Dosya ve dizinlerin varsayılan izinlerini gösterir. Aslında izin verilmeyen değer gösterilir.
Örneğin;
  umask 
  0022 ise bu aslında 777-022-> 755 şeklinde varsayılan dizin izindir.
  0022 ise bu aslında 666-022-> 644 şeklinde varsayılan dizin izindir.
 Bu varsayılan izinleri değiştirebiliriz.  Umask 0011 gibi

Eğer bir dosyayının silinmesini istemiyorsak chattr +i dosya şeklinde komut vererek yapabiliriz. Bu komutla root yetkisiyle dahi dosya silinmez.  Bu işlemi geri almak içinde -i parametresiyle bu komut çalıştırılır.

Tar: tar komutu dosya ve dizinleri sıkıştırmada kullanılan dizindir. 
Örneğin;   tar -cvzf home.tar.gz  /home  komutu ile home dizini altındaki dosyaları home.tar.gz dosyasına sıkıştırılarak arşivlenir.
Tekrardan açmak için ise   tar -xvzf home.tar.gz  şeklinde açılır. 

Stat: belirttiğimiz dosya dizin hakkında bilgi verir.
