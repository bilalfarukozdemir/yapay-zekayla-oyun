# Animasyonu nasıl yapıyorum?

## Kısa cevap

Karakter animasyonlarını Claude'a kodla çizdiriyorum; bunun için kendi açık kaynak piksel çizim motorum [pixel-art-engine](https://github.com/bilalfarukozdemir/pixel-art-engine)'i kullanıyorum. Kol, bacak, asa ve pelerin için pozlar tanımlatıp her kareyi bu pozlardan üretiyorum. Kareleri PNG olarak dışarı alıp Phaser'da oynatıyorum. Şu an Korel'in bekleme, koşu, saldırı ve Uğurla animasyonları var; oyunda henüz düşman, can ve ölüm yok.

## Karakter kareleri nasıl üretiliyor?

Korel'i TypeScript ile, motorun `Painter` aracı üzerinden çizdiriyorum. Kodda kol ve bacak açılarını, gövdenin eğilmesini, asanın yönünü, pelerinin savrulmasını ve fenerin sallanmasını tanımlıyorum. Çizim bu değerlere göre her karede yeniden hesaplanıyor. Kareler arasında çizim titremesin diye gürültü tohumlarını sabit tutuyorum.

İlk denemede karakter yaklaşık 36 piksel boyundaydı. Sonra 64 piksele çıkardım ve kıyafet olarak Maskeli Yasçı'yı seçtim. Mevcut karakterin kare tuvali 140×100 piksel; karakter boyuyla kare tuvalinin ölçüsü aynı şey değil.

Şu an toplam 32 kare üretiyorum:

| Hareket | Kare sayısı | Üretimde kaydettiğim kare süreleri |
| --- | ---: | --- |
| Bekleme (`idle`) | 6 | Her kare 150 ms |
| Koşu (`run`) | 8 | Her kare 80 ms |
| Saldırı (`attack`) | 6 | Sırayla 120, 50, 50, 140, 80, 120 ms |
| Uğurla (`ugurla`) | 12 | İlk 3 kare 90 ms, kalanlar 110 ms |

Saldırıda asanın savrulma izini ve temas kıvılcımını da kodla çizdiriyorum. Uğurla'da Korel diz çöküyor, asasını dik tutuyor; yerde bir halka açılıyor ve önünde soluk bir ruh yükseliyor. Bu, şu an oynatabildiğim bir animasyon; henüz oyundaki bir düşmanı uğurlamıyorum.

Her hareketin karelerini yan yana tek bir PNG'de topluyorum; buna sprite sheet deniyor. Kare ölçülerini, ayakların sabitlendiği noktayı ve süreleri JSON'a yazdırıyorum. Çizim betiği ayrıca tek tek kare PNG'leri ve `.aseprite` dosyası da üretiyor.

Codex'e görsel olarak ürettirdiğim parçalar tanrı başı, dev kılıç ve kapı gibi büyük sahne parçaları. Korel'in bu animasyon karelerini koddan üretiyorum.

## Oyunda nasıl oynatılıyor?

Oyunda Phaser kullanıyorum. Her hareketin PNG dosyasını 140×100 piksellik karelere böldürüp JSON'daki süreleri animasyonun karelerine `duration` değeri olarak veriyorum. Oynatma kodunda ayrıca sabit bir `frameRate` belirtmiyorum; yukarıdaki değerler üretim dosyasına kaydettiğim süreler.

Bekleme ve koşuyu sürekli döndürüyorum. Hareket ederken koşuya, durunca beklemeye geçiyorum; sola dönerken aynı çizimi yatay çeviriyorum. Saldırı ve Uğurla'yı bir kez oynatıyorum. Bu ikisi sürerken hareketi ve yeni bir saldırı ya da Uğurla başlatmayı kilitliyorum; animasyon bitince kilidi kaldırıp beklemeye dönüyorum.

## Yapay zekânın zorlandığı yerler

İlk denemede koşu ve saldırı okunuyordu ama karakter düz ve koyu kalmıştı. Pelerindeki kıvrımlar ve tonlar eksikti, el ve ayaklar belirsizdi. Teknik olarak hareket etmesi, istediğim görünüme ulaştığı anlamına gelmedi.

64 piksellik denemede koşarken pelerin bacakları örtüyordu; karakter kayıyormuş gibi görünüyordu. Saldırıda fener tuvalden taşıyor, Uğurla'da asa yüzden geçiyordu. Bunları düzelttirdim. Maskeli Yasçı kıyafetine geçince de kanca ters kıvrılıp feneri yüze düşürdü, bacaklar kısa kaldı; o çizimi de yeniden düzelttirdim.

## Sırada ne var?

İlk düşman için Zincirli Keşiş ve Paslı Zırhlı Asker görünüm adaylarını çizdirdim; henüz oyunda değiller. Oylamada kazananı önce cilalayıp Gün 2'de yapmayı planlıyorum. Kazanan için bekleme, yürüme, saldırı, sendeleme ve Uğurla ile geçirilme animasyonları sırada.
