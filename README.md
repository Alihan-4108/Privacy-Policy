# Privacy Policy Site (GitHub Pages + Unity)

Oyun: **Balloon Pop Puzzle: Clear Path** — Turul Games

Tek kaynak dosya: **`privacy.json`**. Hem web sayfasi (`index.html`) hem de Unity oyunu
bu dosyadan metni okur. Sadece `privacy.json` dosyasini duzenlemen yeterli.

## Dosyalar

| Dosya | Amac |
|---|---|
| `privacy.json` | Politika metninin tek kaynagi (meta + bolumler) |
| `index.html` | `privacy.json`'u okuyup insanlar icin sik bir sayfa olusturur |
| `unity/PrivacyPolicyLoader.cs` | Unity'de `privacy.json`'u indirip metne yazan script |

## GitHub Pages'e Yukleme

1. GitHub'da yeni bir repo ac. Onerilen ad: **`privacy-policy`**
   (baska ad verirsen asagidaki tum URL'lerde `privacy-policy` yerine onu yaz).
2. `privacy.json` ve `index.html` dosyalarini reponun kokune yukle.
3. Repo > **Settings > Pages** > Source: `Deploy from a branch`
   > Branch: `main` / `root` > **Save**.
4. Birkac dakika sonra yayinlanir:
   - Sayfa: `https://alihan-4108.github.io/privacy-policy/`
   - Ham JSON: `https://alihan-4108.github.io/privacy-policy/privacy.json`
5. Google Play Console > **App content > Privacy policy** alanina
   `https://alihan-4108.github.io/privacy-policy/` adresini gir.

## Unity Entegrasyonu

1. `PrivacyPolicyLoader.cs` dosyasini projenin `Assets/` klasorune kopyala.
2. Gizlilik ekranindaki bir GameObject'e script'i ekle.
3. Inspector'da:
   - `Json Url` zaten `https://alihan-4108.github.io/privacy-policy/privacy.json` olarak ayarli.
   - `Target Text` = metni gosterecek UI Text alani.
4. TextMeshPro kullaniyorsan script'in en altindaki nota bak (2 satir degisiklik).

Not: `https` kullandigimiz icin Android'de ek ag ayari (cleartext) gerekmez.

## privacy.json Alanlari

- `meta.appName`, `meta.company`, `meta.contactEmail`
- `meta.effectiveDate`, `meta.lastUpdated` — tarihler (YYYY-AA-GG)
- `meta.version` — politika surumu (metni her degistirdiginde artir)
- `intro` — giris paragrafi
- `sections[]` — `{ "heading": "...", "body": "..." }`.
  `body` icinde `\n` satir sonu olarak calisir.

## IAP eklediginde

Uygulama ici satin alma eklersen:
1. `privacy.json` icinde yeni bir bolum ekle (odeme bilgisinin Google Play tarafindan
   islendigini, sizin kart bilgisi saklamadiginizi belirt).
2. `meta.version` ve `meta.lastUpdated` degerlerini guncelle.
3. Play Console'daki **Data safety** formunu guncelle.

Sablondaki metin genel bir taslaktir; yayinlamadan once kontrol et,
mumkunse bir hukukcuya danis.
