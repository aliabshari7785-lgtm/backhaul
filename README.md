# 🚇 Backhaul

ابزار تونل معکوس سبک و سریع برای دور زدن محدودیت‌های شبکه و NAT Traversal — مناسب برای سرورهای ایران و خارج.

> فورک شده از [WaffleNoodle/Zenith-Stash](https://github.com/WaffleNoodle/Zenith-Stash)

---

## ✨ ویژگی‌ها

- 🔁 **تونل معکوس** — اتصال از سرور ایران به سرور خارج بدون نیاز به IP عمومی
- ⚡ **سبک و سریع** — نوشته شده با Shell، بدون وابستگی سنگین
- 🖥️ **پشتیبانی از معماری‌های مختلف** — AMD64 و ARM64
- 🛡️ **مناسب برای دور زدن فیلترینگ** — کارکرد پایدار در شرایط محدودیت شبکه

---

## 📁 فایل‌ها

| فایل | توضیح |
|------|--------|
| `backhaul.sh` | اسکریپت اصلی راه‌اندازی و مدیریت تونل |
| `backhaul_amd64.tar.gz` | باینری آماده برای سیستم‌های x86_64 |
| `backhaul_arm64.tar.gz` | باینری آماده برای سیستم‌های ARM64 |

---

## 🚀 نصب سریع

فقط یک دستور کافیه:

```bash
bash <(curl -Ls --ipv4 https://raw.githubusercontent.com/aliabshari7785-lgtm/backhaul/refs/heads/main/backhaul.sh)
```

---

## ⚙️ پیکربندی

### سرور (خارج)

```bash
./backhaul -mode server -port 3080 -token YOUR_SECRET_TOKEN
```

### کلاینت (ایران)

```bash
./backhaul -mode client -server YOUR_FOREIGN_IP:3080 -token YOUR_SECRET_TOKEN -local 0.0.0.0:443
```

> **توجه:** مقدار `YOUR_SECRET_TOKEN` را با یک رشته تصادفی و امن جایگزین کنید.

---

## 🗂️ معماری کلی

```
[ کاربر ] ──► [ سرور ایران (کلاینت) ] ══► [ سرور خارج ] ──► [ اینترنت آزاد ]
```

- **سرور ایران** نقش کلاینت تونل را دارد و به سرور خارج وصل می‌شود
- **سرور خارج** نقش سرور تونل را دارد و ترافیک را به اینترنت می‌رساند

---

## 📋 پیش‌نیازها

- سیستم‌عامل لینوکس (Ubuntu / Debian / CentOS)
- دسترسی root یا sudo
- دو سرور: یکی در ایران، یکی در خارج

---

## 🤝 مشارکت

Pull Request و Issue خوشایند است! لطفاً قبل از ارسال PR یک Issue باز کنید.

---

## 📄 لایسنس

این پروژه تحت شرایط لایسنس مخزن اصلی منتشر شده است. برای جزئیات بیشتر به [WaffleNoodle/Zenith-Stash](https://github.com/WaffleNoodle/Zenith-Stash) مراجعه کنید.
