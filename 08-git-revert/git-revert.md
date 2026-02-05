# Git Revert 

`git revert` pushlanmış hatalı commitleri etkisiz hale getirmek için atılmış yeni bir commit işlemidir.Commit silinmez geçmişte durur fakat etkisi yoktur yaptığı değişiklikler geri alınır.
`git reset` ise henüz pushlanmamış commitleri geçmişten tamamen silme işlemidir.

---

```bash 

 🔹 git reset 
 - Commit’i tamamen siler 
 - Yeni commit oluşturmaz 
 - Sadece local için güvenlidir
 - Pushlanmamış commitlerde kullanılır 
 
 🔹 git revert
 - Commit’i silmez
 - Hatanın tersini yapan yeni bir commit oluşturur
 - Pushlanmış commitlerde güvenlidir
 - Takım çalışmalarında kullanılır


 Pushlandıysa → REVERT
 
 Pushlanmadıysa → RESET


 A — B — C — D (hatalı) 

 D pushlanmadıysa → git reset 
 
 D pushlandıysa → git revert 


Son commit pushlanmadıysa (tamamen siler) --> git reset --hard HEAD~1

Pushlanmış hatalı commit’i geri alır (yeni commit oluşturur) --> git revert <commit-hash>


--soft  → commit silinir, dosyalar staged kalır
--mixed → commit silinir, dosyalar unstaged olur (default)
--hard  → commit + dosyalar tamamen silinir ⚠️


