# turkce-humanizer (Global Rule Sürümü)

[bushrabeg/turkce-humanizer](https://github.com/bushrabeg/turkce-humanizer) projesinin, yapay zekâ asistanlarında (Antigravity, Claude Code, Cursor, Windsurf vb.) **her mesajda aktif kalan Global Rule (`GEMINI.md` / `CLAUDE.md` / `AGENTS.md`)** olarak kullanılmak üzere sadeleştirilmiş ve yeniden kurgulanmış versiyonudur.

## Orijinal Skill Sürümünden Farkları

1. **Zorunlu Onay ve Profil Soruları Kaldırıldı:** Model işlem öncesinde *"Bu metni X register'ı olarak görüyorum, onaylıyor musun?"* veya *"Kendi yazdığın 2-3 örnek metin paylaş"* diye soru sormaz; register tespitini arka planda sessizce yapar.
2. **5 Bölümlü Rapor Formatı Kaldırıldı:** Çıktı sonuna *Tespit Raporu, Sinyal Yoğunluğu, Değişiklik Özeti, Notlar* basılmaz; model doğrudan kurallara uygun yanıtı üretir.
3. **"Metni Düzelt" Dili "Yanıtı Üret" Diline Çevrildi:** Kurallar yalnızca verilen bir metni yeniden yazmak (rewrite) için değil, modelin kendi ürettiği tüm Türkçe yanıtları doğal kurması için doğrudan üretim yönergesi biçiminde yazıldı.
4. **Düşük Token Maliyeti ve Sıfır Dış Dosya Referansı:** Sürüm notları, uzun belge protokolleri ve `docs/` veya `examples/` klasörlerine giden dosya referansları temizlendi; sistem bağlamında minimum token harcayacak tek bir çekirdek blok bırakıldı.
5. **Teknik Terim, Kod ve Noktalama Esnekliği Eklendi:**
   - Kod bloklarına, loglara, LaTeX formüllerine ve yerleşik İngilizce yazılım terimlerine (`cache'i`, `endpoint'e`, `token'ları` vb.) dokunmama kuralı eklendi.
   - Noktalı virgül (`;`) ve iki nokta (`X: Y`) kuralları mutlak yasak yerine **seyrek ve işlevsel kullanım** (madde başı tanımlar, teknik listeler ve virgüllü grupları ayırma) olarak güncellendi.

## Kullanım

`SKILL.md` (veya birebir aynı içeriğe sahip `RULE.md`) dosyasının içeriğini kullandığınız aracın global kural dosyasına (`~/.gemini/GEMINI.md`, `~/.claude/CLAUDE.md`, `AGENTS.md` vb.) yapıştırmanız yeterlidir.

## Lisans ve Kaynak

MIT — Orijinal çalışma: **Büşra Begçecanlı** ([@bushrabeg/turkce-humanizer](https://github.com/bushrabeg/turkce-humanizer)).
