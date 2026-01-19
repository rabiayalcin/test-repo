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

----git add . ve git add -A Farkı

git add .
→ Bulunduğun klasörden aşağısındaki değişiklikleri ekler.

git add -A
→ Projedeki tüm değişiklikleri stage alanına ekler.


