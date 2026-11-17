# Oasel Capital — Private Credit Management Dashboard

[![Live Demo](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-blue?style=for-the-badge&logo=github)](https://mrchandrayee.github.io/oasel-private-credit-dashboard/)
[![HTML](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org) [![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org) [![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](./LICENSE)

A runnable HTML/CSS/JavaScript reconstruction of the uploaded **5.63-second** screen recording (720 × 1280, 30 fps).

## Run locally
1. Extract `oasel-private-credit-dashboard.zip`.
2. Open `index.html` in Chrome, Edge, Firefox or Safari.
3. Select the left sidebar sections to navigate.
4. Try the property gallery, risk stress grid, payment modal and new-record actions.

No npm install, build step, server, API key or backend is required.

Optional local server:
```bash
python3 -m http.server 8000
```
Open `http://localhost:8000`.

## What is visible in the video

The screen is branded **Oasel — Private credit desk**. The profile shown is **Sana Whitlock · Head of credit**. The UI uses a warm charcoal/olive palette, cream text, and bright lime active states.

### Sidebar navigation
- Dossier
- Portfolio
- Pipeline (badge 4)
- Loans
- Borrowers
- Payments (badge 2)
- Risk
- Documents
- Reports
- Settings

Top bar: `Oasel Capital`, search for loans/borrowers, `+ New`, appearance control and notifications.

### Dossier — Casa Duna
Visible record:
- `L-1042`
- Boutique stay · Twentynine Palms, CA
- Senior debt, pool and solar retrofit funded from cash in 2025; trading ahead of plan
- Status: Current
- 6 keys · 810 booked
- Property gallery strip
- Loan-to-value gauge: **62.9%**
- At funding: **66.1%**
- Balance: **€1.58m**
- Limit: **70%**
- Buttons: Watch, Documents, Record payment

### Portfolio
Visible values:
- Book outstanding: **$14.31m**
- 11 loans
- Weighted LTV: **60.0%** (limit 70%)
- Weighted DSCR: **1.20x** (floor 1.25x)
- In arrears: **$16,973** (2 payments)
- Outstanding balance chart
- “Needs a decision” list, including Palmera Court, Stonebrook Barn, Glass Pavilion and Alder House.

### Risk
The video shows a **Stress grid** with:
- Stress axes for income change and interest-rate rises
- 5-column heatmap with loan counts / percentages
- A right-side summary: **7 loans break**, **$10.54m of the book at risk**
- Tabs: Stress grid, Watchlist, Covenants

## Readable original TypeScript code from `src/motion.ts`

The source panel is legible in the video. The visible snippet is transcribed below, preserving the identifiers and easing values (formatting normalized):

```ts
export function slidePill(pill: HTMLElement, el: HTMLElement) {
  const box = pill.parentElement!;
  const W = box.offsetWidth, H = box.offsetHeight;
  const to: Edges = {
    l: el.offsetLeft, r: W - el.offsetLeft - el.offsetWidth,
    t: el.offsetTop, b: H - el.offsetTop - el.offsetHeight,
  };
  const st = (pill as PillHost).__st;
  const fwd = to.t > st.t;
  const [lead, trail] = fwd ? ['b', 't'] : ['t', 'b'];
  const paint = () => gsap.set(pill, { clipPath: clip(st) });
  gsap.to(st, { [lead]: to[lead], duration: 0.36,
    ease: 'power3.out', onUpdate: paint });
  gsap.to(st, { [trail]: to[trail], duration: 0.55,
    ease: 'power3.inOut', onUpdate: paint });
}
```

The video does not show the definitions of `Edges`, `PillHost`, or `clip`, nor the code that initializes `__st`. These are not invented as part of the transcription. The included runnable app uses its own CSS/JavaScript navigation state and does not require GSAP.

## Included functionality
- Dossier, Portfolio, Pipeline, Loans, Borrowers, Payments, Risk, Documents, Reports and Settings screens.
- Collapsible left sidebar and responsive layout.
- Dark / light appearance toggle.
- Casa Duna property gallery with thumbnail switching.
- LTV gauge and portfolio metrics.
- Portfolio loan register and decision list.
- Pipeline opportunities and stage progress.
- Borrower directory and payments register.
- Interactive risk stress grid with selectable cells.
- Risk Watchlist and Covenants tabs.
- New loan application / borrower modal.
- Record payment and upload document demo dialogs.
- Search navigation and toast feedback.

## Project files
- `index.html` — dashboard shell and modal.
- `styles.css` — charcoal/olive theme, cards, charts, gallery, tables and responsive layout.
- `app.js` — sample credit book data, navigation, pages and demo interactions.
- `README.md` — source-derived observations, visible TypeScript snippet and run guide.

## Accuracy and limitations
This is a screen-based frontend reconstruction, not the original Oasel source repository. The video shows a running dashboard and only one readable TypeScript motion helper, not the complete application source. Other page content is reconstructed from visible labels, figures and UI elements; screens not shown in the short clip use coherent demo layouts. Property imagery is loaded from Unsplash and requires internet access.

No loan servicing, banking, borrower KYC, credit bureau, document storage, payment processing, underwriting model or external financial data is connected. All records and actions are local demo data. Currency symbols/values are reproduced as displayed where legible; sample secondary records are illustrative.

## 👨‍💻 Author

**mrchandrayee** · [GitHub](https://github.com/mrchandrayee)

## 📄 License

[MIT License](./LICENSE)
