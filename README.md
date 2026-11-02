# Portfolio Page responsive

Esercizio Epicode – Settimana V, Giorno I: **mobile-first refactoring**.

Ho ripreso la Portfolio Page fatta nella Settimana I, Giorno IV e l'ho resa responsive, cioè leggibile e ben proporzionata su:

| Dispositivo | Larghezza |
|-------------|-----------|
| Mobile      | < 576px (stili di base) |
| Tablet      | da 768px |
| Desktop     | da 1200px |

## Obiettivi

- Usare il `viewport` meta tag
- Applicare l'approccio mobile-first con `min-width`
- Gestire immagini, tabella e form in modo responsive

## Struttura del progetto

```
index.html
grazie.html
assets/
  css/style.css
  image/climber.jpg
  image/everest.jpg
```

## Cosa ho fatto

### HTML
- Ho completato il meta viewport: `<meta name="viewport" content="width=device-width, initial-scale=1.0">`.
- Ho dato all'header l'id `site-header` e l'ho spostato fuori da `<main>`, così occupa tutta la larghezza.
- Ho avvolto la tabella delle esperienze in `<div class="table-wrapper">`.
- Ho spostato la sezione Contatti dentro `<main>`.
- Ho tolto un `</div>` in più e corretto il tag di chiusura in `grazie.html`.

### CSS – base mobile (< 576px)
- Immagini fluide: `img { max-width: 100%; height: auto; }`.
- Header con padding ridotto (`30px 16px 20px`) e `h1` con `clamp(1.8rem, 6vw, 3rem)`.
- Nav con i `<li>` in `inline-block` centrati: su mobile vanno a capo da soli.
- Padding di `main` e delle sezioni a 16px.
- Avatar centrato sopra il testo (`display: block; margin: 0 auto 16px`).
- Form: `width: 100%` e `font-size: 16px` su input, textarea, select e button; `width: auto` sul checkbox `#consenso`.
- Tabella: `.table-wrapper` con `overflow-x: auto` e `table` con `min-width: 480px`, così scorre in orizzontale senza allargare la pagina.

### CSS – tablet (`@media (min-width: 768px)`)
- Ripristinati i valori desktop: header `60px 20px 40px`, main `40px 20px`, sezioni `32px`.
- Avatar di nuovo flottato a sinistra, con `display: flow-root` sulla sezione per contenerlo.
- Input, textarea e select al 60%, bottone `width: auto`.

### CSS – desktop (`@media (min-width: 1200px)`)
- `h1` più grande (3.5rem).

### Extra
- **Secondo breakpoint** a 1200px (vedi sopra).
- **`clamp()` per h2**: `font-size: clamp(1.3rem, 4vw, 1.8rem)`.

## Come vederlo

Apri `index.html` nel browser e usa i DevTools (modalità dispositivo) per provare le larghezze 576px, 768px e 1200px.

---

© 2026 Gabriel Bollati

Scritto con l'aiuto di un modello (Readme) di ©Luca.