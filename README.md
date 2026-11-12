# Yapay Zekâyla Oyun Yapıyorum — Yöntem Defteri

Selam, ben Bilal. Yapay zekâ araçlarıyla 2D piksel aksiyon oyunumu geliştiriyorum. Bu serüveni YouTube ve TikTok üzerinde **"Yapay zekâyla oyun yapıyorum — Gün N"** devlog serisi olarak paylaşıyorum.

Bu depo, o serinin **yöntem defteri**. Burada oyunun kaynak kodu yok; her video için o gün neler yaptığımı, hangi teknikleri kullandığımı, nelerin işe yarayıp yapay zekânın nerede tıkandığını ve çıkardığım somut dersleri açıkça belgeliyorum.

- **Oyunu Dene:** [Tarayıcıda oyna](https://veyra-aksiyon.vercel.app)
- **Videolar:** [YouTube @bilaldevlog](https://youtube.com/@bilaldevlog) — TikTok, Instagram, X ve Threads'te de aynı ad: `bilaldevlog`
- **Tüm linkler:** [link.vitrincim.com](https://link.vitrincim.com)

---

## Rol Paylaşımı ve Şeffaflık

Bu serinin temeli tam yapay zekâ şeffaflığına dayanıyor:

- **Kararlar & Yönetmenlik (Bilal):** Sanat tarzı, oyun hissi, mekanikler, kamera açısı ve nelerin çöpe atılacağı benim kararım.
- **Kod (Claude):** Oyun mimarisi, matematiksel hesaplamalar, gölgelendirme algoritmaları, animasyon ve oynanış kodları Claude tarafından yazılıyor.
- **Görseller (Codex):** Büyük set parçaları ve atmosferik konsept çizimleri Codex tarafından üretiliyor.
- **Kodla piksel çizim:** Kodla çizilen parçalar (ızgara/palet dönüşümü, heykel başı denemeleri) kendi açık kaynak motorum [pixel-art-engine](https://github.com/bilalfarukozdemir/pixel-art-engine) ile yapılıyor.

Oyun, [yazı tabanlı oyunum Veyra: Kırık Ölüm](https://play.google.com/store/apps/details?id=com.ironcoreapps.veyra)'ün dünyasında geçiyor; bu ilk sahnede henüz hikâye yok.

---

## Bu Defter Nasıl Okunur?

Her devlog videosuna karşılık `gunler/` klasörü altında bir gün dosyası yer alır. Her gün dosyasında:

1. **Bugün Ne Yaptım:** Günün kısa ve net özeti.
2. **Kullanılan Araçlar ve Teknikler:** Hangi model ne için kullanıldı, hangi algoritmalardan yararlanıldı.
3. **Adım Adım:** Fikirden uygulamaya somut geliştirme aşamaları.
4. **Yapay Zekânın Beceremediği Anlar:** Modellerin çuvalladığı, komik veya yapay duran kısımlar ve bunlara bulduğumuz çözümler.
5. **Dersler:** Bir sonraki güne veya benzer projelere aktarılabilecek altın kurallar.
6. **İzleyiciye Sorulan Soru:** Videoda topluluğa yöneltilen oylamalar ve yön belirleme kararları.
7. **Görseller:** Adımları gösteren ham ve işlenmiş ekran görüntüleri.

---

## Günler

- [Gün 1: Fikirden İlk Oynanabilir Sahneye](gunler/gun-01.md) — Pinterest panosundan ilham alıp dev set parçaları, hibrit piksel tekniği ve ilk web sürümüne uzanan ilk gün.
- [Gün 2: İlk Düşman ve Uğurla](gunler/gun-02.md) — Zincirli Keşiş, karma yöntemle yenilenen karakterler ve dört vuruştan sonra başlayan üç saniyelik Uğurla penceresi.
- [Gün 3: Devrik Kervan ve İçi Boş Bedenler](gunler/gun-03.md) — Aynı Uğurla tuşunun iki sonucu, ilk turkuaz ışık ve tek veri dosyasından içerik ekleme.
- [Gün 4: Eşik Köyü ve Hanın Kapısı](gunler/gun-04.md) — Gözlü kapıdan ikinci haritaya; karakterlerin paleti, telefonda fark edilen ölçek ve oturma sorunları, başarısız esnetme denemesi ve denetçinin yakaladıkları.

## Teknikler

- [Animasyonu nasıl yapıyorum?](teknikler/animasyon.md)

---

## Lisans

Bu yöntem defterindeki metinler ve dökümantasyon [Creative Commons Attribution 4.0 International (CC BY 4.0)](LICENSE) ile lisanslanmıştır.
