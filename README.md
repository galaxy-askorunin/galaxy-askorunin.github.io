# Galaxy Áskorunin — frumgerð vef-apps

Gagnvirkt vef-app fyrir herferð Tæknivara og Samsung: fjórir þættir, fjórar „touch“ áskoranir, stigatafla, vinningar og úrslit í Smáralind 19. desember.

> **Frumgerð til prófana.** Ekki fara í loftið með þessa útgáfu. Sjá „Takmarkanir“ hér fyrir neðan.

## Innihald

| Skrá | Hvað |
| :--- | :--- |
| `index.html` | Allt appið í einni skrá (HTML, CSS og JavaScript). Engin uppsetning eða „build“ skref. |
| `PROFANIR.md` | Prófunarlisti fyrir prófara. |
| `robots.txt` | Bannar leitarvélum að skrá síðuna. |
| `.nojekyll` | Segir GitHub Pages að birta skrárnar óbreyttar. |

## Setja á GitHub Pages

1. Búðu til nýtt repository á GitHub, t.d. `galaxy-askorunin`.
2. Hladdu upp öllum skránum í þessari möppu (líka `.nojekyll`), annaðhvort með **Add file › Upload files** eða með git:
   ```bash
   git init
   git add .
   git commit -m "Frumgerð Galaxy Áskorunarinnar"
   git branch -M main
   git remote add origin https://github.com/<notandi-eða-fyrirtæki>/galaxy-askorunin.git
   git push -u origin main
   ```
3. Farðu í **Settings › Pages**, veldu **Deploy from a branch**, svo `main` og `/ (root)`, og smelltu á **Save**.
4. Eftir 1–2 mínútur er appið aðgengilegt á `https://<notandi-eða-fyrirtæki>.github.io/galaxy-askorunin/`.

**Athugið:** GitHub Pages síða er opin öllum sem hafa hlekkinn, jafnvel þótt repository-ið sé lokað (nema á GitHub Enterprise). Síðan er merkt þannig að leitarvélar skrá hana ekki, en ekki deila hlekknum opinberlega fyrr en Samsung hefur samþykkt efnið.

## Prófa á eigin tölvu

Opnaðu `index.html` beint í vafra, eða keyrðu einfaldan vefþjón í möppunni:

```bash
python3 -m http.server 8000
```

og opnaðu `http://localhost:8000`. Til að prófa í síma á sama neti: `http://<IP-tala-tölvunnar>:8000`.

## Kynningarstilling

- **Allir þættir eru opnir** svo hægt sé að prófa allt strax. Slökkva má á því undir **Ég › Kynningarstilling** til að sjá útgáfudagsetningar.
- **Núllstilla:** **Ég › Núllstilla kynningu** hreinsar stig og svör.
- **Verslunarkóðar:** `2701`–`2705`.
- **Faldir kóðar í þáttum:** `4821`, `3307`, `6159`, `7744` (þáttur 1–4).
- **Vinaboð:** bættu `?vinur=ABC12` aftan við slóðina til að prófa boð frá vini.
- **Útlit:** takkinn efst við hliðina á stigunum skiptir á milli ljóss og dökks útlits. Undir **Ég › Útlit** er líka hægt að velja „Sjálfvirkt“.

## Takmarkanir frumgerðarinnar

Þetta þarf að klára áður en appið fer í loftið:

- **Enginn bakendi.** Stig, skráningar og vinaboð eru aðeins geymd í vafra notandans (localStorage). Stigataflan og vinnustaðataflan eru kynningargögn.
- **Tímataka í símanum.** Tími og stig eru reiknuð í vafranum. Í raunútgáfu þarf netþjónn að mæla og staðfesta tíma svo ekki sé hægt að svindla.
- **Stigatafla:** bakendinn á aðeins að senda efstu 10 og eigið sæti notandans, aldrei heildarlistann.
- **Samsung-merkið** er staðgengill í hausnum. Opinbera SVG-skráin fer þar inn.
- **Myndefni** er teiknað. Skipta á út fyrir samþykktar vörumyndir og ramma úr þáttunum.
- **Myndbönd** eru sýnishorn. Lokaþættir með opinberu front/end plate koma í staðinn.
- **Leikreglur og persónuverndarstefna** eru drög.
- **Lén** `galaxyaskorunin.is` á Story-myndum er staðgengill.
- **Röð þátta** í tökulista og appi þarf að samræma.
