# Git Ignore (.gitignore)

`.gitignore`, Git tarafından **takip edilmesini istemediğimiz** dosya ve klasörleri belirtmek için kullanılır.

---

## 1- Temel Senaryo

Diyelim ki şu dosyalar var ve **hiçbiri add edilmemiş**:

- `.gitignore`
- `data.txt`
- `dizin/`

```bash
git status
➡️ Üçü de kırmızı (untracked) görünür.

2- Tek Bir Dosyayı Ignore Etme

data.txt dosyasını .gitignore içine yazalım:


Tekrar:

git status

➡️ Artık terminalde sadece:

.gitignore

dizin/

kırmızı görünür.
data.txt Git tarafından yok sayılır.

3- Bir Klasörü Tamamen Ignore Etme

dizin/ klasörünü de ignore etmek istersek:

gitignore içine dizin/*

git status

➡️ Bu sefer sadece .gitignore kırmızı kalır.

4- Klasör İçinde Sadece Tek Dosyayı Takip Etme (Önemli)

🎯 Amaç:

dizin/ klasöründe sadece deneme.txt dosyası takip edilsin,
diğer her şey ignore edilsin.

Çözüm:
gitignore içine 
dizin/*
!dizin/deneme.txt

git status


➡️ Bu durumda:

.gitignore

dizin/deneme.txt

kırmızı görünür.


5- Stage ve Commit Davranışı
git add .


➡️ Sadece:

.gitignore

dizin/deneme.txt

stage alanına alınır (yeşil görünür).

git commit -m "add gitignore rules and track deneme.txt"
git push


⚠️ Önemli Not

Commit edilmiş bir dosyayı .gitignore’a alsan bile GitHub görmeye devam eder.

📌 Çünkü:

.gitignore → gelecek dosyalar içindir

Daha önce commit edilmiş dosyaları geri almaz

✅ En Doğru Pratik

Projeye başlarken ilk iş .gitignore oluştur

Commit & pushlamak istemediğin dosyaları önceden buraya ekle


📍 Mini Özet

.gitignore → takip edilmemesi gerekenler

dizin/* → klasörün tamamını ignore eder

!dizin/deneme.txt → ignore dışına çıkarır

Commit edilmiş dosya → ignore’dan etkilenmez



