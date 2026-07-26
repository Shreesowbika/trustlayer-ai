<div align="center">
  <img src="https://via.placeholder.com/120x120/121A2B/2DD4A8?text=TL" alt="TrustLayer AI Logo" width="120" />
  <h1>🛡️ TrustLayer AI</h1>
  <p><strong>Fintech-Grade Transaction Safety & Fraud Prevention Infrastructure</strong></p>
  
  <p>
    <a href="#the-problem"><img src="https://img.shields.io/badge/Track-Fintech-2DD4A8?style=for-the-badge&logo=moneymarket" alt="Track: Fintech"></a>
    <a href="#powered-by-nitrostack"><img src="https://img.shields.io/badge/Framework-NitroStack_SDK-F0A94E?style=for-the-badge&logo=typescript" alt="NitroStack"></a>
    <a href="#license"><img src="https://img.shields.io/badge/Status-Hackathon_Submission-4CAF50?style=for-the-badge" alt="Status"></a>
  </p>

  <p><em>Built for the NitroStack × Amrita University Hackathon</em></p>
</div>

---

## 🚨 The Problem

In the modern digital economy, Peer-to-Peer (P2P) marketplaces (like OLX, Facebook Marketplace) are plagued by sophisticated financial fraud. Millions of dollars are lost annually to scammers utilizing advanced manipulation tactics:
* **QR Inversion Scams:** Scammers send a `upi://pay` QR code, claiming it is for a "refund" or "advance payment," tricking victims into authorizing a deduction from their own accounts.
* **Off-Platform Diversion (P3 Interception):** Scammers lure victims off the secure platform to WhatsApp or Telegram where moderation tools cannot protect them.
* **Price Manipulation:** Scammers list fake products at artificially low prices to trigger FOMO (Fear Of Missing Out) and urgency.

Existing platforms lack active, context-aware intervention. They rely on passive warnings that users blindly ignore.

---

## 💡 The Solution: TrustLayer AI

**TrustLayer AI** is an invisible, real-time **Fintech Security Copilot**. It injects directly into existing marketplaces via a browser extension and acts as a specialized security layer.

Instead of generic chat bots, TrustLayer utilizes a **Multi-Agent Architecture** to evaluate listings, cross-reference live market pricing, verify WHOIS domain records, and decode UPI payloads in real-time. If it detects a highly probable scam, it executes **Bounded Autonomy** to intervene, injecting verification challenges directly into the chat or rendering unmissable financial fraud alerts.

---

## 🛠️ Powered by NitroStack

This project is built strictly around the **official `@nitrostack/core` TypeScript SDK**, utilizing its most powerful Agentic capabilities:

1. **`@Injectable()` & Dependency Injection:** The architecture is decoupled into specific domains (`ListingService`, `PaymentService`, `IdentityService`) managed natively by the NitroStack DI container.
2. **`@Tool()` Decorators:** We expose precise, typed Agentic capabilities (e.g., `qrDirectionVerify`, `priceAnomalyCheck`) strictly validated by **Zod schemas**.
3. **Execution Context:** Every tool invocation utilizes NitroStack's `ExecutionContext` to track tracing, logging, and transaction lifecycles.
4. **Bounded Autonomy:** Instead of an LLM freely hallucinating decisions directly to the user, our NitroStack Agents emit structured mathematical `Claims`. A central `PolicyService` performs **Evidence Fusion**, calculating posterior risk probabilities before taking autonomous action.

---

## 🏗️ Architecture & Agent Workflow

![TrustLayer AI Architecture](architecture.png)
---

## 🌟 Key Innovations

1. **QR Payment Inversion Detection:** TrustLayer intercepts QR codes in chats, decodes the raw `upi://pay` payload, and semantically compares it against the seller's chat messages. If the QR requests a payment while the seller claims a "refund", an immediate **Financial Fraud Alert** is triggered.
2. **Physical-World Verification (In-Platform P1):** TrustLayer can autonomously inject a random challenge code (e.g., `TL-8472`) into the marketplace chat box. It uses a DOM `MutationObserver` to detect when the seller uploads a verification photo, piping it through real **Tesseract.js OCR** to verify possession.
3. **Privacy-First SHA-256 Hashing:** Before transmitting any PII (Phone numbers, emails) from the page to the backend, the extension hashes the data using `crypto.subtle.digest`. The backend only evaluates cryptographic fingerprints.
4. **Live Market Price Intelligence:** The `ListingService` executes live DuckDuckGo web searches, calculates mathematical medians, and compares them against hardcoded brand benchmarks to detect "Too Good To Be True" FOMO pricing traps.

---

## 💻 Setup & Installation

### Prerequisites
* Node.js v18.0.0+
* Git
* Google Chrome (For extension loading)

### 1. Start the NitroStack Backend
```bash
git clone https://github.com/your-org/trustlayer-ai.git
cd trustlayer-ai
npm install
cp .env.example .env

# Start the NitroStack DI container and API router
npm run dev
```

### 2. Load the TrustLayer Chrome Extension
1. Open Google Chrome and navigate to `chrome://extensions/`.
2. Toggle **Developer mode** ON (top right).
3. Click **Load unpacked** and select the folder:
   `trustlayer-ai/frontend/extension`
4. The TrustLayer shield icon will appear in your browser!

---

## 🧪 How to Demo (Hackathon Guide)

### Scenario A: Testing on Real OLX (`olx.in`)
1. Open any listing or chat page on `https://www.olx.in`.
2. Click the floating cyan TrustLayer shield button in the bottom-right corner.
3. Watch the NitroStack backend extract context, run evidence fusion, and render the safety dashboard.

### Scenario B: The Fake QR Scam (Mock Marketplace)
1. Open the file `trustlayer-ai/mock-marketplace/index.html` in Chrome.
2. Select **"Scenario 3: Fake QR / Refund Scam"** from the top bar.
3. Click the TrustLayer shield icon.
4. **The Result:** The backend will detect the `upi://pay` string in the hidden page text, cross-reference it against the seller's claim of a "refund", and blast a highly visible red **🚨 FINANCIAL FRAUD ALERT** telling the user explicitly not to scan the QR.

---

## ⚖️ Hackathon Compliance
Built specifically for the **Fintech Track** of the NitroStack × Amrita Hackathon. All core logic heavily utilizes the official `@nitrostack/core` TypeScript SDK.
