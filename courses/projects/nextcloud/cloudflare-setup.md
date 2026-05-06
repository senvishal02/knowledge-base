# 🌍 Cloudflare Setup (Account + Domain)

If you already have a Cloudflare account and your domain is added, you can skip this section.

---

## 🧾 Step 1: Create Cloudflare Account

1. Go to 👉 https://dash.cloudflare.com/sign-up  
2. Enter:
   - Email address
   - Password  
3. Click **Sign Up**
4. Verify your email address

---

## 🌐 Step 2: Add Your Domain

1. Login to Cloudflare Dashboard  
2. Click **"Add a Site"**  
3. Enter your domain name  
   - Example: `yourdomain.com`  
4. Click **Continue**

---

## 💳 Step 3: Select Plan

- Choose **Free Plan** (sufficient for this setup)
- Click **Continue**

---

## 🔍 Step 4: Review DNS Records

Cloudflare will scan existing DNS records.

- If you already have a website → records will appear automatically  
- If not → you can add records later  

👉 Click **Continue**

---

## 🔁 Step 5: Update Nameservers (Important)

Cloudflare will provide **2 nameservers**, like:

- ns1.cloudflare.com
- ns2.cloudflare.com


### Now go to your domain registrar:

Examples:
- GoDaddy
- Namecheap
- Google Domains

### Steps:

1. Login to your domain provider
2. Go to **DNS / Nameserver settings**
3. Replace existing nameservers with Cloudflare nameservers
4. Save changes

---

## ⏳ Step 6: Wait for Activation

- DNS propagation may take **5 minutes to 24 hours**
- Cloudflare status will change to:

✅ **Active**

---

## ✅ Step 7: Verify Domain

Once active:

- Go to **Cloudflare Dashboard → DNS**
- You should see your domain listed

---

## ⚠️ Important Notes

- Do NOT skip nameserver update (most common mistake)
- Keep Cloudflare proxy **enabled (orange cloud ☁️)**
- Free plan is enough for Cloudflare Tunnel

---

## 🎯 What’s Next?

After domain setup, proceed to:

👉 [**Cloudflare Tunnel Setup**](index.md)