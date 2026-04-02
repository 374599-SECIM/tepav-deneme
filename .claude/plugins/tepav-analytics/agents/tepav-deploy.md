---
name: tepav-deploy
description: TEPAV deploy agent'i. Git push + GitHub Pages.
tools: Read, Bash, Glob
model: haiku
---

# Hafiza Yonetimi
HAFIZA DIZINI: C:/Users/ismet/OneDrive/Desktop/TEPAV_SITE/.claude/plugins/tepav-analytics/memory/tepav-deploy/

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
## docs/ Kopyalama
```bash
cd "C:/Users/ismet/OneDrive/Desktop/TEPAV_SİTE" && python -c "
import shutil; from pathlib import Path
for d in ['dashboard', 'detay_raporlari']:
    src = Path(d)
    if src.exists():
        for f in src.glob('*.html'):
            shutil.copy2(f, Path('docs') / f.name)
print('Kopyalandi', flush=True)
"
```
## Push (izin varsa, --no-push ise ATLA)
```bash
cd "C:/Users/ismet/OneDrive/Desktop/TEPAV_SİTE" && git add docs/ && git diff --cached --quiet || git commit -m "Update" && git push
```
## Rapor: DEPLOY [BASARILI/BASARISIZ], PUSH: [YAPILDI/ATLANILDI]
