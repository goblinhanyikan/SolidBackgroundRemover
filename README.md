This tool allows you to remove backgrounds from solid backgrounds (like a brand logo behind a white background)
https://goblinhanyikan.github.io/SolidBackgroundRemover/

# Offline Background Remover

A single-file, offline HTML tool for removing solid backgrounds from logos and objects, and exporting the result as a transparent PNG. No internet connection, server, or AI model required — everything runs locally in your browser.

## How to use

1. Open `bg-remover.html` in any modern browser (Chrome, Firefox, Edge, Safari).
2. Drop an image or click to select one.
3. The background color is auto-detected from the image corners. Click anywhere on the background in the original preview to pick a different color if needed.
4. Adjust the sliders (see below) until the result looks clean.
5. Click **Download PNG** to save the transparent cutout.

## Controls

- **Match tolerance** — how close a pixel's color must be to the picked background color to be flood-filled away. The removal starts from the image edges and spreads inward, so it won't touch similar colors that are enclosed inside the object.
- **Edge cleanup (px)** — width of the band around the removed background where edge pixels get "decontaminated": any blended background tint is mathematically removed instead of just faded, which prevents a light halo/fringe around the object.
- **Fill enclosed holes** — automatically removes background-colored regions that are fully enclosed by the object (e.g. the inside of an "O" or "A"), even though they're not connected to the image border. Capped by size so it won't eat large same-colored parts of the logo.
- **Purity strip** — an aggressive, image-wide pass (not limited to connected regions) that fades and decontaminates *any* pixel close to the picked color, useful for scattered bleed, dust, or faint tint left after the main removal. Pushed high enough, it can start eating into the logo itself — use the live preview to judge.
- **Reset pick** — restores the auto-detected background color.

## Notes

- Works best on flat/solid backgrounds (logos, product shots on white, etc.). Complex or textured backgrounds are not supported — that would require an AI segmentation model, which this tool intentionally avoids to remain fully offline and lightweight.
- All processing happens in-browser; no image data is ever uploaded anywhere.

---

# Çevrimdışı Arka Plan Kaldırma Aracı

Logo ve nesnelerden düz (tek renk) arka planları kaldırıp sonucu şeffaf bir PNG olarak indirmenizi sağlayan, tek dosyalık ve tamamen çevrimdışı çalışan bir HTML aracı. İnternet bağlantısı, sunucu veya yapay zeka modeline ihtiyaç yoktur — her şey tarayıcınızda yerel olarak çalışır.

## Kullanım

1. `bg-remover.html` dosyasını güncel bir tarayıcıda açın (Chrome, Firefox, Edge, Safari).
2. Bir görsel sürükleyip bırakın veya tıklayarak seçin.
3. Arka plan rengi görselin köşelerinden otomatik olarak algılanır. Gerekirse orijinal önizlemede arka plan üzerinde herhangi bir noktaya tıklayarak farklı bir renk seçebilirsiniz.
4. Sonuç temiz görünene kadar kaydırıcıları (aşağıda açıklanmıştır) ayarlayın.
5. Şeffaf kesimi kaydetmek için **Download PNG** (PNG İndir) butonuna tıklayın.

## Kontroller

- **Match tolerance (Eşleşme toleransı)** — bir pikselin, seçilen arka plan rengine ne kadar yakın olması gerektiğini belirler; bu değere göre "flood fill" (yayılmalı doldurma) yöntemiyle kaldırılır. Kaldırma işlemi görselin kenarlarından başlayıp içe doğru yayılır, bu sayede nesnenin içinde kalan benzer renkli alanlara dokunulmaz.
- **Edge cleanup (px) (Kenar temizliği)** — kaldırılan arka planın etrafındaki kenar bandının genişliğini belirler; bu banttaki pikseller sadece soldurulmaz, üzerlerine bulaşmış arka plan rengi matematiksel olarak ayrıştırılıp temizlenir. Bu, nesnenin etrafında açık renkli bir hale/leke oluşmasını önler.
- **Fill enclosed holes (Kapalı boşlukları doldur)** — nesnenin içinde tamamen çevrelenmiş, arka plan renginde kalan bölgeleri (örneğin "O" veya "A" harfinin içi) otomatik olarak kaldırır; bu bölgeler görsel kenarına bağlı olmasa bile. Logoya ait büyük, aynı renkteki alanları yanlışlıkla silmemesi için boyut sınırlaması vardır.
- **Purity strip (Saflık ayıklama)** — bağlantılı bölgelerle sınırlı olmayan, görselin tamamında agresif bir şekilde çalışan bir geçiştir; seçilen renge yakın olan *herhangi bir* pikseli soldurup temizler. Ana kaldırma işleminden sonra kalan dağınık lekeler, toz veya hafif renk sızıntıları için kullanışlıdır. Değer çok yükseltilirse logonun kendisini de aşındırmaya başlayabilir — canlı önizlemeyi takip ederek ayarlayın.
- **Reset pick (Seçimi sıfırla)** — otomatik algılanan arka plan rengine geri döner.

## Notlar

- En iyi sonucu düz/tek renkli arka planlarda verir (logolar, beyaz zemin üzerindeki ürün fotoğrafları vb.). Karmaşık veya dokulu arka planlar desteklenmez — bu, yapay zeka tabanlı bir segmentasyon modeli gerektirir ve aracın tamamen çevrimdışı ve hafif kalması için bilinçli olarak bu yöntemden kaçınılmıştır.
- Tüm işlemler tarayıcı içinde gerçekleşir; hiçbir görsel veri herhangi bir yere yüklenmez.
