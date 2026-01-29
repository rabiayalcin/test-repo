# Merge Conflict 

`merge conflict` aynı dosyanın aynı satırında iki farklı branchde değişiklik yapıldığında olur.Git bunların hangisinin doğru olduğuna karar veremez.

---> Çözüm olarak dosya elle düzeltilir.Git add . yapılır ve git commit atılır.

---

```bash 

git conflict --> dosyayı elle düzelt --> git add . --> git commit


Merge conflict’te dosya içinde sırasıyla

<<<<<<< → ======= → >>>>>>> işaretleri görülür.

Doğru kod seçilip bu işaretler silinir, sonra git add . ve git commit yapılır.


*** SENARYOLU SORU

masterda index.html e <p> hos geldin master </p1> giriliyor

devde    index.html e <p> hos geldin dev</p1> giriliyor.

mastera geçip git merge dev yaparsan sana merge conflict hatası verdi !!!!


<<<<<<< HEAD

<p>Hoş geldin master</p>

=======

<p>Hoş geldin dev</p>

>>>>>>> dev
 
devdekini seçmek istiyorsun naparsın ??

<p> hos geldin dev </p>  git add . git commit -m "devdeki komut seçildi." 



****Tek cümlelik özet:

Merge conflict’te istenen branch’in kodu bırakılır, conflict işaretleri silinir ( <<< === >>> ), git add . ve git commit ile işlem tamamlanır.



