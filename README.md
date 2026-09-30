# AI Scholar (PWA)

En enkel progressiv webbapp för att söka vetenskapliga publikationer – med AI-sammanfattning (TLDR) för varje träff.

## Funktioner

- Sök bland 200+ miljoner publikationer via Semantic Scholars öppna API
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

Ren HTML, CSS och JavaScript – inga byggverktyg eller beroenden. Hanterar automatiskt CORS- och hastighetsbegränsningar i Semantic Scholars API med reservvägar, och faller tillbaka på exempeldata om API:et inte kan nås.
