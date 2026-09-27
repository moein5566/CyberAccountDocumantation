# خطای قفل سخت‌افزاری Sentinel - تنظیمات سرور و تک‌کاربر

## هدف
این راهنما برای عیب‌یابی خطاهای مربوط به قفل سخت‌افزاری `Sentinel` در نرم‌افزار `حسابگر` استفاده می‌شود.

---

## مراحل عیب‌یابی

### ۱. اطمینان از اتصال فیزیکی قفل
- کلیدهای `Win + R` را بزن و `devmgmt.msc` را اجرا کن.
- مسیر زیر را طی کن:
  `Device Manager > Universal Serial Bus controllers > SafeNet Sentinel Dual Hardware Key`
- اگر قفل متصل باشد، باید در این لیست قابل مشاهده باشد.

### ۲. اطمینان از نصب بودن درایور
- کلیدهای `Win + R` را بزن و `services.msc` را اجرا کن.
- در لیست سرویس‌ها، باید `درایورهای قفل Sentinel` قابل مشاهده باشند.

> اگر درایور نصب نیست، از لینک زیر دانلود کن:  
> `https://www.shygunsys.net/wp-content/uploads/downloads/LCKDRV.rar`

> اگر قفل متصل و درایور نصب باشد، **چراغ قفل روشن** می‌شود.

### ۳. غیرفعال کردن Firewall
- `Control Panel > Windows Defender Firewall > Turn Windows Defender Firewall on or off`.
- گزینه‌های `Public Network`، `Private Network` و `Domain Network` را غیرفعال کن.

### ۴. بررسی تنظیمات قفل در برنامه

#### الف) بررسی فایل `prgsetting.ini`
- روی آیکون برنامه در `Desktop` راست‌کلیک کن > `Open File Location`.
- فایل `prgsetting.ini` را با `Notepad` باز کن.
- خط دوم باید: `ProviderName=Sentinel` باشد.
- خط سوم: بعد از `Cyberacc`، نسخه برنامه درج شده است.
  - وجود `i` = نسخه **صنعتی**
  - وجود `2L` = نسخه **دو زبانه**
  - نبود موارد بالا = نسخه **بازرگانی** و **تک‌زبانه**

#### ب) بررسی فایل `sntlconfig.xml`
- در محل نصب برنامه، فایل `sntlconfig.xml` را با `Notepad` باز کن.
- بین دو عبارت `AccessMode`، باید `IP` سیستم **سرور** نوشته شده باشد.

> اگر فایل `sntlconfig.xml` وجود نداشت، از `DVD` برنامه، مسیر `Extra > Prgsetting` را باز کن و فایل را در محل نصب برنامه کپی کن.