
# Git Push & Git Pull

Git push ve git pull, local (bilgisayar) ile remote (GitHub) arasındaki senkronizasyonu sağlar.

---

## 1- git push

`git push`, local repoda yaptığın **commit’leri** GitHub’daki uzak repoya göndermek için kullanılır.

### Ne Zaman Kullanılır?
- Dosya eklediysen
- Dosya sildiysen
- Kodda değişiklik yaptıysan
- ➡️ Ve bu değişiklikleri commit ettiysen

### Kullanım Akışı
```bash
git add .
git commit -m "commit mesajı"
git push

LOCAL  --->  GITHUB

2- git pull

git pull, GitHub’daki en güncel hali kendi bilgisayarına almak için kullanılır.

Ne Zaman Kullanılır?

GitHub’dan dosya eklediysen

Başka biri aynı repoya commit attıysa

Başka bir bilgisayardan değişiklik yaptıysan

Mantık
GITHUB  --->  LOCAL

3- Kısa Karşılaştırma
Komut	Ne Yapar?
git push	Local’deki commit’leri GitHub’a gönderir
git pull	GitHub’daki değişiklikleri locale çeker
⚠️ Önemli İpuçları

git push commit olmadan çalışmaz

git pull atmadan önce local’de değişiklik varsa conflict çıkabilir

Takım çalışmasında güne başlarken ilk iş git pull atmak iyi pratiktir

📍 Özet
PUSH = LOCAL  →  GITHUB
PULL = GITHUB →  LOCAL


Add → commit’e hazırlık

Commit → kayıt alma

Push → kayıtları GitHub’a gönderme



🔹 Untracked Files (Takip Edilmeyen Dosyalar)

Örnek: style.css dosyası commit’e girmiyor

➡️ Çözüm
git add style.css
git commit -m "add style css"


📌 Untracked dosyalar commit’e giremez, önce git add yapılmalıdır.



Local ve Remote Branch Mantığı
HEAD → dev        (bilgisayarımdaki aktif branch)
origin/dev        (GitHub’daki dev branch)


HEAD → şu an çalıştığın branch’i gösterir

origin/* → GitHub’daki (remote) branch’lerdir

🔹 Commit vs Push (Çok Önemli)

commit = kendin için kayıt

push = ekiple paylaşma

Pratik

Bitmemiş kod → local’de kalır

Hazır kod → push edilir


🔹 Mini Ezber
🔽 GIT PULL

Remote gerideyse → sorun yok

Remote ilerideyse → commit’ler locale gelir

🔼 GIT PUSH

Remote gerideyse → commit’ler remote’a gider

Remote ilerideyse → ❌ red / hata verir

⚠️ İki taraf da ilerideyse
➡️ Conflict riski vardır.






