Git remove
git rm test.txt  
Bu komut dosyayı siler. Silinen dosya otomatik olarak stage area’ya alınır.  
`git status` dediğinde dosyayı yeşil (staged) olarak görürsün ve direkt commit atabilirsin.  
Örnek commit mesajı:  
git commit -m "deneme4 dosyası silindi"

Klasörden silmek ile git rm arasındaki fark şudur:  
Klasörden silmek dosyayı sadece bilgisayardan siler. Git bu silmeyi commit’e dahil etmez, ayrıca `git add .` yapmak gerekir.  
`git rm` ise dosyayı hem bilgisayardan siler hem de Git’e bu silmenin commit edileceğini tek adımda bildirir.

git rm -r klasor.adi/  
Bu komut verilen klasörü ve içindeki tüm dosyaları siler.  
Silinen her şey otomatik olarak stage area’ya eklenmiş olur.

Git move 
git mv, dosya veya klasör taşımak ve isim değiştirmek için kullanılır.

git mv dosya.adi yeni.ad  
Dosyanın ismini değiştirir.  
`git status` çıktısında renamed olarak görünür.  
Ardından `git add .` ve commit atılır.

git mv dosya.adi klasor.adi/  
Dosyayı belirtilen klasöre taşır.  
`git status` ile kontrol edilir, sonra add ve commit yapılır.

Aynı anda hem dosyayı taşımak hem de ismini değiştirmek için iki adım yapmak gerekmez.  
Uzun yol:  
git mv dosya.adi ikinci.ad  
git mv ikinci.ad klasor.adi/

Kısa yol (önerilen):  
git mv dosya.adi klasor.adi/yeni.ad  
Bu şekilde dosya hem klasöre taşınır hem de ismi değişir.  
Sonrasında `git add .` ve commit atılır.

git mv eski.klasor/ yeni.klasor/  
Klasörü içindekilerle birlikte yeni klasöre taşır.

git mv eski.klasor/* yeni.klasor/  
Eski klasörün içini yeni klasöre taşır, eski klasör boş kalır.
