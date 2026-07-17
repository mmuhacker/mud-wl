<div align="center">

# 📋 Whois Lookup — أداة معلومات تسجيل النطاق

**تعمل على نظام Kali Linux و تطبيق Termux**

꧁ঔৣ☬ Muhannad Daher ☬ঔৣ꧂

---
[![by](https://img.shields.io/badge/mmuhacker-%EF%BA%97%EF%BB%84%EF%BB%AE%EF%BB%B3%EF%BA%AE-blue?style=for-the-badge&logo=github)](https://github.com/mmuhacker)<br>
![Version](https://img.shields.io/badge/1.0-%EF%BA%8D%EF%BB%B9%EF%BA%BB%EF%BA%AA%EF%BA%8D%EF%BA%AE-blue?style=for-the-badge)<br>
![Platform](https://img.shields.io/badge/%EF%BB%9B%EF%BA%8E%EF%BB%9F%EF%BB%B2%20%EF%BB%9F%EF%BB%B4%EF%BB%A8%EF%BB%9C%EF%BA%B2-%EF%BA%8D%EF%BB%9F%EF%BA%92%EF%BB%B4%EF%BA%8C%EF%BA%94-green?style=for-the-badge&logo=kalilinux)<br>
![Platform](https://img.shields.io/badge/%EF%BA%84%EF%BB%A7%EF%BA%AA%EF%BA%AE%EF%BB%AE%EF%BB%B3%EF%BA%AA-%EF%BA%8D%EF%BB%9F%EF%BA%92%EF%BB%B4%EF%BA%8C%EF%BA%94-green?style=for-the-badge&logo=android)<br>
![Python](https://img.shields.io/badge/3x-%EF%BA%91%EF%BA%8E%EF%BB%B3%EF%BA%9C%EF%BB%AE%EF%BB%A6-blue?style=for-the-badge&logo=python)<br>
![License](https://img.shields.io/badge/MIT-%EF%BA%8D%EF%BB%9F%EF%BA%98%EF%BA%AE%EF%BA%A7%EF%BB%B4%EF%BA%BA-red?style=for-the-badge)<br>
![Status](https://img.shields.io/badge/%EF%BB%A7%EF%BA%B8%EF%BB%82-%EF%BA%8D%EF%BB%9F%EF%BA%A4%EF%BA%8E%EF%BB%9F%EF%BA%94-blue?style=for-the-badge)
---

**المحتويات:**

</div>

- [الوصف](#الوصف)
- [المميزات](#المميزات)
- **التثبيت**
  - [التثبيت على Termux](#تيرمكس)
  - [التثبيت على توزيعات لينكس](#لينكس)
- [تحديث الأداة](#تحديث)
- [التشغيل](#التشغيل)
- [طريقة الاستخدام](#طريقة-الاستخدام)
- [مثال](#مثال)
- [المتطلبات](#المتطلبات)
- [إخلاء المسؤولية](#إخلاء-المسؤولية)
- [المطوّر](#المطوّر)
- [الرخصة](#-الرخصة)

---

<div align="center" id="الوصف">

## 📌 الوصف

</div>

أداة للحصول على معلومات تسجيل أي نطاق أو عنوان IP عبر بروتوكول Whois، مكتوبة بلغة Python وتعمل على Termux و Kali Linux. تعرض تفاصيل المسجِّل وتواريخ التسجيل والانتهاء وخوادم الأسماء.

---

<div align="center" id="المميزات">

## ✨ المميزات

</div>

- 📋 عرض معلومات تسجيل النطاق كاملة
- 📅 تواريخ التسجيل والتحديث والانتهاء
- 🌐 خوادم الأسماء ومزود التسجيل
- 🔍 استعلام Whois لعناوين IP
- 🗒️ خيار عرض النص الخام كاملاً
- 🌍 دعم امتدادات عربية (sa, ae, jo, eg)
- 🌍 واجهة عربية بالكامل

---

<div align="center" id="تيرمكس">

## ⚙️ التثبيت

### Termux

</div>

**الخطوة 1 — تحديث النظام**
```bash
pkg update && pkg upgrade -y
```

**الخطوة 2 — تثبيت المتطلبات** *(لمرة واحدة فقط)*
```bash
pkg install python tor curl fontconfig rust -y
```
```bash
pip install requests pysocks arabic-reshaper
pip install python-bidi==0.4.2
```

**الخطوة 3 — تثبيت الخط العربي** *(لمرة واحدة فقط)*
```bash
curl -L "https://fonts.gstatic.com/s/notonaskharabic/v33/RrQ5bpV-9Dd1b1OAGA6M9PkyDuVBePeKNaxcsss0Y7bwvc-VaA.ttf" -o ~/.termux/font.ttf
termux-reload-settings
```

**الخطوة 4 — تنزيل الأداة**
```bash
curl -o $PREFIX/bin/mud_wl.py https://raw.githubusercontent.com/mmuhacker/mud-wl/main/mud_wl.py
```

**الخطوة 5 — إعطاء صلاحية التشغيل**
```bash
chmod +x $PREFIX/bin/mud_wl.py
```

**الخطوة 6 — إنشاء رابط الاختصار**
```bash
ln -sf $PREFIX/bin/mud_wl.py $PREFIX/bin/wl
```

**⚡ أو قم بكل شيء بأمر واحد مجمّع**
```bash
pkg update && pkg upgrade -y && pkg install python tor curl fontconfig rust -y && pip install requests pysocks arabic-reshaper && pip install python-bidi==0.4.2 && curl -L "https://fonts.gstatic.com/s/notonaskharabic/v33/RrQ5bpV-9Dd1b1OAGA6M9PkyDuVBePeKNaxcsss0Y7bwvc-VaA.ttf" -o ~/.termux/font.ttf && termux-reload-settings && curl -o $PREFIX/bin/mud_wl.py https://raw.githubusercontent.com/mmuhacker/mud-wl/main/mud_wl.py && chmod +x $PREFIX/bin/mud_wl.py && ln -sf $PREFIX/bin/mud_wl.py $PREFIX/bin/wl && wl
```

---

<div align="center" id="لينكس">

### Kali Linux

</div>

**الخطوة 1 — تحديث النظام**
```bash
sudo apt update && sudo apt upgrade -y
```

**الخطوة 2 — تثبيت المتطلبات** *(لمرة واحدة فقط)*
```bash
pip install requests arabic-reshaper python-bidi==0.4.2 --break-system-packages
```

**الخطوة 3 — تنزيل الأداة**
```bash
sudo curl -o /usr/local/bin/mud_wl.py https://raw.githubusercontent.com/mmuhacker/mud-wl/main/mud_wl.py
```

**الخطوة 4 — إعطاء صلاحية التشغيل**
```bash
sudo chmod +x /usr/local/bin/mud_wl.py
```

**الخطوة 5 — إنشاء رابط الاختصار**
```bash
sudo ln -sf /usr/local/bin/mud_wl.py /usr/local/bin/wl
```

**⚡ أو قم بكل شيء بأمر واحد مجمّع**
```bash
sudo apt update && sudo apt upgrade -y && pip install requests arabic-reshaper python-bidi==0.4.2 --break-system-packages && sudo curl -o /usr/local/bin/mud_wl.py https://raw.githubusercontent.com/mmuhacker/mud-wl/main/mud_wl.py && sudo chmod +x /usr/local/bin/mud_wl.py && sudo ln -sf /usr/local/bin/mud_wl.py /usr/local/bin/wl && wl
```

---

<div align="center" id="التشغيل">

## 🚀 التشغيل

</div>

```bash
wl
```

**أو بالأمر الكامل**

```bash
mud_wl.py
```

---


<div align="center" id="تحديث">
  
## تحديث الأداة

***على أندرويد Termux***

```bash
curl -o $PREFIX/bin/mud_wl.py https://raw.githubusercontent.com/mmuhacker/mud-wl/main/mud_wl.py
```

***على توزيعات Linux***

```bash
sudo curl -o /usr/local/bin/mud_wl.py https://raw.githubusercontent.com/mmuhacker/mud-wl/main/mud_wl.py
```
  
</div>

---

<div align="center" id="طريقة-الاستخدام">

## 📖 طريقة الاستخدام


| الوضع | الوصف |
|-------|-------|
| `1` استعلام نطاق | معلومات تسجيل أي نطاق |
| `2` استعلام IP | معلومات Whois لعنوان IP |

</div>

---

<div align="center" id="مثال">

## 💡 مثال

</div>

اختيارك: 1

أدخل النطاق: google.com
<div align="center">
  
  اسم النطاق          GOOGLE.COM
  
  المسجِّل             MarkMonitor Inc.
  
  تاريخ التسجيل       1997-09-15
  
  تاريخ الانتهاء      2028-09-14
  
  آخر تحديث           2019-09-09
  
  خوادم الأسماء       ns1.google.com
  
  حالة النطاق         clientDeleteProhibited
  
  DNSSEC              unsigned
  
</div>

---

<div align="center" id="المتطلبات">

## 🔧 المتطلبات


| المتطلب | الوصف |
|---------|-------|
| Python 3.6+ | لغة البرمجة |
| arabic-reshaper | دعم النص العربي |
| python-bidi | اتجاه النص العربي |
| curl | تنزيل الأداة |
| اتصال بالإنترنت | للاستعلام عن بيانات Whois |

</div>

> ⚠️ **ملاحظة:** بدون تثبيت `arabic-reshaper` و `python-bidi` سيظهر النص العربي معكوساً ومتقطعاً.

---

<div align="center" id="إخلاء-المسؤولية">

## ⚖️ إخلاء المسؤولية

</div>

هذه الأداة مخصصة **لأغراض تعليمية فقط**.
لا تستخدمها لأغراض غير مشروعة.

---

<div align="center" id="المطوّر">

## 👨‍💻 المطوّر

**Muhannad Daher**

[![GitHub](https://img.shields.io/badge/GitHub-mmuhacker-black?style=for-the-badge&logo=github)](https://github.com/mmuhacker)

---


## 📄 الرخصة
**MIT License — حر الاستخدام مع ذكر المصدر**

---
</div>

- أداة معلومات تسجيل النطاق
- البيئة: Termux (Android) / Kali Linux
- الإصدار: v1.0



---
<div align="center">

***Madarik Tools — صُنع بالعربية***

⭐ **إذا أعجبتك الأداة، لا تنسَ النجمة!** ⭐
</div>
