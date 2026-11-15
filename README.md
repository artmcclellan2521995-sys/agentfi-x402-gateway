# AgentFi — Stateless HTTP 402 (x402 V2) M2M Micro-Clearing Gateway
> **Live Interactive Playground:** https://sprightly-unicorn-59c755.netlify.app *(Simulate the HTTP 402 handshake & Base L2 USDC verification in your browser)*
**AgentFi** is a production-grade, stateless machine-to-machine (M2M) payment gateway bridging wholesale multilateral clearing logic with high-frequency autonomous AI agent micro-transactions.

---

## 1. Live Production Endpoint

* **Gateway URL:** `https://agentfi.vip/v1/extract`
* **Discovery Manifest:** `https://agentfi.vip/x402/discovery` (MCP-compatible tool discovery)
* **Settlement Rail:** Base L2 USDC (`Chain ID: 8453`)
* **Unit Pricing:** `$0.05 USDC` per verified payload request
* **Deliverable:** Denoised CNH/USD offshore liquidity matrix with deterministic SHA-256 integrity proof (`X-Payload-Hash`)

---

## 2. Quick Verification (cURL Test)

Test the live HTTP 402 payment challenge handshake directly from your terminal:

    curl -i -X GET "https://agentfi.vip/v1/extract"

### Expected Gateway Challenge (`HTTP/1.1 402 Payment Required`)
The gateway responds with deterministic x402 V2 payment headers specifying the Base L2 USDC recipient, atomic amount (`$0.05 USDC`), and anti-replay nonce:

    HTTP/1.1 402 Payment Required
    Content-Type: application/json
    X-Protocol-Version: x402-v2
    X-Network-Chain-Id: 8453
    X-Payment-Token: USDC

    {
      "error": "payment_required",
      "protocol": "x402-v2",
      "amount_usdc": "0.05",
      "chain_id": 8453,
      "message": "Attach signed Base L2 USDC payment proof header to execute extraction."
    }

---

## 3. Core Architectural Guarantees

1. **Zero-Gas Offline Cryptographic Verification:** Eliminates on-chain verification latency at the edge while maintaining sub-500ms global response times via Cloudflare Zero Trust SSL.
2. **Idempotent Retry Protection:** On-chain transaction hashes and payment proofs act as deterministic idempotency keys in the replay-protection ledger—mid-flight connection drops never trigger double-charging.
3. **Gateway-Level Spend Dampers:** Enforces per-agent rate and budget circuit breakers outside the LLM context window to prevent recursive token burn.
4. **Atomic Non-Custodial Settlement:** No user balances held; if upstream extraction fails schema integrity checks, settlement aborts prior to final commit.

---

## 4. Collaboration & Contact

* **Architect:** Yixuan Li (Kelly) — Protocol & Automation Architect | MBA (Distinction, mBridge CBDC & Agent Payment Rails)
* **Open For:** AI Agent / Stablecoin Ecosystem Integrations, Technical Advisory, and Remote Protocol / Solutions Architect Roles
* **Direct Inquiry:** `artmcclellan2521995@gmail.com`
