# پنل Nova-Vless

> ⚡ پنل مدیریت VLESS برای Cloudflare Workers

<p align="center">
  <img src="https://img.shields.io/badge/Cloudflare-Workers-F38020?style=for-the-badge&logo=cloudflare" alt="Cloudflare Workers">
  <img src="https://img.shields.io/badge/VLESS-Protocol-blue?style=for-the-badge">
  <img src="https://img.shields.io/badge/TLS-ECH-green?style=for-the-badge">
</p>

---

## ✨ امکانات

### 🔐 پروتکل‌های پشتیبانی شده
- **VLESS** - پروتکل اصلی
- **Trojan** - پروتکل جایگزین

### 🌐 انواع اتصال
- **WebSocket** - استاندارد
- **HTTP/2** - سریع‌تر
- **HTTP/3 (gRPC)** - مدرن‌ترین

### 🔒 امنیت
- **TLS** - رمزنگاری
- **ECH** (Encrypted Client Hello) - پنهان‌سازی SNI
- **0-RTT** - اتصال سریع‌تر

### 📡 سیستم اشتراک
- اشتراک محلی با IP های تصادفی Cloudflare
- پشتیبانی از API های خارجی (SUB Generator)
- تبدیل خودکار به فرمت‌های مختلف
- پشتیبانی از: Clash, Sing-box, Surge, Quantumult, Loon

### 🖥️ پنل مدیریت
- تنظیمات کامل از طریق وب
- بهینه‌سازی آنلاین IP
- تنظیمات سفارشی IP

### 📱 امکانات اضافی
- **تلگرام** - اعلان‌ها و مدیریت
- **SOCKS5/HTTP Proxy** - پروکسی سفارشی
- **Anti-Proxy Fallback** - مکانیزم بازگشت

---

## 📋 متغیرهای محیطی (Environment Variables)

برای استقرار این پروژه، متغیرهای زیر را در Cloudflare Workers تنظیم کنید:

| متغیر | الزامی | توضیحات | مثال |
|--------|---------|----------|-------|
| `ADMIN` | ✅ | رمز عبور مدیر | `MySecurePassword123` |
| `KEY` | ✅ | کلید رمزنگاری | `YourSecretKey` |
| `UUID` | ❌ | UUID سفارشی (اختیاری) | `550e8400-e29b-41d4-a716-446655440000` |
| `HOST` | ❌ | دامنه هاست | `example.com` |
| `KV` | ❌ | Namespace برای KV | `nova-kv` |
| `PROXYIP` | ❌ | IP پروکسی | `proxy.example.com` |
| `GO2SOCKS5` | ❌ | لیست SOCKS5 | `socks5://user:pass@host:port` |
| `URL` | ❌ | صفحه فریب (Fake) | `nginx` یا دامنه |
| `ECH` | ❌ | فعال‌سازی ECH | `true` |

---

## 🚀 نحوه استقرار

### ۱. ایجاد Worker
1. به داشبورد Cloudflare بروید
2. یک Worker جدید ایجاد کنید
3. کد `nvless.js` را کپی کنید

### ۲. تنظیم متغیرها
در بخش Settings > Environment Variables:

```
ADMIN = رمز_عبور_شما
KV = namespace-name
```

### ۳. ایجاد KV Namespace
1. به Cloudflare Workers > KV بروید
2. یک Namespace جدید ایجاد کنید
3. نام آن را در متغیر `KV` وارد کنید

### ۴. اتصال Domain
1. یک Subdomain به Worker متصل کنید
2. یا از Routes استفاده کنید

---

## 📖 راهنمای استفاده


پارامترهای اضافی:
- `&target=clash` - فرمت Clash
- `&target=singbox` - فرمت Sing-box
- `&target=surge` - فرمت Surge
- `&target=mixed` - ترکیبی (پیش‌فرض)
- `&base64=true` - خروجی Base64
- `&sub=URL` - استفاده از API خارجی

### 👤 صفحه مدیریت

```
https://your-domain/login
```

پس از ورود:
- `/admin` - پنل تنظیمات
- `/admin/config.json` - تنظیمات JSON
- `/admin/ADD.txt` - IP های سفارشی
- `/admin/cf.json` - اطلاعات Cloudflare
- `/admin/log.json` - لاگ‌ها

### 📱 بهینه‌سازی آنلاین IP

1. وارد پنل مدیریت شوید
2. به بخش "بهینه‌سازی آنلاین" بروید
3. کتابخانه IP را انتخاب کنید
4. تست را اجرا کنید
5. بهترین IP ها را ذخیره کنید

---



## 🔧 تنظیمات پیشرفته

### ECH (Encrypted Client Hello)
برای فعال‌سازی ECH:
1. متغیر `ECH` را `true` تنظیم کنید
2. یک دامنه با DoH تنظیم کنید

### SOCKS5 Proxy
```
SOCKS5=username:password@host:port
```

### IP پروکسی سفارشی
در پنل admin > IP های سفارشی یا `ADD.txt`

---

## ⚡ تولید اشتراک بهینه

سیستم تولید اشتراک این پنل از **3 روش** مختلف پشتیبانی می‌کند:

### 🏠 روش ۱: حالت محلی (Local)
این روش پیش‌فرض است و IP های Cloudflare را از GitHub دریافت می‌کند:
- IP های رسمی Cloudflare (از IRNova/Tools)
- پشتیبانی از اپراتورهای  (CMCC, CU, CT)
- تولید تصادفی IP از رنج‌های موجود
- **نام نودها**: به صورت تصادفی با پیشوند `Nova-` و کد 5 کاراکتری

### 🔗 روش ۲: حالت API خارجی (SUB Generator)
استفاده از API های آماده برای دریافت اشتراک:
- می‌توانید هر SUB API معتبر را وارد کنید
- مثلاً: `https://subapi.example.com`
- سیستم به طور خودکار لینک‌ها را پردازش می‌کند
`

---

## ⚙️ اطلاعات پیکربندی جزئی

تنظیمات قابل تغییر در پنل:

| تنظیم | قابل تغییر | توضیحات |
|--------|-------------|----------|
| پروتکل | ✅ | VLESS / Trojan |
| نوع اتصال | ✅ | WebSocket / HTTP/2 / HTTP/3 |
| مسیر | ✅ | مسیر دلخواه |
| TLS | ✅ | فعال/غیرفعال |
| Fingerprint | ✅ | chrome, firefox, safari, etc |
| TLS Fragment | ✅ | اندازه و نوع |
| ECH | ✅ | فعال/غیرفعال |
| نام اشتراک | ✅ | متن دلخواه |
| تعداد IP | ✅ | 1-100 |
| پورت | ✅ | سفارشی |

---

## 🔐 Encrypted Client Hello (ECH)

### ❓ ECH چیست؟

**ECH (Encrypted Client Hello)** یک ویژگی جدید در پروتکل TLS است که اطلاعات حساس مانند SNI (نام سرور) را رمزنگاری می‌کند.

### ⚠️ مشکل چیست؟

در اتصالات معمولی WS + TLS:
- ✅ محتوای ارتباط رمزنگاری شده
- ❌ اما **SNI** (دامنه نود) به صورت plaintext ارسال می‌شود

این یعنی GFW می‌داند به کدام دامنه متصل شده‌اید، حتی اگر محتوا را نبیند.

### 💡 نقش ECH

ECH با رمزنگاری SNI این مشکل را حل می‌کند:
- ✅ GFW دیگر نمی‌تواند دامنه واقعی را ببیند
- ✅ دامنه نمایش داده شده: `cloudflare-ech.com` (یکپارچه)
- ✅ مسدودسازی دقیق دامنه غیرممکن می‌شود

### 📱 کلاینت‌های پشتیبان:
- v2rayN v7.17.0+
- v2rayNG v2.0.0+
- Clash.Meta (Mihomo)
- Sing-box

### 🌐 DNS های پشتیبانی شده:
- Cloudflare DoH
- Google DoH
- Ali DoH
- Tencent SM DoH
- و دیگر DoH ها...

---


## 🔄 پیکربندی تبدیل اشتراک

سیستم تبدیل اشتراک برای تبدیل لینک‌ها به فرمت‌های مختلف استفاده می‌شود:

### ⚙️ تنظیمات اصلی:

| تنظیم | توضیحات | پیش‌فرض |
|-------|---------|----------|
| **SUBAPI** | آدرس سرور تبدیل | SUBAPI.cmliussss.net |
| **SUBCONFIG** | فایل کانفیگ | ACL4SSR_Online_Mini_MultiMode_CF |
| **EMOJI** | افزودن شکلک | غیرفعال |

### 🌐 فرمت‌های پشتیبانی شده:
- **Clash** - برای کلاینت‌های Clash
- **Sing-box** - برای Sing-box
- **Surge** - برای Surge
- **Quantumult** - برای Quantumult
- **Loon** - برای Loon
- **Mixed** - ترکیبی (پیش‌فرض)




---

## 🙏 تشکر و قدردانی

- [IRNova/Tools](https://github.com/IRNova/Tools) - ابزارها و منابع IP
- [ACL4SSR](https://github.com/ACL4SSR) - کانفیگ Subconverter
- [ipverse](https://github.com/ipverse/asn-ip) - پایگاه داده ASN
- [Cloudflare](https://cloudflare.com) - زیرساخت Workers

---

## 📝 لایسنس

این پروژه برای استفاده شخصی و آموزشی است.

---

## 📞 ارتباط

<p align="center">
  <a href="https://github.com/IRNova/Nova-Proxy">
    <img src="https://img.shields.io/badge/GitHub-گیتهاب-0ea5e9?style=for-the-badge&logo=github" alt="GitHub">
  </a>
  <a href="https://t.me/irnova_proxy">
    <img src="https://img.shields.io/badge/Telegram-تلگرام-0ea5e9?style=for-the-badge&logo=telegram" alt="Telegram Channel">
  </a>
</p>

<p align="center">
  برای دیدن آخرین تغییرات و پروژه‌های بیشتر حتماً عضو کانال ما شوید
</p>

---

<p align="center">
  <strong>نسخه 1.0.0 - در حال توسعه | با ❤️ برای جامعه ایران</strong>
</p>
