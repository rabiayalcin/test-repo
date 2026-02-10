# HOTFIX BRANCH 

Hotfix, master (ya da main) branch’inden açılan ve canlı ortamda (production) çıkan acil hataları düzeltmek için kullanılan bir branch’tir.
Önceliği hızdır; planlı geliştirmeleri beklemez.

``` bash 

## Temel özellikler

Sadece kritik ve acil bug fix içerir

Yeni özellik eklenmez

Kısa ömürlüdür (iş biter bitmez kapatılır)

## Akış

Hotfix branch’i master’dan açılır

Hata düzeltilir

Hotfix önce master’a merge edilir (canlıya çıkar)

Ardından yapılan fix’in kaybolmaması için dev’e de aktarılması gerekir


Hotfix Sonrası Master → Dev Aktarımı

Hotfix’i master’a merge ettikten sonra dev’e nasıl geçileceği, master’daki duruma göre değişir:

✅ Master’da sadece hotfix commit’i varsa
→ master → dev merge etmek daha mantıklıdır

✅ Master’da hotfix dışında başka commit’ler de varsa
→ Sadece hotfix commit’ini cherry-pick etmek gerekir
(Böylece istenmeyen değişiklikler dev’e taşınmaz)


Özet

Hotfix = canlıyı kurtarma branch’i

Mutlaka master + dev ile senkronlanmalıdır

Aktarım yöntemi, master’ın içeriğine göre seçilir



