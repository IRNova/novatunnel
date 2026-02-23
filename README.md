<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/vazirmatn@33.0.3/font/css/vazirmatn.css">
<style>
body {
    font-family: 'Vazirmatn', sans-serif !important;
    direction: rtl;
}
</style>

# 🚀 edgetunnel 2.0
![后台页面](./img.png)

[![Stars](https://img.shields.io/github/stars/cmliu/edgetunnel?style=flat-square&logo=github)](https://github.com/cmliu/edgetunnel/stargazers)
[![Forks](https://img.shields.io/github/forks/cmliu/edgetunnel?style=flat-square&logo=github)](https://github.com/cmliu/edgetunnel/network/members)
[![License](https://img.shields.io/github/license/cmliu/edgetunnel?style=flat-square)](https://github.com/cmliu/edgetunnel/blob/main/LICENSE)
[![Telegram](https://img.shields.io/badge/Telegram-Group-blue?style=flat-square&logo=telegram)](https://t.me/CMLiussss)
[![YouTube](https://img.shields.io/badge/YouTube-Channel-red?style=flat-square&logo=youtube)](https://www.youtube.com/watch?v=LeT4jQUh8ok)
[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/cmliu/edgetunnel)
---

## 📖 معرفی پروژه

**edgetunnel** یک راه‌حل تونل رمزگشایی لبه (Edge Computing) بر پایه پلتفرم CF Workers/Pages است. این ابزار قادر است ترافیک شبکه را به طور کارآمد پردازش کند و پنل مدیریت قدرتمندی با قابلیت پیکربندی انعطاف‌پذیر گره‌ها ارائه دهد.

- 🖥️ **دمو سایت**：[https://EDT-Pages.github.io/admin](https://EDT-Pages.github.io/admin)

### ✨ ویژگی‌های اصلی

- 🛡️ **پشتیبانی از پروتکل**: پشتیبانی از پروتکل‌های اصلی مانند VLESS و Trojan با یکپارچه‌سازی عمیق انتقال رمزگذاری شده.
- 📊 **پنل مدیریت**: پنل پشتیبانی بصری داخلی با پشتیبانی از تغییر پیکربندی بلادرنگ، مشاهده لاگ‌ها و آمار ترافیک.
- 🛠️ **استقرار انعطاف‌پذیر**: سازگاری کامل با CF Workers و CF Pages (GitHub / آپلود).
- 🔄 **سیستم اشتراک**: تولید خودکار اشتراک و تبدیل ابهام‌زدایی داخلی، سازگار با کلاینت‌های اصلی (Clash, Sing-box, Surge و غیره).
- ⚡ **شتاب عملکرد**: پشتیبانی از ProxyIP سفارشی، پروکسی زنجیره‌ای SOCKS5/HTTP و API‌های بهینه‌سازی شده برای کاهش تاخیر شبکه.
- 🌐 **سازگاری با چندین دستگاه**: سازگاری کامل با Windows, Android, iOS, MacOS و انواع فرم‌ورهای روتر نرم‌افزاری.

---

## 💡 استقرار سریع
>[!TIP]
> 📖 **آموزش تصویری جامع**：[راهنمای استقرار edgetunnel](https://cmliussss.com/p/edt2/)

>[!WARNING]
> ⚠️ **مشکل Error 1101**：[ویدیوی آموزشی](https://www.youtube.com/watch?v=r4uVTEJptdE)

### ⚙️ استقرار Workers

<details>
<summary><code><strong>« آموزش متنی استقرار Workers »</strong></code></summary>

1. استقرار CF Worker:
   - یک Worker جدید در کنسول CF Worker ایجاد کنید.
   - محتوای [worker.js](https://github.com/cmliu/edgetunnel/blob/main/_worker.js) را در ویرایشگر Worker کپی کنید.
   - در تب `تنظیمات` سمت چپ، `متغیرها` > `افزودن متغیر` را انتخاب کنید.
     نام متغیر را **ADMIN** و مقدار را رمز عبور مدیر خود قرار دهید، سپس `ذخیره` کنید.

2. اتصال فضای نام KV:
   - در تب `اتصال‌ها`، `افزودن اتصال +` > `فضای نام KV` > `افزودن اتصال` را انتخاب کنید، سپس یک فضای نام موجود را انتخاب کنید یا یک فضای نام جدید ایجاد کنید.
   - `نام متغیر` را **KV** قرار دهید، سپس `افزودن اتصال` را کلیک کنید.

3. اتصال دامنه سفارشی به Workers:
   - در تب `Triggers` کنسول Workers، در پایین `افزودن دامنه سفارشی` را کلیک کنید.
   - دامنه فرعی که به سرویس DNS CF منتقل کرده‌اید را وارد کنید، مثلاً:`vless.google.com` سپس `افزودن دامنه سفارشی` را کلیک کنید و منتظر فعال شدن گواهینامه بمانید.

4. دسترسی به پنل مدیریت:
   - به `https://vless.google.com/admin` بروید و رمز عبور مدیر را وارد کنید تا وارد پنل شوید.

</details>

### 🛠️ روش استقرار Pages آپلود **بهترین پیشنهاد!!!** [آموزش تصویری](https://cmliussss.com/p/edt2/)

<details>
<summary><code><strong>« آموزش متنی استقرار Pages آپلود »</strong></code></summary>

1. استقرار CF Pages:
   - فایل [main.zip](https://github.com/cmliu/edgetunnel/archive/refs/heads/main.zip) را دانلود کنید و حتماً به آن ستاره بدهید !!!
   - در کنسول CF Pages، `آپلود دارایی` را انتخاب کنید، سپس برای پروژه خود نامی انتخاب کنید و `ایجاد پروژه` را کلیک کنید، سپس فایل [main.zip](https://github.com/cmliu/edgetunnel/archive/refs/heads/main.zip) دانلود شده را آپلود کنید و `استقرار سایت` را کلیک کنید.
   - پس از اتمام استقرار، `ادامه پردازش سایت` را کلیک کنید، سپس `تنظییمات` > `متغیرهای محیطی` > **ساخت** را برای تعریف متغیر برای محیط تولید انتخاب کنید > `افزودن متغیر`.
     نام متغیر را **ADMIN** و مقدار را رمز عبور مدیر خود قرار دهید، سپس `ذخیره` را کلیک کنید.
   - به تب `استقرار` برگردید، در پایین سمت راست `ایجاد استقرار جدید` را کلیک کنید، سپس فایل [main.zip](https://github.com/cmliu/edgetunnel/archive/refs/heads/main.zip) را دوباره آپلود کنید و `ذخیره و استقرار` را کلیک کنید.

2. اتصال فضای نام KV:
   - در تب `تنظییمات`، `اتصال‌ها` > `+ افزودن` > `فضای نام KV` را انتخاب کنید، سپس یک فضای نام موجود را انتخاب کنید یا یک فضای نام جدید ایجاد کنید.
   - `نام متغیر` را **KV** قرار دهید، سپس `ذخیره` را کلیک کنید و استقرار را مجدداً امتحان کنید.

3. اتصال دامنه سفارشی CNAME به Pages: [آموزش ویدیویی](https://www.youtube.com/watch?v=LeT4jQUh8ok&t=851s)
   - در تب `دامنه‌های سفارشی` کنسول Pages، در پایین `تنظیم دامنه سفارشی` را کلیک کنید.
   - دامنه فرعی سفارشی خود را وارد کنید، توجه داشته باشید که از دامنه ریشه استفاده نکنید، مثلاً:
     اگر دامنه اختصاص داده شده به شما `fuck.cloudns.biz` است، سپس دامنه سفارشی را به صورت `lizi.fuck.cloudns.biz` وارد کنید.
   - طبق الزامات CF، به ارائه دهنده خدمات DNS دامنه خود برگردید، رکورد CNAME را برای دامنه سفارشی `lizi` به صورت `edgetunnel.pages.dev` اضافه کنید، سپس `فعال‌سازی دامنه` را کلیک کنید.
   
4. دسترسی به پنل مدیریت:
   - به `https://lizi.fuck.cloudns.biz/admin` بروید و رمز عبور مدیر را وارد کنید تا وارد پنل شوید.

</details>

### 🛠️ روش استقرار Pages + GitHub

<details>
<summary><code><strong>« آموزش متنی استقرار Pages + GitHub »</strong></code></summary>

1. استقرار CF Pages:
   - ابتدا این پروژه را در GitHub Fork کنید و حتماً به آن ستاره بدهید !!!
   - در کنسول CF Pages، `اتصال به Git` را انتخاب کنید، سپس پروژه `edgetunnel` را انتخاب کنید و `شروع تنظییمات` را کلیک کنید.
   - در پایین صفحه `تنظیم ساخت و استقرار`، `متغیرهای محیطی (پیشرفته)` را انتخاب کنید و `افزودن متغیر` را کلیک کنید.
     نام متغیر را **ADMIN** و مقدار را رمز عبور مدیر خود قرار دهید، سپس `ذخیره و استقرار` را کلیک کنید.

2. اتصال فضای نام KV:
   - در تب `تنظییمات`، `اتصال‌ها` > `+ افزودن` > `فضای نام KV` را انتخاب کنید، سپس یک فضای نام موجود را انتخاب کنید یا یک فضای نام جدید ایجاد کنید.
   - `نام متغیر` را **KV** قرار دهید، سپس `ذخیره` را کلیک کنید و استقرار را مجدداً امتحان کنید.

3. اتصال دامنه سفارشی CNAME به Pages: [آموزش ویدیویی](https://www.youtube.com/watch?v=LeT4jQUh8ok&t=851s)
   - در تب `دامنه‌های سفارشی` کنسول Pages، در پایین `تنظیم دامنه سفارشی` را کلیک کنید.
   - دامنه فرعی سفارشی خود را وارد کنید، توجه داشته باشید که از دامنه ریشه استفاده نکنید، مثلاً:
     اگر دامنه اختصاص داده شده به شما `fuck.cloudns.biz` است، سپس دامنه سفارشی را به صورت `lizi.fuck.cloudns.biz` وارد کنید.
   - طبق الزامات CF، به ارائه دهنده خدمات DNS دامنه خود برگردید، رکورد CNAME را برای دامنه سفارشی `lizi` به صورت `edgetunnel.pages.dev` اضافه کنید، سپس `فعال‌سازی دامنه` را کلیک کنید.

4. دسترسی به پنل مدیریت:
   - به `https://lizi.fuck.cloudns.biz/admin` بروید و رمز عبور مدیر را وارد کنید تا وارد پنل شوید.

</details>

---

## 🔑 توضیحات متغیرهای محیطی

| نام متغیر | الزامی | مثال | توضیحات تفصیلی |
| :--- | :---: | :--- | :--- |
| **ADMIN** | ✅ | `123456` | رمز عبور پنل مدیریت |
| **KEY** | ❌ | `CMLiussss` | کلید مسیر اشتراک سریع، با دسترسی به `/CMLiussss` می‌توانید سریعاً گره‌ها را دریافت کنید |
| **UUID** | ❌ | `90cd4a77-141a-43c9-991b-08263cfe9c10` | ثابت کردن اجباری UUID، فقط فرمت استاندارد **UUIDv4** پشتیبانی می‌شود |
| ~~HOST~~ | ❌ | `edt.pages.dev` | ~~ثابت کردن اجباری دامنه~~قابل تنظیم از طریق پنل |
| ~~PATH~~ | ❌ | `/` | ~~ثابت کردن اجباری مسیر~~قابل تنظیم از طریق پنل |
| **PROXYIP** | ❌ | `proxyip.cmliussss.net:443` | IP پروکسی معکوس سفارشی سراسری |
| **URL** | ❌ | `https://cloudflare-error-page-3th.pages.dev` | آدرس پیش‌فرض صفحه اصلی (می‌توانید URL صفحه وب یا `1101` را وارد کنید) |
| **GO2SOCKS5** | ❌ | `blog.cmliussss.com`,`*.ip111.cn`,`*google.com` | لیست اجباری عبور از SOCKS5 (`*` به معنای سراسری، دامنه‌ها با کاما جدا می‌شوند) |

---

## 🔧 ترفندهای پیشرفته

این ابزار از تغییر پویای طرح پروکسی زیرین از طریق **مسیر PATH** پشتیبانی می‌کند:

- تعیین `PROXYIP` نمونه
   ```url
   /proxyip=proxyip.cmliussss.net
   /?proxyip=proxyip.cmliussss.net
   /proxyip.cmliussss.net (فقط برای دامنه‌هایی که با 'proxyip.' شروع می‌شوند)
   ```

- تعیین `SOCKS5` نمونه
   ```url
   /socks5=user:password@127.0.0.1:1080
   /?socks5=user:password@127.0.0.1:1080
   /socks://dXNlcjpwYXNzd29yZA==@127.0.0.1:1080 (فعال‌سازی پیش‌فرض SOCKS5 سراسری)
   /socks5://user:password@127.0.0.1:1080 (فعال‌سازی پیش‌فرض SOCKS5 سراسری)
   ```

- تعیین `HTTP Proxy` نمونه
   ```url
   /http=user:password@127.0.0.1:1080
   /http://user:password@127.0.0.1:8080 (فعال‌سازی پیش‌فرض SOCKS5 سراسری)
   ```

---

## 💻 سازگاری کلاینت‌ها

| پلتفرم | کلاینت پیشنهادی | توضیحات |
| :--- | :--- | :--- |
| **Windows** | [v2rayN](https://github.com/2dust/v2rayN), [FlClash](https://github.com/chen08209/FlClash), [mihomo-party](https://github.com/mihomo-party-org/mihomo-party), [Clash Verge Rev](https://github.com/ClashVerge/ClashVerge-Rev) | پشتیبانی کامل |
| **Android** | [ClashMetaForAndroid](https://github.com/chen08209/ClashMetaForAndroid), [FlClash](https://github.com/chen08209/FlClash), [v2rayNG](https://github.com/2dust/v2rayNG) | پیشنهاد استفاده از هسته Meta |
| **iOS** | [Surge](https://surgeapp.com/), [Shadowrocket](https://shadowrocket.com/), [Stash](https://stashapp.com/) | سازگاری کامل |
| **MacOS** | [FlClash](https://github.com/chen08209/FlClash), [mihomo-party](https://github.com/mihomo-party-org/mihomo-party), [Clash Verge Rev](https://github.com/ClashVerge/ClashVerge-Rev), [Surge](https://surgeapp.com/) | سازگاری کامل M1/M2 |

---

## ⭐ محبوبیت پروژه

[![Stargazers over time](https://starchart.cc/cmliu/edgetunnel.svg?variant=adaptive)](https://starchart.cc/cmliu/edgetunnel)

---

## 🙏 تشکر ویژه
### 💖 حمایت مالی - ارائه سرور ابری برای حفظ [سرویس تبدیل اشتراک](https://sub.cmliussss.net/)
- [NodeLoc](https://www.nodeloc.com/)
- [Alice](https://url.cmliussss.com/alice)
- [EasyLinks](https://www.vmrack.net?ref_code=5Zk7eNhbgL7)
- [ZMTO(VTEXS)](https://zmto.com/?affid=1532)

### 🛠️引用 کد منبع باز
- [zizifn/edgetunnel](https://github.com/zizifn/edgetunnel)
- [3Kmfi6HP/EDtunnel](https://github.com/6Kmfi6HP/EDtunnel)
- [SHIJS1999/cloudflare-worker-vless-ip](https://github.com/SHIJS1999/cloudflare-worker-vless-ip)
- [Stanley-baby](https://github.com/Stanley-baby)
- [ACL4SSR](https://github.com/ACL4SSR/ACL4SSR/tree/master/Clash/config)
- [股神](https://t.me/CF_NAT/38889)
- [Workers/Pages Metrics](https://t.me/zhetengsha/3382)
- [白嫖哥](https://t.me/bestcfipas)
- [Mingyu](https://github.com/ymyuuu/workers-vless)
- [Alexandre Kojève](https://t.me/Enkelte_notif/784)
- [eooce](https://github.com/eooce/Cloudflare-proxy)
- [Sukka](https://ip.skk.moe/)

---

## ⚠️ سلب مسئولیت

1. این پروژه ("edgetunnel") فقط برای **اهداف آموزش، تحقیقات علمی و تست امنیت شخصی** است.
2. کاربران هنگام دانلود یا استفاده از کد این پروژه، باید قوانین و مقررات منطقه خود را رعایت کنند.
3. نویسنده **cmliu** هیچ مسئولیتی در قبال سوء استفاده از کد این پروژه ندارد.
4. این پروژه هیچ مسئولیتی در قبال آسیب مستقیم یا غیرمستقیم ناشی از استفاده از کد ندارد.
5. پیشنهاد می‌شود ظرف 24 ساعت پس از اتمام تست، استقرار مرتبط با این پروژه را حذف کنید.

---

**اگر فکر می‌کنید این پروژه به شما کمک کرده است، لطفاً یک ستاره بدهید 🌟، این بزرگ‌ترین تشویق برای من است!**
