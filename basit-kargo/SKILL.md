---
name: basit-kargo
description: Basit Kargo ile kargo işlemleri — gönderi takibi, fiyat karşılaştırma, taslak sipariş, kargo kodu üretme ve etiket basma. Kullanıcı kargo, gönderi, takip, etiket, kargo fiyatı veya Basit Kargo bakiyesinden bahsettiğinde kullan.
---

# Basit Kargo

Basit Kargo; Aras, MNG, Yurtiçi, Sürat, PTT, HepsiJet ve diğer kargo firmalarını tek hesapta toplayan bir e-ticaret kargo platformudur. Bu eklenti `basit-kargo` MCP sunucusunu (https://mcp.basitkargo.com/mcp) kullanır.

## Başlarken

- İlk işlemden önce `auth_status` ile oturumu kontrol et. Oturum yoksa kullanıcıdan OAuth ile bağlanmasını iste.

## Sık iş akışları

**Gönderi takibi**
1. `track_shipment` ile takip numarası veya sipariş üzerinden hareket geçmişini getir.
2. Birden fazla gönderi için `list_shipments` kullan; durum adları için `status_labels`.

**Yeni gönderi**
1. Alıcı adresi yoksa `list_cities` / `get_districts` ile il-ilçe doğrula, `create_address` ile kaydet.
2. `create_shipment` ile taslak oluştur — taslaklar ücretsizdir.
3. `get_price_quote` ile firmaların canlı fiyatlarını karşılaştırıp kullanıcıya sun.
4. Kargo kodu üretmek (`generate_shipment_code`, `bulk_generate_codes`) bakiyeden ücret düşer: tutarı ve firmayı gösterip **kullanıcıdan açık onay almadan asla çalıştırma**.

**Etiket**
- `get_label` ile etiketi görüntü olarak getir; masaüstü yazıcıya göndermek için `list_printers` ardından `print_label`.

**Hesap**
- `get_balance`, `list_transactions`, `get_cod_status` (kapıda ödeme), `get_stats`.

## Kurallar

- Ücretli veya geri alınamaz işlemlerden (kod üretme, `cancel_shipment`, `delete_order`) önce özet göster ve onay iste.
- Fiyatları ve tutarları TL olarak, firmaya göre sıralı bir tabloyla sun.
