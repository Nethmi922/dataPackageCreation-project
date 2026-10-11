# Custom Data Package Builder

A responsive front-end prototype for building a mobile data package from selected social apps and optional anytime data. The interface is implemented in `index.html` with plain HTML, CSS, and JavaScript; it does not require a build step.

## Features

- Select WhatsApp, YouTube, Instagram, Facebook, and TikTok independently.
- Choose `1 GB`, `2 GB`, `5 GB`, or `Unlimited` for each selected social app.
- Optionally add anytime data, usable outside the selected apps, in amounts from `1 GB` to `10 GB`.
- Choose whether anytime data is allocated per day or is one total allowance for the whole package period.
- Select a package validity of 1, 7, or 30 days.
- See a package summary and estimated price update as selections change.
- Open a detailed package review before the demo Activate action.
- Use the package builder on desktop or mobile screens.

## Run the Prototype

Open `index.html` directly in a browser, or serve the project folder through a local web server such as XAMPP. The social-media logos are loaded from the Simple Icons CDN, so an internet connection is needed to display them.

## Sample Rates

These are demonstration values in LKR, not official carrier prices.

| Data option | Rate |
| --- | ---: |
| WhatsApp | LKR 20 per GB; LKR 220 for Unlimited |
| Telegram | LKR 20 per GB; LKR 220 for Unlimited |
| imo | LKR 20 per GB; LKR 220 for Unlimited |
| Viber | LKR 20 per GB; LKR 220 for Unlimited |
| YouTube | LKR 40 per GB; LKR 420 for Unlimited |
| Instagram | LKR 35 per GB; LKR 390 for Unlimited |
| Facebook | LKR 25 per GB; LKR 320 for Unlimited |
| TikTok | LKR 40 per GB; LKR 420 for Unlimited |
| Anytime data | LKR 115 per GB |

The Unlimited app rates are flat sample prices for that app allowance before the package-validity multiplier is applied. Anytime data does not currently have an Unlimited option.

Telegram, imo, and Viber use the same illustrative messaging-app rates as WhatsApp until specific sample prices are configured.

## Estimate Calculation

Social-app charges are calculated by adding the selected app rates, then applying a multiplier based on package validity:

| Validity | Multiplier |
| --- | ---: |
| 1 day | 1.0 |
| 7 days | 1.8 |
| 30 days | 4.5 |

Anytime data is charged separately:

- **Entire period:** selected GB amount × LKR 115, charged once for the package period.
- **Per day:** selected GB amount × LKR 115 × number of validity days.

The estimated total is rounded up to the next LKR 10:

```text
estimate = round up to next LKR 10 (
  social app rates × validity multiplier + anytime data charge
)
```

### Example

The default selection is 1 GB WhatsApp, 1 GB YouTube, and 2 GB of anytime data for the entire 30-day period:

```text
( LKR 20 + LKR 40 ) × 4.5 + ( 2 × LKR 115 )
= LKR 270 + LKR 230
= LKR 500
Rounded estimate = LKR 500
```

## Important Limitations

- All prices are illustrative prototype estimates. Confirm actual rates with the mobile operator before using this in a real service.
- The Activate action is a demo only. There is no carrier API, payment processing, account authentication, or live package activation connected.
- The prototype uses example account and package details; replace them with authorized production data and services before deployment.
