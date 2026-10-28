# Zap Band Pricing and Cost Laboratory

Mission 3 is a separate browser-only laboratory for a proposed personal electrical-pulse wearable alarm. It does not change the Mission 2 website or confirm a student decision automatically.

## Run and publish

Node 22+; no dependency installation required. `npm test`, `npm run build`, then `npm run dev` serves http://127.0.0.1:4174. Equivalent direct commands are `node --test tests/model.test.mjs` and `node scripts/build.mjs`. Production assets are in `dist`. GitHub Actions deploys to Pages on main. Relative paths and hash routing support the repository base path. The browser DOCX library (docx 9.6.1, MIT) is bundled locally with its license.

## Research and assumptions

Mission 1 JSON is preserved in `data/competitors.json`. The spreadsheet, analysis report and Mission 2 implementation were inspected. Four brands and ten offers are retained. All competitor prices date to 2026-10-27 and are not live.

`data/defaults.json` contains 32 venture-specific cost allowances and seven primary-source references checked 2026-10-27. Stripe domestic card charges, Adafruit battery quantity pricing, a Connecticut LLC report fee and free hosting are directly researched references. Assembly derives from BLS annual wage data plus explicitly estimated production time and employer burden. Shipping and prototype board totals are estimates informed by published prices. Circuitry, tooling, safety testing, insurance, overhead and demand remain illustrative where quotes or evidence are absent. Research status does not establish technical suitability or product safety.

The base scenario assumes direct US online sales, home-based operations and Connecticut LLC overhead. It does not assume commercial premises, land or full-time employees. A static store with Stripe checkout is an operating assumption; the laboratory itself has no payments, backend, database, login, paid API or secret.

## Financial model

All operating results use one annual USD period. Fixed monthly costs multiply by 12; annual costs stay annual; per-sale costs multiply by annual billable sales; percentage costs multiply by gross revenue. Refund reserve is a cost allowance, not a second revenue deduction. One sale assumes one order/payment. Startup cash is separate. Only assets with an explicit positive life contribute straight-line annual depreciation (zero salvage, full year in service). Initial inventory reserve is working capital, not additional P&L expense.

Product base variable cost plus assigned costs determines unit cost. Shared variable expenses apply per billable sale or revenue to every product. Product-specific fixed expenses stay with that product. Shared fixed allocation can use revenue, unit or equal shares; zero totals fall back to equal shares. Business totals count overhead once.

Break-even uses fixed cost divided by weighted contribution at the entered quantity mix. Zero total quantities use an explicit equal mix. Nonpositive contribution returns null, not infinity or a misleading finite result. Whole-sale totals round up; for multiple products this approximates the fractional mix. Break-even revenue uses the unrounded intersection. Margin of safety uses theoretical break-even. Quantity sensitivity rounds each product to whole sales. These calculations assume constant unit economics and no capacity constraints; they omit taxes, financing, inventory timing and demand elasticity.

One-time, per-unit, bundle and service scenarios are supported. Subscription models are intentionally not activated for the documented hardware concept. Individual device competitor comparisons require the comparable-device setting and one-time/per-unit model. Bundles and services are excluded. Similar price means within 5%; equal prices are separately identified. GBP and subscriptions never enter USD hardware comparisons.

## Scenarios and persistence

Lean and Expansion vary only selected overhead by 0.5× and 2×; initial volume remains 1,200 in each. Scenario switching preserves edits. Custom scenarios and 60%/100%/140% volume assumptions are editable. localStorage is browser-local and may be lost; JSON backup/import restores the working model. Import validates financial structure and resets review/confirmation.

## Decision workflow and privacy

The review engine is deterministic and documents thresholds in the UI and report. A model fingerprint invalidates prior evaluation/confirmation after changes. A written explanation of at least 20 characters and acknowledgment of major warnings are required. High-risk prices can still be confirmed. Both final exports derive from one detached snapshot; no user decision is confirmed by the build process.

The full report and JSON contain private financial data. Only `publicWebsiteData` is intended as potential public product copy; performance claims still require validation. `privateDecision` contains costs, assumptions and risk findings. The student setup supplied a live Mission 2 URL in its repository field. The exact supplied URL is retained; `originalRepositoryUrl` is null and the inferred repository is separately identified for verification before Mission 4.

## Verification

`tests/model.test.mjs` includes independent arithmetic fixtures for annualization, depreciation, percent fees, negative/zero contribution, multi-product allocation, zero volumes, filtering, confirmation locks, snapshot immutability and input validation. `scripts/test-report.mjs` creates clearly labeled QA-only DOCX/JSON using an external bundled docx module path. Browser QA uses `?test=1`, an isolated storage namespace; its confirmations are test-only. No QA test decision is a real student confirmation.

No sales forecasts or failure probabilities are claimed. Validate engineering, compliance, insurance, landed supplier costs and willingness to pay before launch. Mission 4 is not started.
