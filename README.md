# AgentFi — Stateless HTTP 402 (x402 V2) M2M Micro-Clearing Gateway

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

```bash
curl -i -X GET "[https://agentfi.vip/v1/extract](https://agentfi.vip/v1/extract)"
