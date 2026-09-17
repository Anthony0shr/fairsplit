# 🤝 FairSplit — Cloud-Native Equitable Expense Sharing

> **Cloud Wars Hackathon Submission | AWS Cloud Club, SRMIST Delhi-NCR**  
> *Track: FinTech / Financial Inclusion / Serverless Cloud Architecture*  
> 🌐 **[Live Demo](https://anthony0shr.github.io/fairsplit/)** | 📁 **[Source Code](https://github.com/Anthony0shr/fairsplit)**

---

## 💡 Problem Statement
Splitting recurring group expenses (hostel rent, canteen bills, group outings, groceries) is traditionally handled by equal division. However, equal splits fail to account for unequal financial situations across peers.

Asking to pay less or negotiating custom amounts creates awkward social tension, causing individuals with lower liquidity to either overpay quietly, take on high-interest personal loans, or self-isolate from group activities entirely. Existing platforms (like Splitwise) force equal divisions or demand manual negotiations, keeping the awkward conversation alive.

---

## 🚀 The Solution: FairSplit
FairSplit acts as an **empathy layer** over standard group expense tracking.

When an expense is recorded, members have the option to mark their status as **"Tight this month"**. The platform algorithmically redistributes the bill:
- Members marked "Tight" automatically pay **50% of a standard equal share**.
- The remaining balance is evenly absorbed across the other group members.
- The recalculation happens instantly and programmatically, removing personal confrontation and preserving individual dignity.

---

## 📐 Mathematical Formulation

For an expense of total amount $T$ among $N$ group members, where $k$ members are marked as "Tight" ($0 \le k \le N$):

1. **Baseline Equal Share ($E$):**
   $$E = \frac{T}{N}$$

2. **Tight Member Contribution ($S_{\text{tight}}$):**
   $$S_{\text{tight}} = 0.5 \times E = \frac{T}{2N}$$

3. **Normal Member Contribution ($S_{\text{normal}}$):**
   $$S_{\text{normal}} = \frac{T - \left(k \times \frac{T}{2N}\right)}{N - k} = \frac{T(2N - k)}{2N(N - k)}$$

*Note: If all members select "Tight" ($k = N$), the system safely falls back to standard equal shares ($T / N$) to eliminate division-by-zero errors. Rounding deltas are preserved down to the exact paise.*

---

## ☁️ Cloud Architecture & Technologies Used

### Current MVP Implementation
- **Frontend / Client Compute:** HTML5, CSS3, Vanilla JavaScript (zero-latency, client-side edge calculation).
- **Deployment & Hosting:** Deployed on GitHub Pages / AWS Amplify with continuous edge delivery.

### AWS Serverless Cloud Roadmap (Round 2)
- **Edge Delivery:** Amazon CloudFront CDN for global content caching.
- **Microservices Engine:** AWS Lambda (Node.js) for serverless debt simplification and ledger calculations.
- **Persistence Layer:** Amazon DynamoDB for low-latency, encrypted multi-device group syncing.
- **Identity & Security:** Amazon Cognito for anonymous, tokenized peer-to-peer authentication.

---

## 🔗 Live Links
- **Live Interactive Demo:** https://anthony0shr.github.io/fairsplit/
- **Source Code Repository:** https://github.com/Anthony0shr/fairsplit
