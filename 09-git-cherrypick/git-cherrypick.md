# Git Cherry Pick 

`Git cherry pick` başka bir branchde bulunan tek bir commiti (veya birden fazla seçili commiti) alıp,bulunduğun branche taşımak için kullanılır.

---> Hepsini istemiyorum sadece şu commit gelsin denilen durumlarda kullanılır.

---

```bash 

### Ne Zaman Kullanılır?

dev branch’inde geliştirme yapıyorsun

Orada yapılmış sadece 1 fix commit’inin master branch’ine gitmesi gerekiyor

Ancak dev branch’ini komple merge edemezsin

Bu durumda merge yerine cherry-pick kullanılır.


### Kullanım Adımları

1.Hedef branch’e geçilir
(Commit nereye gidecekse orada olmalısın)

git checkout master

2.Alınmak istenen commit ID bulunur

git log

3.Cherry-pick işlemi yapılır

git cherry-pick a12345
Sadece o commit master branch’ine eklenmiş olur.


Conflict Çıkarsa Ne Yapılır?

Cherry-pick sırasında conflict oluşabilir. Bu durumda:

1.Conflict’leri elle düzelt

2.Dosyaları stage’e al

--> git add .

3.Cherry-pick işlemine devam et

git cherry-pick --continue


Bu süreç rebase mantığına benzer.
Conflict sonrası direkt git commit atılmaz, --continue kullanılır.


Cherry-pick commit’in gideceği branch’ten çalıştırılır

Yani:

dev → master commit taşıyacaksan

Önce master branch’ine geçilir, sonra cherry-pick yapılır

git checkout master
git cherry-pick <commit-id>


!!! Önemli Bilgi

Hatasız ve düzgün çalışan 20 commit’i olan bir branch’ten

Sadece 1 commit bile cherry-pick ile alınabilir

Branch’in tamamını taşımak zorunda değilsin



