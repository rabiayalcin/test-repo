
📌 GIT PUSH ve GIT PULL

🔼 git push
git push, local (bilgisayarındaki) repoda yaptığın değişiklikleri GitHub’daki uzak repoya göndermek için kullanılır.


Ne zaman kullanılır?
Dosya eklediysen
Dosya sildiysen
Kodda değişiklik yaptıysan
➡️ ve bu değişiklikleri commit ettiysen


Akış:
git add .
git commit -m "commit mesajı"
git push

Mantık:
LOCAL  --->  GITHUB


🔽 git pull
git pull, GitHub’daki güncel hali kendi bilgisayarına almak için kullanılır.

Ne zaman kullanılır?
GitHub’dan dosya eklediysen
Başka biri aynı repoya commit attıysa
Başka bir bilgisayardan değişiklik yaptıysan

Mantık:
GITHUB  --->  LOCAL


Kısa Karşılaştırma
Komut	    Ne yapar?
git push	Localdeki commitleri GitHub’a gönderir
git pull	GitHub’daki değişiklikleri locale çeker


⚠️ Önemli İpucu
git push commit olmadan çalışmaz
git pull atmadan önce localde değişiklik varsa conflict çıkabilir
Takım çalışmasında güne başlarken ilk iş git pull atmak iyi pratiktir


📍 Özet
PUSH = LOCAL  →  GITHUB
PULL = GITHUB →  LOCAL


Add    → commit’e hazırlık
Commit → kayıt alma
Push   → kayıtları GitHub’a gönderme


🔹 Untracked Files (Takip Edilmeyen Dosyalar)

Örnek: style.css dosyası commit’e girmiyor

➡️ Çözüm:

git add style.css
git commit -m "add style css"

📌 Untracked dosya commit’e giremez, önce git add yapılmalıdır.


🔹 Local ve Remote Branch Mantığı
HEAD → dev       (bilgisayarımdaki aktif branch)
origin/dev       (GitHub’daki dev branch)


HEAD → şu an çalıştığın branch’i gösterir

origin/* → remote (GitHub) tarafındaki branch’lerdir



🔹 Commit vs Push (Çok Önemli)

commit = kendin için kayıt

push = ekiple paylaşma

📌 Pratik:
❌ Bitmemiş kod → local’de kalır
✅ Hazır kod → push edilir



🔹Mini Ezber 
🔽 GIT PULL
Remote gerideyse → bir şey olmaz
Remote ilerideyse → commit’ler locale gelir

🔼 GIT PUSH
Remote gerideyse → commit’ler remote’a gider
Remote ilerideyse → ❌ red / hata verir

⚠️ İki taraf da ilerideyse
➡️ Conflict riski vardır




