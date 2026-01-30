
# Git Rebase 

`rebase` kendi branchimde oluşturduğum commitleri başka bi branchin sonuna taşımaktır .
 
```bash 

diyelim devde A---B---C VAR
feature branchde  X---Y var

--->feature branchdeyken; git rebase dev dedim

A--B--C--X--Y olur

rebaseyi sadece kendi branchimde yapabilirim

git rebase kullanırken conflict çıkarsa çözülür fakat hemen git add. ve commit atılmaz git add . ve git rebase --continue komutu kullanılır.


**MERGE VE REBASE FARKI**
Merge:
“Dev’de ne varsa olduğu gibi al, geçmişi bozma”

Rebase:
“Benim yaptıklarım, dev’in en güncel halinin üstüne yazılmış gibi dursun”


1️⃣ Rebase = kendi commit’lerini, dev’in devamına almak
2️⃣ Sadece kişisel branch’te yapılır (feature)
3️⃣ Rebase conflict’te git commit yok → git rebase --continue var


>>>rebase hatalı kodu düzeltemez sadece commitlerin yerini değiştirir.Hatalı kod yeri değişse bile yine hatalıdır.

 
1️⃣ Rebase sonrası commit ID’leri (hash) değişir.
 
Commit ID neden değişiyor? 

örnek:Senin branch’te şu commit var:

X (ID: 111aaa)

Rebase yaptın.

Git ne yapıyor?

“Bu commit’i alıyorum, silip, aynısını yeniden yazıyorum”

Yeni durum:

X (ID: 999zzz)

❓ Soru

Kod aynıysa neden ID değişti?

 Cevap ---> Çünkü:Git için bu artık YENİ bir commit

 Rebase = commit’i kopyalayıp yeniden oluşturmak


2️⃣ Push edilmiş branch’te neden dikkatli olunması gerekiyor ?
📌 Senaryo

1️⃣ Sen feature branch’i push ettin
2️⃣ Arkadaşın o branch’ten çekti
3️⃣ Sen rebase yaptın

❓ Soru

Ne bozulur?

❌ Cevap

Senin:

111aaa commit’i YOK
999zzz commit’i VAR


Arkadaşının:

111aaa commit’i VAR


➡️ Git geçmişi uyuşmaz
➡️ Branch bozulur

📌 O yüzden:

Rebase → sadece kimse kullanmıyorken


3️⃣ --force-with-lease neden var?
📌 Senaryo

1️⃣ Sen branch’i push ettin
2️⃣ Rebase yaptın
3️⃣ Push atacaksın

❓ Soru

Normal push niye olmuyor?

❌ Cevap

Git der ki:

Remote geçmiş ≠ senin geçmişin

❓ Soru

--force atsak?

❌ Risk:

Arkadaşının commit’ini de siler

✅ Çözüm
git push --force-with-lease

Ne yapar?
Eğer remote aynen bildiğim gibiyse → yaz
Değilse → DUR



4️⃣ Rebase yukarıdan aşağı neden önemli?
📌 Senaryo

Rebase dosyası:

pick A
pick B
pick C

Git hangisini önce uygular?

ÖNCE A → sonra B → sonra C


📌 Yani:

En üst = en eski

En alt = en yeni

❗ Squash yaparken sıralama çok önemlidir.



5️⃣ Rebase iptal edilince ne olur?
📌 Senaryo

 Rebase başlattın --> Conflict çıktı

❓ Soru

Branch bozuldu mu?

Hayır.

git rebase --abort

Git der ki:

Hiç rebase yapmamış gibi olalım


6️⃣ “Rebase kodu düzeltmez” ne demek?
📌 Senaryo

Kodun hatalı:

if (x = 5) { ... }  // hata

Rebase yaptın.

Hata gider mi? Hayır.

Rebase şunu yapar:

Sadece commitleri taşır

Kod: Önce hatalıysa → sonra da hatalıdır

