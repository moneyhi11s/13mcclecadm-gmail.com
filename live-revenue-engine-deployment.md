# Live Revenue Engine Deployment

The Moneyhi11s Cloudflare project now contains a real tracking pipeline for the primary Copy Paste Millionaire Explodely affiliate campaign.

## What the build does

* Public presell page at `/offer`
* Source-tracked outbound links such as `/go/cpm?src=tiktok`
* Automatic Explodely `tid` generation for attribution
* Affiliate Sale ISN listener at `/api/explodely/isn`
* Durable Cloudflare Workflow for validating and recording each confirmed sale
* Duplicate-order protection
* Live click, sale, conversion-rate, commission, and campaign-source statistics
* No fake revenue counters; commissions increase only after an accepted Explodely sale notification

## Explodely listener configuration

After deployment, create a long random Cloudflare secret named `ISN_SECRET`. Then in Explodely Affiliate → Account → Instant Sale Notification configure:

* **ISN URL:** `https://YOUR-DOMAIN/api/explodely/isn?key=YOUR_SECRET`
* **Send ISN:** Yes
* **ISN Type:** POST (the listener also accepts GET)

## Promotion links

Use source-specific redirect URLs so confirmed sales can be attributed:

* TikTok: `/go/cpm?src=tiktok`
* YouTube: `/go/cpm?src=youtube`
* Pinterest: `/go/cpm?src=pinterest`
* Email: `/go/cpm?src=email`
* Presell page: `/offer`

{% hint style="warning" %}
Keep the ISN secret and all account credentials out of GitBook and source control. The system records real affiliate commissions; it does not guarantee or fabricate income.
{% endhint %}
