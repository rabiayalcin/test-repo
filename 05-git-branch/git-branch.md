# Git Branch 

Bu doküman, Git ve GitHub üzerinde `branch (dal)` kullanımını, oluşturma–push–pull–merge ve silme işlemlerini adım adım açıklar.

---

```bash 

## Branch Yapısı

Genellikle 2 temel branch kullanılır:

master:
Canlı sunucularda çalışan, testleri tamamlanmış ve hazır kodlar bulunur.

dev (development):
Geliştirme yapılan, hataların düzeltildiği branch’tir.

Akış şu şekildedir:

DEV → test edilir → hatalar düzeltilir → MASTER


İhtiyaca göre feature, test, hotfix gibi istediğimiz kadar branch oluşturabiliriz.


Branch Listeleme

git branch --> Sadece local branch’leri gösterir.

git branch --all --> Hem local hem remote (origin) branch’leri gösterir.


GitHub Üzerinden Branch Oluşturma

GitHub’a gidilir

Find branch alanından dev branch’i, master üzerinden oluşturulur

Master’daki tüm kodlar dev’e otomatik olarak gelir


Remote Branch’i Locale Çekme
git fetch --> GitHub’da oluşturulan branch’leri local’e getirir

Sonrasında:
git branch --all

çıktısında şunlar görülür:

master

remotes/origin/master

remotes/origin/dev


Local Branch Oluşturma ve Geçiş

git branch dev --> Localde dev branch’i oluşturur (aktif değildir)

git checkout dev --> Aktif branch artık dev olur

git branch --all

Aktif branch yeşil renkte dev olarak görünür

Dosya Ekleme, Commit ve Push

Yeni bir dosya oluştur

Durumu kontrol et:

git status


Dosyaları ekle ve commit at:

git add .
git commit -m "Yeni dosya eklendi"


Dev branch’ine push et:

git push -u origin dev


📌 Bu dosya sadece dev branch’inde bulunur, master’da görünmez.

Branch’ler Arası Dosya Farkı
git checkout master

Klasörde dev branch’te oluşturulan dosyalar görünmez

GitHub’dan Locale Dosya Çekme

GitHub üzerinden dev branch’ine dev.html dosyası eklenirse:

git pull origin dev


GitHub’daki dev branch’i local dev branch’ine çekilir

Merge (Birleştirme) İşlemi

Testleri tamamlanan kodları master’a almak için:

git checkout master
git merge dev


Sonuç:

dev.html

yeni metin belgesi

master branch’ine eklenmiş olur.

Ardından:

git status
git push -u origin master


İstenirse Pull Request ile de merge yapılabilir.

Yeni Branch (test) Oluşturma

GitHub’da test adında yeni branch oluşturulduktan sonra:

git fetch
git branch --all


remotes/origin/test görünür

Localde oluşturmak için:

git branch test

Branch Silme
GitHub Üzerinden Silme

Branch listesinden silinecek branch’in yanındaki 🗑️ ikonuna basılır

Gerekirse Restore ile geri alınabilir

Local ve Remote Temizleme 

git fetch -p --> Silinmiş remote branch’leri localden temizler

git branch --all


Eğer branch hâlâ localde varsa:

git branch -D test --> test branch’i localden de silinir

Özet

dev → geliştirme

master → canlı ortam

fetch → remote branch’leri gör

pull → kodu indir

push → kodu yükle 

merge → branch’leri birleştir

-D → local branch sil


