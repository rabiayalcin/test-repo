
# Git Stash 

 `Git stash` , yaptığın ama commit atmadığın değişiklikleri geçici olarak saklar.
>> Şuan bu işi bırakmam lazım ama silmek istemiyorum dediğimiz anlarda kullanırız.

```bash

# Ne zaman kullanılır?
Kod yazıyorsun ama yarım
Acil branch değiştirmen gerekiyor
Commit atmak istemiyorsun (çünkü iş bitmedi)
--> İşte tam burada stash devreye girer.


*** SENARYOLU
git featurde geliştirme yapıyorsun acil masterda hotfix çıktı ne yapman gerekir
gidersin featurde git stash dersin

git checkout master diyip mastera geçersin hotfixi çözer git add . ve commit atarsın şimdi deploy olmaması için hotfixi deve de taşımam lazım

git checkout dev dersin ----> ve git merge master yaparsın masterdaki hotfix değişikliklerini devede alırsın (git add. ve commit atmana gerek yok git otomatik atar) sonra;

featureye dönersin ve --> git stash pop dersin stash listeden silinir ve kod kaldığın yerden geri gelir.


git stash apply şeklinde kullanırsan da stash listede kalmaya devam eder kod yine gelir
git stash list dersen listesini verir

listedeki belirli bir stashi almak istiyorum ne yaparım >>>git stash pop stash{0}dersin

mesaj ekleme : git stash push - m "login form yarıda kaldı".


1 tane stash silmek için : git stash drop stash{0}
hepsini silmek için de git stash clear
 

pop => getir +listeden sil
apply => getir +listeden silme


