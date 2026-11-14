# AgentFi — Stateless HTTP 402 (x402 V2) M2M Micro-Clearing Gateway

[![Protocol](https://img.shields.io/badge/Protocol-HTTP%20402%20%2F%20x402%20V2-0284c7)]()
[![Network](https://img.shields.io/badge/Settlement-Base%20L2%20USDC%20(8453)-0f172a)]()
[![SLA](https://img.shields.io/badge/Edge%20SLA-%3C%20500ms-10b981)]()
[![Custody](https://img.shields.io/badge/Architecture-Non--Custodial%20%2F%20Zero--Gas-334155)]()

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
