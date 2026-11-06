# Taktik

Animasyonlu pozisyon eğitimi. Tek dosya (index.html), GitHub Pages ile yayınlanır. Diller: TR / DE / EN / FR.

- **Dersler:** Her ders önce sık yapılan hatayı (Yanlış), sonra doğrusunu (Doğru) adım adım oynatır. Pozisyona göre filtrelenir.
- **Dizilişler:** 4-1-4-1, 4-2-3-1, 4-4-2, 4-3-3, 3-5-2 için savunma bloğu ve hücum şekli; oyuncuya dokununca görevi.

## Yeni ders eklemek
`LESSONS` dizisine bir nesne ekle. Saha birimleri: x 0–68 (genişlik), y 0–105, bizim kale y=105.
- `actors`: `[id, 'us'|'op', x, y]`
- `intro`, `good[]`, `bad[]`: adımlar. Her adım: `p` (yeni konumlar), `ball` (oyuncu id veya [x,y]), `arrows` (`[x1,y1,x2,y2,'run'|'pass'|'press'|'guide']`), `zone` (`[x,y,r,'good'|'bad']`), `line` (`[y,'good'|'bad']`), `txt` (4 dil).

**Sen karar ver:** seçili filtreden 8 pozisyon. Her biri donar, iki hareket (A/B) ipucusuz izlenir, oyuncu doğruyu seçer, sonra doğrusu anlatımla oynar. Sonuç `postMessage` ile gönderilir: `{source:'ttsc-games', game:'taktik-karar', score, questions, accuracy, lessons}`.

Doğrudan bir derse link: `#ders-markaj`, dizilişler: `#dizilis`.
