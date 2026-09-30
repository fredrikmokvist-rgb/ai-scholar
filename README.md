# AI Scholar (PWA)

En enkel progressiv webbapp för att söka vetenskapliga publikationer – med AI-sammanfattning (TLDR) för varje träff.

## Funktioner

- Sök bland 250+ miljoner publikationer via OpenAlex API (CORS-vänligt och utan nyckel)
- AI-sammanfattning per publikation (SciTLDR-modellen)
- Abstrakt, citeringsantal, författare, år och tidskrift
- Läslista som sparas lokalt i webbläsaren
- Installerbar på hemskärmen och offline-kapabel tack vare service worker

## Köra lokalt

Service worker kräver att sidan serveras via http(s), inte file://. Starta en lokal server i projektmappen:

    python3 -m http.server 8000

Öppna sedan http://localhost:8000 i webbläsaren.

## Publicera på GitHub Pages

1. Öppna repots Settings och sedan Pages
2. Välj Deploy from a branch, branch: main, mapp: / (root)
3. Spara – appen publiceras inom några minuter på https://fredrikmokvist-rgb.github.io/ai-scholar/

## Teknik

Ren HTML, CSS och JavaScript – inga byggverktyg eller beroenden. Sökdata hämtas från OpenAlex (pålitligt, CORS-aktiverat), och AI-sammanfattningar (TLDR) hämtas i ett enda batch-anrop från Semantic Scholar; om det är hastighetsbegränsat visas abstrakten istället.
