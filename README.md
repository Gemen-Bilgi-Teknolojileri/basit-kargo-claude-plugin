# Basit Kargo — Claude Plugin

Tüm kargo firmaları tek yerde: oluştur, takip et, yönet.

[Basit Kargo](https://basitkargo.com), e-ticaret satıcıları için Aras, MNG, Yurtiçi, Sürat, PTT, HepsiJet ve diğer kargo firmalarını tek hesapta toplayan bir kargo platformudur. Bu eklenti Basit Kargo MCP sunucusunu ve kullanım becerisini Claude Code ve Cowork'e ekler.

## Neler yapabilirsiniz

- Gönderileri tüm hareket geçmişiyle takip etme
- Taslak sipariş oluşturma ve canlı kargo fiyatlarını karşılaştırma
- Onayınızla kargo kodu üretme (taslaklar ücretsiz; ücretlendirme ayrı ve onaylı bir adım, sunucu tarafında çift ödeme koruması)
- Etiketleri görüntü olarak alma veya masaüstü yazıcıdan basma

## Kurulum

```
/plugin install basit-kargo
```

İlk kullanımda Basit Kargo hesabınızla OAuth üzerinden giriş yapmanız istenir.

## Bileşenler

- **MCP sunucusu:** `https://mcp.basitkargo.com/mcp` (OAuth)
- **Skill:** `basit-kargo` — kargo iş akışları ve güvenli kullanım kuralları

## Destek

- Dokümantasyon: https://basitkargo.com/mcp
- E-posta: info@basitkargo.com

## Lisans

MIT
