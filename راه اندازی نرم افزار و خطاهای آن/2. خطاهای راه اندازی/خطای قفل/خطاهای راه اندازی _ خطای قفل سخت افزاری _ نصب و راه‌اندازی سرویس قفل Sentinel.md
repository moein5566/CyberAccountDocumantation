# خطاهای راه اندازی _ خطای قفل سخت افزاری _ نصب و راه‌اندازی سرویس قفل Sentinel

## هدف
این راهنما برای نصب درایور قفل سخت‌افزاری `Sentinel` جهت راه‌اندازی نرم‌افزار `حسابگر` استفاده می‌شود.

## مراحل نصب

### ۱. دریافت فایل نصب
- از وب‌سایت شایگان سیستم: `www.shygunsys.net > پشتیبانی > مرکز دانلود > درایورها > درایور قفل Sentinel`.
- یا از `DVD` نصب برنامه: مسیر `ADDIN > LCKDRV`.

### ۲. اجرای فایل نصب‌ کننده نرم افزار
- فایل `Setup.exe` را در پوشه `LCKDRV` اجرا کن.
- اگر خطای `This App Has Been Blocked For Your Protection` ظاهر شد، به بخش **پیوست** مراجعه کن.

### ۳. طی کردن مراحل نصب
- روی `Next` کلیک کن.
- گزینه `I accept the terms in the license agreement` را انتخاب کن و `Next` بزن.
- گزینه `Complete` را انتخاب کن و `Next` بزن.
- روی `Install` کلیک کن تا نصب انجام شود.
- در پنجره `Important Note`، روی `Yes` کلیک کن.
- در مرحله آخر، روی `Finish` کلیک کن.

> پس از نصب موفق، چراغ قفل سخت‌افزاری روشن می‌شود.

---

## پیوست: رفع خطای `This App Has Been Blocked For Your Protection`

### روش اول: تغییر Group Policy
1. کلیدهای `Win + R` را بزن و `gpedit.msc` را اجرا کن.
2. مسیر زیر را طی کن:
   `Computer Configuration > Windows Settings > Security Settings > Local Policies > Security Options`
3. گزینه `User Account Control: Run all administrators in Admin Approval Mode` را پیدا کن.
4. روی آن دابل‌ کلیک کن و گزینه `Disable` را انتخاب کن و `OK` بزن.
5. سیستم را `Restart` کن و دوباره نصب را اجرا کن.
6. اگر مشکل باقی ماند، روش دوم را انجام بده.

### روش دوم: تغییر رجیستری
1. کلیدهای `Win + R` را بزن و `regedit` را اجرا کن.
2. مسیر زیر را طی کن:
   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`
3. گزینه `EnableLUA` را پیدا کن.
4. روی آن دابل‌کلیک کن و مقدار `Value Data` را به `0` تغییر بده و `OK` بزن.
5. پیغام `Restart` ظاهر می‌شود، روی آن کلیک کن و `Restart Now` را بزن.
6. پس از راه‌اندازی مجدد، نصب درایور را انجام بده.