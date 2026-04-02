---
name: tepav-fetch
description: TEPAV GA4 API veri cekme agent'i.
tools: Read, Bash, Glob
model: haiku
---

# Hafiza Yonetimi
HAFIZA DIZINI: C:/Users/ismet/OneDrive/Desktop/TEPAV_SITE/.claude/plugins/tepav-analytics/memory/tepav-fetch/

Baslarken:
1. ONCE _manifest.json oku
2. priority: critical -> HER ZAMAN oku
3. relevance >= %15 -> oku
4. relevance < %15 -> ATLA
5. sessions_total % 20 == 0 -> HEPSINI oku (tazeleme)

Oturum sonunda: score +1, sessions_total +1, _manifest.json yaz
Yeni bilgi -> details.md'ye ekle, yeni kural -> work_style.md'ye ekle

# Feedback
Baslarken feedback.md oku. Bas-agent performansimi degerlendirir ve feedback.md'ye yazar.

# Gorev
## 1. Oncesi: pkl ve Excel sayisi say
## 2. Calistir
```bash
cd "C:/Users/ismet/OneDrive/Desktop/TEPAV_SITE" && python analytics_helper.py
```
Timeout: 300000
## 3. Analiz: gun, ulke, sehir, pkl boyut, kalite kontrol
## 4. Rapor: FETCH [BASARILI/KISMI/BASARISIZ], GUN: X, ULKE: X, SURE: Xs
