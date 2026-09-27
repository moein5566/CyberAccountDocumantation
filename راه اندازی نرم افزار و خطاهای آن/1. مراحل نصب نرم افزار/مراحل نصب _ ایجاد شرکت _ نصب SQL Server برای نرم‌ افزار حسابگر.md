# مراحل نصب _ ایجاد شرکت _ نصب SQL Server برای نرم‌ افزار حسابگر

## هدف
این راهنما برای نصب و راه‌ اندازی `SQL Server` جهت استفاده از نرم‌ افزار `حسابگر` شایگان سیستم استفاده میشود.

---

## نصب SQL Server

### پیش‌ نیاز ها
- نسخه‌ های پشتیبانی‌ شده: `SQL Server 2008` تا `2019`.
- فایل نصب در `DVD` برنامه، مسیر `ADDIN > SQL` موجود است.
- بر اساس ویندوز خود (۳۲ یا ۶۴ بیت)، پوشه `x86` یا `x64` را انتخاب کن.

### مراحل نصب
۱. فایل `SETUP.exe` را اجرا کن.

۲. در پنل سمت چپ، گزینه `Installation` را انتخاب کن.

۳. روی `New SQL Server stand-alone installation` کلیک کن.

۴. اگر پیغام وجود نسخه‌ های دیگر ظاهر شد، گزینه اول را انتخاب کن.

۵. تیک `I accept the license terms` را بزن و `Next` کن.

۶. در بخش `Feature Selection`، سه گزینه زیر را حتماً انتخاب کن:
   - `Database Engine Services`
   - `SQL Server Replication`
   - `Client Tools Connectivity`

۷. در بخش `Instance Configuration`:
   - گزینه `Named Instance` را انتخاب کن.
   - نام پیشنهادی: `SHYGUN` + نسخه (مثلاً `SHYGUN2014`).
   - `Next` بزن.

۸. در بخش `Server Configuration`:
   - `Startup Type` را برای هر دو سرویس روی `Automatic` تنظیم کن.
   - `Next` بزن.

۹. در بخش `Database Engine Configuration`:
   - گزینه `Mixed Mode` را انتخاب کن.
   - رمز عبور برای کاربر `sa` وارد کن (پیشنهاد: `123@123` یا `123@abc`).
   - `Next` بزن.

۱۰. در صفحه بعد، روی `Next` کلیک کن تا نصب شروع شود.

۱۱. پس از اتمام، روی `Close` کلیک کن.

---

## راه‌ اندازی دستی SQL Server
اگر سرویس به‌ صورت خودکار شروع نشد:
- `This PC > Manage > Services and Applications > SQL Server Configuration Manager`.
- در بخش `SQL Server Services`:
  - روی `SQL Server (InstanceName)` راست‌ کلیک کن و `Start` را بزن.
  - روی `SQL Server Browser` راست‌ کلیک کن و `Start` را بزن.

---

## فعال کردن TCP/IP (برای محیط شبکه)
- `SQL Server Configuration Manager > SQL Server Network Configuration`.
- پروتکل مربوط به `Instance` خود را انتخاب کن.
- روی `TCP/IP` راست‌ کلیک کن و `Enable` را بزن.
- در پنجره باز شده، تمام گزینه‌ ها را روی `Yes` تنظیم کن و `OK` بزن.
- در بخش `SQL Server Services`:
  - روی `SQL Server (InstanceName)` راست‌ کلیک کن > `Stop`.
  - دوباره راست‌ کلیک کن > `Start`.

