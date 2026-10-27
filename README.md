# PesaBridge: M-Pesa payment gateway API for Kenya

**PesaBridge** is an M-Pesa payment gateway API. Developers get one API key and use a simple REST API to collect payments and send payouts, without dealing with Safaricom Daraja credentials, token handling or callbacks.

- **Website:** https://pesabridge.obedtech.name.ng/
- **API docs:** https://pesabridge.obedtech.name.ng/docs
- **Get an API key:** https://pesabridge.obedtech.name.ng/auth
## What you can do

- Collect M-Pesa payments with **STK Push**
- Collect with **scan-to-pay M-Pesa QR** codes
- Share **payment links** by WhatsApp or SMS, with no website needed
- Pay out to **M-Pesa numbers, bank accounts and till numbers**
- Receive **signed webhooks** with automatic retries, or poll transaction status
- Use **idempotency keys** to avoid double charges
- Keep a **transaction ledger** of every payment

## Quick example: STK Push

```bash
curl https://pesabridge.obedtech.name.ng/api/public/v1/stkpush \
  -H "Authorization: Bearer sk_live_xxx" \
  -H "Idempotency-Key: order_10231" \
  -H "Content-Type: application/json" \
  -d '{
    "amount": 250,
    "phone": "254708374149",
    "accountReference": "ORDER-10231"
  }'
```

The customer gets an M-Pesa prompt on their phone. Keep your secret key on your server only, never in a website or mobile app.

## Endpoints

Base URL: `https://pesabridge.obedtech.name.ng/api/public/v1`

| Method | Path | Purpose |
| --- | --- | --- |
| POST | `/stkpush` | Start an STK Push collection |
| POST | `/qr` | Create a scan-to-pay QR payment |
| GET | `/transactions/:id` | Check the status of a payment |
| POST / GET | `/links` | Create and list payment links |

Authentication: `Authorization: Bearer <secret key>`

Full documentation with HTML, Node.js and Python examples: https://pesabridge.obedtech.name.ng/docs

## Built by

[Obed Tech](https://pesabridge.obedtech.name.ng/), Kenya.

## Keywords

M-Pesa API, Daraja, STK Push, payment gateway Kenya, PesaBridge, M-Pesa payouts, M-Pesa QR, mobile money API
