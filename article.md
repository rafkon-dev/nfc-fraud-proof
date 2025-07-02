# 🔒 NFC Fraud: A Proof-of-Concept You Shouldn't Ignore

**Author:** Rafał Konieczek  
**Date:** 02.07.2025  
**Support:** [Buy me a coffee](https://www.buymeacoffee.com/rafal)

---

## ✨ Introduction – "Did it work or not?"

In a world where silence equals safety, it's worth asking:  
**Does no alarm really mean no threat?**

This is not a "hack" in the traditional sense.  
It's a **proof-of-concept exposing weaknesses** in the assumptions around NFC-based payments.

---

## 🎯 Goal

To show how it's possible to:

- obtain an **offline NFC authorization**,  
- **delay or migrate** that approval,  
- and **complete a transaction later**, without the cardholder being present — or aware.

---

## 🧪 The Scenario

1. A victim taps their card on a public NFC terminal (parking meter, kiosk, etc.)  
2. The system, lacking online access, **buffers the authorization** locally  
3. The transaction "fails" (or seems to), and the victim walks away  
4. Meanwhile:
   - the authorization remains accessible
   - it can be **captured, transferred or cloned**
   - and **replayed** elsewhere, within the allowed window

---

## ⚙️ Why this works

This is not an exploit. It’s **a trust model failing silently**.

- NFC terminals **may store authorizations** locally (for later sync)
- Cards **do not bind a specific terminal or moment**
- Most systems assume the transaction is local and immediate

If any of these assumptions are violated — **the whole structure cracks**.

---

## 📉 What's the risk?

From the cardholder's perspective:  
"Nothing happened, it failed."

From the bank’s side:  
"It looks legitimate."

From the attacker’s side:  
"I used your card — you just didn’t know when."

---

## 🧠 Takeaways

- This is not card hacking.  
- It's **contextual misuse of trust**, not cryptographic failure.  
- The issue lies not in security — but **in timing, location, and implicit assumptions**.

Statistically rare? Yes.  
Technically possible? Absolutely.  
Traceable? Only if you know *where and when* to look.

---

## 🧩 Get Involved

This repository includes:
- The original concept in Polish (`nfc-fraud-proof.txt`)
- This article (`article.md`) – to share, adapt, or expand

If you find it valuable — please ⭐ the repo or grab me a ☕:  
👉 [https://www.buymeacoffee.com/rafal](https://www.buymeacoffee.com/rafal)

Stay sharp.  
— Rafał
