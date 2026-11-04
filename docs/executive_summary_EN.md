# Google Online Store · Digital Marketing Analysis: Channels, Purchase Funnel and Devices (September 2026)

**Author:** Dámaris Cubos Rosas · **Tools:** Google Analytics 4 (GA4) · Looker Studio
**Data:** GA4 demo account of the Google Merchandise Store · September 1–30, 2026 · 137,067 sessions · 1,921 purchases · USD 340,182 in revenue (the demo account rounds some figures)

---

## 🎯 Key message

> **94% of purchases come from the United States, even though some countries have many sessions and almost no purchases. The store should confirm which countries it ships to before deciding on marketing actions. In addition, only 24% of users who begin checkout on mobile complete the purchase, versus 53% on desktop; testing the checkout on mobile and comparing it with desktop is recommended to find the cause.**

---

## 1. Context

Google's online store sells branded products. This project is a **simulated business case**: the marketing director must decide which channels, devices and countries to focus on next quarter. The questions were defined at the start, before looking at the data:

1. Which channels generate the most purchases and revenue, and which bring many sessions but few purchases?
2. At which step of the purchase journey (view product → add to cart → begin checkout → purchase) do people drop off the most?
3. Which devices and countries generate the most purchases, both in total and relative to their sessions?

**Key terms:** a **session** is a visit to the site (one user can have several). A **channel** is the route a person took to arrive (search engine, ads, links from other sites, etc.). The **purchase funnel** is the series of steps a person follows until buying; people are lost at every step.

---

## 2. Main findings

### 📣 Channels (Question 1)
- **Two channels bring almost everything:** Direct (GA4 cannot identify where the person came from) and Organic Search (a click on an unpaid search-engine result) add up to **87% of sessions and 87% of revenue**. The business depends on two channels.
- **Paid Search (search ads) and Unassigned (GA4 could not assign a channel) bring 11% of sessions but only 3% of purchases.** They convert 0.37% and 0.49% of sessions into purchases, versus 1.4% for the whole site.
- Small channels (social, video, email, shopping, cross-network) show high or odd rates, but with very few sessions (under 1,000 each): **nothing is concluded about them**. Referral (links from other sites) has the highest purchases-per-session rate (3.56%) among channels with 1,000 sessions or more (2,415 sessions), but deserves its own review.

### 🛒 Purchase funnel (Question 2)
- **Of the people who view a product, 70% do not add it to the cart.** This is the biggest drop, but it may be normal behavior for people who are just browsing.
- **Of the people who begin checkout, 52% do not buy.** This loss is more costly, because these people already showed purchase intent.
- **The device gap is large:** of those who begin checkout, **24% buy on mobile and 53% on desktop**. The gap holds within a single channel (in Organic Search: 16.4% on mobile and 41.9% on desktop), so it is not explained only by which channel brings people in.
- My initial hypothesis was that the biggest loss was at checkout. **It was partly right:** the step with the most drop-off is viewing the product → cart, although the checkout drop-off is the most costly.

### 📱 Devices and countries (Question 3)
- **Mobile brings 65% of users, but desktop accounts for 92% of purchases.**
- Excluding sessions without an identified country, **desktop converts 2.8% of its sessions into purchases and mobile 0.5%**. The gap shrinks once that doubtful traffic is removed, but it persists.
- **The United States accounts for 94% of purchases** with 39% of sessions. No other country with 1,000 sessions or more reaches the site average of 1.4% purchases per session.
- Tablet and smart tv have fewer than 1,000 sessions: they are small samples and are not interpreted.

### ⚠️ Unexpected finding: traffic without a location
- **32% of sessions (43,403) have no identified country ("not set") and generated no purchases at all.** Almost all of them are Direct and mobile, and they barely view products.
- This inflates **sessions**, not **purchases or revenue**: without that group, the site's purchases per session rise from 1.4% to ≈ 2.05%. This explains why Direct and mobile look "bad" in percentages. That is why the dashboard excludes this group when comparing devices and countries, and flags it with a note.

---

## 3. Recommendations

| # | Recommendation | Why (data) | What we don't know / missing data |
|---|---|---|---|
| 1a | **💰 Paid Search: compare ad costs with the revenue the channel generated** and, if the cost is similar or higher, consider reducing or redesigning the investment. | Paid Search combined with Unassigned: 11% of sessions, only 3% of purchases; channel revenue USD 7,618 for the month. | Ad costs are unknown; this data is needed before deciding. Revenue is not profit: the figure is a signal, not proof. |
| 1b | **🏷️ Unassigned: ask the marketing team to review link tagging** (the marks that let GA4 know which channel each session came from). | GA4 could not identify the channel of 7,296 sessions. | It is unknown why they appear without a channel; tagging is a hypothesis to confirm. |
| 2 | **🛒 Test the checkout process from a phone**, check whether payment methods work the same on mobile and desktop, and verify in GA4 whether there is a record showing **exactly where in checkout** the purchase is lost. | Of those who begin checkout: 24% buy on mobile, 53% on desktop. | The reason for the drop-off is unknown; the hypotheses are an unclear process or too few payment methods. The 70% lost between viewing the product and the cart remains to be investigated (it may be normal behavior). |
| 3 | **🌎 Confirm which countries the store ships to** before deciding whether marketing should strengthen the United States or other countries with many sessions. **📱 Test usability on mobile and compare it with desktop** (the same review as recommendation 2). | United States: 94% of purchases. Desktop converts 2.8% of its sessions and mobile 0.5%. | It is unknown which countries the store ships to, or whether sessions from countries with almost no purchases are low quality. It is also unknown whether the mobile gap comes from a poor experience or from people who browse on their phone and buy later on desktop. |
| 4 | **🔎 Review the origin of sessions without a country** (marketing/analytics team) and, meanwhile, **report them separately and exclude them from the conversion calculation**, explaining why. | 32% of sessions have no identified country and generated no purchases. | It is unknown whether this is automated traffic, sessions without location for privacy reasons, or mis-tagging; the review must confirm it before deciding. |

*These recommendations include no numeric targets or impact estimates because the demo account has no advertising or product costs. The baseline figures (24% vs. 53% purchase after beginning checkout, 3% vs. 11%, 2.8% vs. 0.5%) serve as a starting point to measure any improvement.*

---

## 4. Assumptions and limitations

- **Demo account:** data from the Google Merchandise Store, read-only, with some rounded figures. Channel and device totals add up to slightly more than total sessions (140,051 and 137,980 versus 137,067); the cause could not be confirmed.
- **No cost data:** there are no ad or product costs, so **revenue is not profit** and profitability is not assessed.
- **Direct** means unknown origin, not necessarily someone who typed the address. Some traffic may be internal to Google (there are sessions from Mountain View, Sunnyvale and San Jose).
- **Small samples:** channels, countries and devices with fewer than 1,000 sessions are not used for recommendations. This is my own judgment-based criterion, not an exact rule.
- **Users are not additive:** the same user can visit from more than one device, so the sum by device exceeds the total number of users.
- **Open funnel:** the dashboard counts users per event; GA4's closed funnel gives similar, not identical, figures. The order of the losses matches.
- **One month only:** seasonality and trends cannot be confirmed. There is a spike in users around September 28–29 that was not investigated.
- **Correlation is not causation:** GA4 shows **where** a difference occurs, not **why**. The causes mentioned are hypotheses.

---

## 5. Suggested next steps

1. Obtain the **advertising costs** to assess the profitability of Paid Search.
2. Confirm **which countries the store ships to** and check for low-quality sessions in India and Japan.
3. Review the **steps inside checkout** in GA4 (shipping and payment details) to locate where people drop off.
4. Analyze **several months** to see trends and seasonality, and investigate the September 28–29 spike.
5. Review **which sites generate the Referral traffic**, the channel with the highest purchases-per-session rate among those with an acceptable sample.
6. Repeat the analysis with GA4 data in **BigQuery (SQL)** for full control over the definitions.
