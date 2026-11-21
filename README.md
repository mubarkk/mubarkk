# Mubark Kalil

Full-stack developer and automation engineer. I build complete products: automation pipelines that connect APIs, web apps with Stripe subscriptions, and iOS apps.

📧 mubark.kalil@gmail.com · [LinkedIn](https://linkedin.com/in/mubarkkalil) · Open to relocating to Dubai

---

## 1. Automated Video Content & Publishing Pipeline (n8n)

A daily automation that turns a product listing into a finished short-form video and posts it to 5 platforms (Instagram, Facebook, X, YouTube, TikTok) with no manual steps.

**▶ [Videos the pipeline produced + workflow screenshots](https://drive.google.com/drive/folders/1BjzVs6Mz_qple7wTOEaIAUhCCg7akhBZ?usp=drive_link)**

![Full workflow](https://github.com/user-attachments/assets/3f1272a4-7134-4018-a839-ecdfeb1005fb)

**How it works**

```
Google Sheets (inventory)
  → GPT-4o vision: analyze product image
  → GPT-4o: write script + 3 scene prompts
  → ElevenLabs: voiceover
  → Veo 2: generate 3 video clips (poll until done)
  → FFmpeg: combine clips + audio
  → Upload-Post: publish to 5 platforms
  → Save post links back to the sheet
```

**What I built**

- **Status-based stages:** `new → ready_to_video → ready_to_publish → posted`. Each stage only picks up its own records, so a failed run picks up where it stopped.
- **Polling and retries for long jobs:** Veo video generation is checked on a timer, and a clip is downloaded only once it's done and has a file link.
- **Duplicate prevention:** I found that matching records by product name caused wrong updates when two products had the same name, so I switched to UUID primary keys and gave existing rows IDs.
- **JavaScript data parsing:** turns messy price text like `Reg. $8,300 → 22% Off → Now: $6,499` into structured fields, then scores each product so API spend goes to the best ones first.
- **Tracking:** every published post's link is saved back to its record.

**Tools:** n8n, JavaScript, OpenAI GPT-4o, ElevenLabs, Google Veo 2, FFmpeg, Google Sheets API, Upload-Post API

---

## 2. Afaan: Language-Learning Web App with Subscriptions

A web app for learning the Oromo language, which I built and deployed solo.

- Set up Stripe payments and recurring subscriptions.
- Used Stripe webhooks to keep each user's subscription status and paid access in sync (different web app, CCI).

*The hosting platform has since shut down, so there's no live link. Here are screenshots from the Stripe dashboard:*

![Stripe screenshot 1](https://github.com/user-attachments/assets/dc0a4147-82a1-4124-80d2-52692393b96e)
![Stripe screenshot 2](https://github.com/user-attachments/assets/200654b3-c9f6-4482-8204-4f53bed5f2c3)
![Stripe screenshot 3](https://github.com/user-attachments/assets/592a7620-ea31-48a8-9255-964dd8475749)

**Tools:** Stripe API, webhooks

---

## 3. CEILR: iOS App

A production iOS app built in Swift with StoreKit 2 in-app purchases. I handled it from system design through release.

- Found and fixed a production bug by tracing it to Apple's 50-token platform limit.

**▶ [View CEILR on the App Store](https://apps.apple.com/us/app/ceilr/id6797726505)**

**Tools:** Swift, StoreKit 2

---

## Skills

**Languages:** JavaScript, Python, Swift, SQL, HTML/CSS, Java, C++
**Integrations:** n8n, REST APIs, webhooks, Stripe, StoreKit 2, OpenAI, ElevenLabs, Google Veo, FFmpeg
**Cloud & tools:** AWS, GCP, Git/GitHub, CI/CD

**Education:** BS, Computer Science, California State University San Marcos (2025)
