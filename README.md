Here is the complete, properly formatted, ready-to-paste `README.md` file for your GitHub repository:

```markdown
# 🛡️ TrustLayer AI
> **Next-Generation Transaction Safety & Fraud Prevention Infrastructure** > *Built exclusively for the NitroStack × Amrita University Hackathon (Fintech Track)*

---

## 🚨 The Fintech Problem: Why Existing Systems Fail

In the booming Peer-to-Peer (P2P) digital economy (e.g., OLX, Facebook Marketplace), buyers transact directly with strangers. The current security paradigm on these platforms relies entirely on **passive, generic warnings** (e.g., *"Do not share OTP"*).

This approach has fundamentally failed because scammers use advanced psychological manipulation (urgency, authority) to induce "warning fatigue," causing victims to ignore static banners. The result is millions lost to:

* **Semantic QR Inversions:** Scammers disguise `upi://pay` requests as "refunds," tricking victims into authorizing debits from their own accounts.
* **Platform Diversion (P3 Interception):** Scammers lure victims off-platform to unmoderated channels (WhatsApp, Telegram) to execute the fraud.
* **Price Manipulation:** Scammers exploit FOMO by listing high-value items at impossible prices.

> **The Gap:** There is no infrastructure that provides active, context-aware intervention at the exact moment a scam is occurring.

---

## 💡 The Novel Solution: TrustLayer AI

**TrustLayer AI** flips the security paradigm from *Passive Warning* to **Active Intervention**.

It operates as an invisible, real-time Fintech Security Copilot that injects directly into the DOM of existing marketplaces. Powered by a Multi-Agent NitroStack backend, it doesn't just read text—it understands the intent of the transaction. When a high-probability scam is detected, TrustLayer executes **Bounded Autonomy** to dynamically halt the user, inject verification challenges into the chat, or render highly specific financial fraud alerts that cannot be ignored.

---

## 🏆 What Makes This Unique? (Core Innovations)

TrustLayer AI introduces four novel engineering approaches to P2P security:

### 1. 💳 Semantic QR Inversion Detection (The Money Guard)
* **The Innovation:** Traditional systems cannot scan QR codes inside chats. TrustLayer extracts hidden QR payloads from the DOM, decodes the `upi://pay` string, and uses NitroStack Agents to cross-reference the direction of the money flow with the human conversation.
* **The Uniqueness:** If the seller types *"Scan this for your refund,"* but the QR code actually requests a payment, TrustLayer immediately detects the semantic inversion and flags a **CRITICAL financial fraud alert**, stopping UPI scams before the PIN is entered.

### 2. 📸 Autonomous Physical-World Verification (In-Platform P1)
* **The Innovation:** To prove a seller actually owns an item, TrustLayer introduces autonomous "Friction." It uses JavaScript to physically type a challenge (e.g., *"Upload a photo with code TL-8472"*) into the seller's chat box.
* **The Uniqueness:** It utilizes a DOM `MutationObserver` to watch for the seller's image upload. Once uploaded, the image is piped through live `Tesseract.js` OCR (Optical Character Recognition) to verify the physical code exists in the real world. If verified, the Policy Engine dynamically recalculates the risk score to "Safe."

### 3. 🔒 "Zero-Knowledge" Privacy-First Architecture
* **The Innovation:** Scraping DOM data raises massive privacy concerns. TrustLayer solves this by implementing in-browser cryptographic hashing.
* **The Uniqueness:** Before any phone number or email leaves the user's device, the Chrome Extension uses `crypto.subtle.digest` to convert it into a SHA-256 fingerprint. The NitroStack backend only ever receives and analyzes hashes, ensuring total compliance with modern Fintech data privacy laws (DPDP/GDPR).

### 4. 📈 Dynamic Live-Market Pricing Agent
* **The Innovation:** Fraudulent listings often rely on "Too Good To Be True" pricing. TrustLayer doesn't rely on static, stale databases.
* **The Uniqueness:** The `ListingService` Agent executes a live DuckDuckGo web search, scrapes current market snippets, calculates the mathematical median price, and strictly enforces a 20% anomaly threshold against brand benchmarks (e.g., Apple, Realme). It calculates exact percentage deviations:
  $$\text{Deviation (\%)} = \left| \frac{\text{Listed Price} - \text{Market Median}}{\text{Market Median}} \right| \times 100$$

---

## ⚙️ The Multi-Agent Pipeline Architecture


```

┌─────────────────────────┐
│  Frontend Interceptor   │ (Extracts DOM, QR Payloads & SHA-256 Hashed PII)
└────────────┬────────────┘
│
▼
┌─────────────────────────┐
│   NitroStack Services   │ (Payment, Listing, Conversation & Identity Agents)
└────────────┬────────────┘
│
▼
┌─────────────────────────┐
│  Evidence Fusion Engine │ (Calculates Time-Decayed Risk Claims)
└────────────┬────────────┘
│
▼
┌─────────────────────────┐
│    Bounded Autonomy     │ (Triggers In-Browser Interventions & UI Alerts)
└─────────────────────────┘

```

1. **The Senses (Frontend Interceptor):** The extension silently monitors the page, extracting the Title, Price, Description, and Full Page Text (including hidden QR payloads). It hashes PII and sends the payload to the backend.
2. **The Brain (NitroStack Services):** Data is routed to specialized, decoupled NitroStack Tools:
   * `PaymentService`: Analyzes QR/UPI payloads for semantic inversions.
   * `ListingService`: Checks for extreme price anomalies.
   * `ConversationService`: Scans for high-pressure urgency and psychological manipulation.
   * `IdentityService`: Queries live RDAP WHOIS registries to detect burner domains.
3. **The Judge (Evidence Fusion):** Instead of relying on raw LLM output (which risks hallucination), our Agents emit mathematical **Claims**. The `PolicyService` aggregates these claims using a time-decayed multiplicative risk algorithm to generate a final Posterior Risk Score.
4. **The Muscle (Bounded Autonomy):** Based on the exact risk score, TrustLayer autonomously executes actions in the browser—from halting off-platform links to rendering glowing red fraud alerts.

---

## 🛠️ Pure NitroStack Architecture

This project pushes the capabilities of the official `@nitrostack/core` TypeScript SDK:

* **`@Injectable()` DI Container:** The entire architecture is decoupled into distinct domains (`ContextService`, `PolicyService`, `PaymentService`) managed natively by NitroStack Dependency Injection.
* **Strict `@Tool()` Decorators:** We expose precise Agentic capabilities validated strictly by **Zod schemas**, ensuring deterministic inputs and outputs.
* **Context Preservation:** Every invocation utilizes NitroStack's `ExecutionContext` to track distributed tracing and transaction lifecycles, proving enterprise-grade readiness.

---

## 🚀 Getting Started

### Prerequisites
* Node.js >= 18.x
* npm / pnpm / yarn
* Google Chrome (or Chromium-based browser)

### Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/trustlayer-ai.git](https://github.com/your-username/trustlayer-ai.git)
   cd trustlayer-ai

```

2. **Install Dependencies:**
```bash
npm install

```


3. **Environment Setup:** Create a `.env` file in the root directory and configure your keys:
```env
PORT=3000
NITROSTACK_API_KEY=your_nitrostack_key

```


4. **Start the NitroStack Server:**
```bash
npm run dev

```


5. **Load Extension in Browser:**
* Open Chrome and navigate to `chrome://extensions/`
* Enable **Developer mode** (top right toggle).
* Click **Load unpacked** and select the `dist/extension` or `extension` folder.



---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

```

```
