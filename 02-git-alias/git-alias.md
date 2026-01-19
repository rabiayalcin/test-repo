# Git Alias

Git alias, sık kullandığımız Git komutlarına kısa isimler vermemizi sağlar.

---

1-Alias Tanımlama

Örnek:  
`git status` yerine `git st` kullanmak için:

```bash
git config --global alias.st status


2-Tanımlı Alias'ları Görüntüleme

git config --global --get-regexp alias


3-Alias Silme
Yanlış tanımlanmış bir alias’ı silmek için:

git config --global --unset alias.df


4-Birden Fazla Komutu Tek Alias’a Bağlama
Birden fazla komutu tek alias’ta kullanmak için ! işareti kullanılır.

git config --global alias.ac '!git add -A && git commit'
git ac -m "commit mesajı"


Alias ≠ Git komutu
git st
👉 Bu Git’in komutu değil
👉 Senin tanımladığın bir kısayol
Başka bilgisayarda çalışmaz.


git add . ve git add -A Farkı

 git add .
- Bulunduğun klasör ve **bu klasörün içindeki (alt klasörler dahil)** dosyaları stage alanına ekler.
- bir üst klasördeki değişiklikleri **almaz**.

📌 Yani:
> “Şu an olduğum klasörden aşağıya bak”

---
 git add -A
- Projedeki **tüm değişiklikleri** stage alanına ekler.
- Dosya ekleme, silme ve güncelleme fark etmez.
- Hangi klasörde olduğun önemli değildir.

📌 Yani:
> “Projede ne değiştiyse hepsini ekle”


