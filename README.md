# Flipiak Szczypuła — strona wizytówkowa

Jednostronicowa strona pracowni informatycznej **Flipiak Szczypuła**.
Statyczny HTML / CSS / JS, bez frameworków i bez procesu buildu —
gotowy do hostowania na **GitHub Pages**.

---

## Struktura projektu

```
.
├── index.html       # cała struktura strony (semantyczny HTML, SEO, JSON-LD)
├── styles.css       # design system + responsywność (mobile-first)
├── script.js        # mobilne menu, scroll reveal, smooth scroll
├── favicon.svg      # ikona w pasku przeglądarki
├── og-image.svg     # podgląd dla social media (Open Graph)
├── robots.txt       # reguły dla wyszukiwarek
├── sitemap.xml      # mapa strony
└── .nojekyll        # wyłącza Jekyll na GitHub Pages
```

---

## Uruchomienie lokalne

Wystarczy otworzyć `index.html` w przeglądarce — strona nie wymaga serwera.

Jeśli chcesz mieć "live reload", możesz uruchomić dowolny prosty serwer HTTP,
np.:

```bash
# Python 3
python -m http.server 8080

# Node (npx, bez instalacji)
npx serve .
```

Następnie wejdź na `http://localhost:8080`.

---

## Publikacja na GitHub Pages

1. Utwórz publiczne repozytorium na GitHubie (np. `flipiak-szczypula.github.io`
   dla domeny użytkownika, albo dowolne inne — np. `strona`).
2. Wgraj zawartość tego folderu do gałęzi `main`.

   ```bash
   git init
   git add .
   git commit -m "init: brutalist one-pager"
   git branch -M main
   git remote add origin git@github.com:<user>/<repo>.git
   git push -u origin main
   ```

3. W repozytorium otwórz **Settings → Pages**:
   - **Source:** `Deploy from a branch`
   - **Branch:** `main` / folder `/ (root)`
4. Po kilkudziesięciu sekundach strona będzie dostępna pod adresem:
   - `https://<user>.github.io/<repo>/` — dla repo zwykłego,
   - `https://<user>.github.io/` — dla repo nazwanego `<user>.github.io`.

### Własna domena (opcjonalnie)

1. Dodaj plik `CNAME` w repo zawierający Twoją domenę, np.:
   ```
   flipiakszczypula.pl
   ```
2. W panelu DNS dostawcy domeny dodaj rekordy `A` lub `CNAME`
   wskazujące na GitHub Pages
   ([dokumentacja](https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site)).
3. W **Settings → Pages → Custom domain** wpisz domenę i włącz HTTPS.

---

## Co podmienić przed publikacją

W `index.html` zaktualizuj dane kontaktowe:

| Element | Lokalizacja | Co zmienić |
|---|---|---|
| E-mail | `mailto:kontakt@flipiakszczypula.pl` | Twój e-mail |
| Telefon | `tel:+48000000000` | Twój numer |
| GitHub | `@flipiak-szczypula` | Twój handle |
| Lokalizacja | `Polska · zdalnie / on-site` | Twoja lokalizacja |
| Domena w `og:image` / `canonical` | linki w `<head>` | Twoja docelowa domena |
| `sitemap.xml` | adres `loc` | Twoja docelowa domena |

---

## Design system w skrócie

- **Estetyka:** brutalist · futuristic · mono-grid.
- **Fonty:** Space Grotesk (display) + JetBrains Mono (mono).
- **Kolory:** off-white `#f1ede4`, czerń `#0a0a0a`, akcent `#d4ff3a`.
- **Ramki:** twarde 2–3 px, **brak zaokrągleń**, twarde cienie offsetowe.
- **Responsywność:** mobile-first, fluid clamp typography, breakpointy
  880 px / 680 px / 520 px.
- **Dostępność:** semantyczny HTML, skip-link, `focus-visible`,
  `prefers-reduced-motion`, kontrast ≥ AA.

Wszystkie tokeny designu trzymane są w `:root` w `styles.css` —
zmiana akcentu czy fontów to jedna linijka.

---

## Sekcje strony

1. **Ticker** — pasek informacyjny.
2. **Nav** — sticky, mobilne menu hamburger.
3. **Hero** — manifest + terminal panel.
4. **Manifest** — krótkie credo pracowni.
5. **Usługi IT** — aplikacje, AI, automatyzacje, gry.
6. **Grafika** — 3D, druk 3D, 2D.
7. **Proces** — 6 kroków współpracy.
8. **Stack technologiczny** — 6 kolumn kompetencji.
9. **FAQ** — 6 najczęstszych pytań.
10. **Kontakt** — dane + formularz `mailto`.
11. **Stopka** — nawigacja + meta.

---

## Future-proof

- Brak zależności zewnętrznych (poza Google Fonts) — strona przeżyje lata.
- Czyste, semantyczne klasy (BEM-like) — łatwe rozszerzanie.
- CSS Variables — łatwa zmiana motywu (np. dark mode w 30 minut).
- IntersectionObserver z graceful fallbackiem.
- JSON-LD dla SEO + Open Graph + Twitter Cards.

---

## Licencja

Treść i identyfikacja: © Flipiak Szczypuła.
Kod strony można swobodnie używać jako bazy własnych projektów.
