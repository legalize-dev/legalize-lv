# Legalize LV

### Latvijas tiesību akti Markdown formātā, versionēti ar Git.

Katrs tiesību akts ir fails. Katra reforma ir commit'a.

**~48 000 konsolidētu tiesību aktu** · Atvērti dati no [likumi.lv](https://likumi.lv)

Projekta [Legalize](https://github.com/legalize-dev/legalize) sastāvdaļa · [legalize.dev](https://legalize.dev)

> **Agrīnā stadijā** — Šis repozitorijs tiek aktīvi izstrādāts. Failu struktūra, commit'u vēsture un saturs var tikt būtiski mainīti, ieskaitot pilnu pārģenerēšanu.

## Ātrais sākums

```bash
# Klonēt Latvijas tiesību aktus
git clone https://github.com/legalize-dev/legalize-lv.git

# Latvijas Republikas Satversmes 1. pants
grep -A 3 "1\\. pants" lv/57980.md

# Konkrēta tiesību akta vēsture
git log --oneline -- lv/225418.md
```

## Struktūra

```
lv/
  57980.md     — Latvijas Republikas Satversme
  225418.md    — Civillikums
  88966.md     — Krimināllikums
  ...          — ~48 000 konsolidētu tiesību aktu
```

Tiesību akta veids (satversme, likums, noteikumi, rīkojums, …) ir norādīts YAML galvenē katrā failā, nevis katalogu struktūrā.

## Formāts

Katram failam ir:

- **YAML frontmatter** — metadati: nosaukums, identifikators, datums, statuss, veids, izdevējs, avots
- **Markdown teksts** — konsolidētais tiesību akta teksts ar nodaļu un pantu struktūru
- **Tabulas** — saglabātas kā Markdown caurules tabulas, kad iespējams

Commit'i izmanto vēsturisko katra grozījuma publicēšanas datumu. Katrā commit'ā ir trailer'i ar tiesību akta un grozījuma identifikatoriem, kas ļauj rekonstruēt pilnu tiesību aktu vēsturi ar `git log`.

### Aptvērums

Tiek apstrādāti tikai konsolidētie tiesību akti (nevis to grozījumi). Grozījumi jau ir iekļauti konsolidētajā versijā. Vēsturiskās redakcijas (`/redakcijas-datums/`) pēc likumi.lv robots.txt nav pieejamas.

## Avots

Visi dati ir iegūti no [likumi.lv](https://likumi.lv) — Latvijas oficiālā tiesību aktu portāla, ko pārvalda VSIA Latvijas Vēstnesis.

Atjauninājumus pārvalda [Legalize Pipeline](https://github.com/legalize-dev/legalize-pipeline) — Python rīks, kas pārveido oficiālos tiesību aktus par Markdown ar Git vēsturi.

## Licence

Šī repozitorija pārveidotie tiesību akti ir iekļauti zem [MIT licences](LICENSE).

Oriģinālie tiesību akti ir publiski pieejami caur likumi.lv saskaņā ar Latvijas likumu.
