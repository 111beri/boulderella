# Boulder Ella – Přehled změn dle zadání

## Struktura souborů
```
boulder-ella/
├── index.html          ← hlavní strana
├── o-nas.html          ← O boulderingu
├── trenink.html        ← Trénink
├── galerie.html        ← Fotogalerie
├── vybaveni.html       ← Vybavení
├── kontakt.html        ← Kontakt
├── robots.txt          ← pro Google Search Console
├── sitemap.xml         ← mapa stránek
├── css/
│   ├── bootstrap.min.css   ← 1. CSS soubor (framework)
│   └── custom.css          ← 2. CSS soubor (vlastní styly)
├── js/
│   ├── bootstrap.bundle.min.js  ← 1. JS soubor
│   └── (jQuery + DataTables načítány z CDN)  ← 2. JS soubor
└── img/
    └── boulder1.jpg … boulder22.jpg
```

## Co bylo přidáno / opraveno

### SEO – meta tagy (každý soubor)
- `<meta name="description">` – unikátní popis stránky
- `<meta name="keywords">` – klíčová slova pro danou podstránku
- `<meta name="author">`
- `<meta name="robots" content="index, follow">`
- `<meta property="og:*">` – Open Graph (index.html)
- Unikátní `<title>` s klíčovým slovem + názvem webu

### Nadpisy H1 / H2 / H3
- Každá strana má právě **jeden H1** odpovídající obsahu stránky
- Podnadpisy H2 a H3 strukturují obsah (galerie, vybavení, kontakt, trénink...)
- Carousel captions přepsány na `<h2>` místo `<h5>` (správná hierarchie)

### Lazy loading obrázků
- Přidáno `loading="lazy"` na všechny obrázky pod fold
- První obrázky v carouselu a galerii bez lazy (rychlejší FCP)
- Přidány atributy `width` a `height` pro předcházení CLS

### 2 CSS soubory
1. `css/bootstrap.min.css` – Bootstrap framework
2. `css/custom.css` – vlastní styly (přesunuté z `<style>` tagů)

### 2 JS soubory
1. `js/bootstrap.bundle.min.js` – Bootstrap JS
2. jQuery + DataTables (CDN) – použito na trenink.html

### Rozšířená patička (footer)
Každá strana má patičku se třemi sloupci:
- Popis webu
- Rychlé odkazy na všechny podstránky
- Kontaktní informace (adresa, telefon, email, sociální sítě)

### Vnitřní propojení stránek (v textu)
Každá strana obsahuje přirozené textové odkazy na ostatní stránky:
- index.html → o-nas.html, galerie.html, trenink.html, vybaveni.html, kontakt.html
- o-nas.html → trenink.html, vybaveni.html, kontakt.html
- trenink.html → o-nas.html, galerie.html, vybaveni.html
- vybaveni.html → o-nas.html, trenink.html, kontakt.html
- kontakt.html → vybaveni.html, trenink.html

### Rozšířený obsah stránek (copywriting + klíčová slova)
- **index.html**: přidána intro sekce s feature kartami a info blokem
- **o-nas.html**: každý tab rozšířen o SEO text
- **trenink.html**: přidána sekce se stupnicí obtížností (barevné karty)
- **vybaveni.html**: přepracována na kartový přehled 6 kategorií vybavení
- **kontakt.html**: přidána tabulka otevírací doby + sekce parkování

### robots.txt + sitemap.xml
- `robots.txt` umožňuje indexaci všech stránek
- `sitemap.xml` ve formátu sitemaps.org s prioritami

### Další
- `aria-label`, `aria-current`, `aria-controls` – přístupnost
- Navbar toggler má správné `aria-*` atributy
- Správné `lang="cs"` na všech stranách
- Footer obsahuje note o studentském projektu na každé straně

## Doporučení pro nasazení
1. Nahrajte celou složku na webhosting
2. Aktualizujte URL v sitemap.xml na skutečnou doménu
3. Propojte s Google Search Console (ověření přes HTML tag nebo soubor)
4. Propojte s Google Analytics (přidejte GA4 script před </head>)
5. Pro minifikaci HTML použijte nástroj jako HTMLMinifier
6. Pro caching nastavte .htaccess nebo Netlify headers
