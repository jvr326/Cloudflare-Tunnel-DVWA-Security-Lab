# Cloudflare Tunnel & DVWA Security Lab

## 🚀 Project Overview
A hands-on cybersecurity portfolio project demonstrating how to securely expose a local vulnerable web application to the public internet using Cloudflare Tunnels, and protecting it using Cloudflare Zero Trust HTTP Gateway firewall rules.

---

## 🏗️ Architecture & Workflow
1. **Local Environment:** Damn Vulnerable Web Application (DVWA) running inside a local Docker container on `http://localhost:8080`.
2. **Ingress/Egress Tunnel:** Connected via `cloudflared` Quick Tunnels to provide secure, encrypted public HTTPS access without opening inbound router ports or owning a public root domain.
3. **Security Policy Layer:** Cloudflare Zero Trust Gateway Layer 7 HTTP firewall policies inspecting and controlling inbound traffic.

---

## 🛠️ Step-by-Step Implementation

### 1. Deploying the Vulnerable Application
* Launched the DVWA container locally via Docker mapped to port `8080`.

### 2. Establishing the Cloudflare Quick Tunnel
* Initialized the tunnel from the terminal:
  ```bash
  cloudflared tunnel --url http://localhost:8080
