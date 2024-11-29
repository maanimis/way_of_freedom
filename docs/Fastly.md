# Fastly

## آموزش قرار دادن یک کانفیگ‌ رایگان یا شخصی پشت CDN سایت fastly و استفاده از دامنه fake برای کانفیگ

امیدوارم این آموزش بدردتون بخوره🤞 میتونید اگر سرور شخصی دارید به همین روش کانفیگ‌ خودتان را ببرید پشت fastly و از دامنه fake استفاده کنید تا از فیلتر شدن دامنه شخصی خودتان جلوگیری کنید☺️


آموزش کامل امین در لینک زیر هست:


https://threadreaderapp.com/thread/1862564725260767600.html


آموزش استفاده از CDN سایت Fastly برای افزایش امنیت و کاهش اختلال

در این آموزش کوتاه، می‌خواهیم یک کانفیگ رایگان را پشت CDN سایت Fastly قرار دهیم. این روش چندین مزیت دارد:

1. کاهش اختلال
2. نامرئی شدن از دید فیلترکننده‌ها
3. امکان استفاده حتی از دامنه‌های فیلتر شده
4. عدم نیاز به استفاده از فرگمنت

مراحل اجرا:

۱. انتخاب کانفیگ رایگان سالم
- توصیه می‌شود از پورت ۴۴۳ استفاده شود
- امکان استفاده از پورت‌های دیگر نیز وجود دارد

۲. ورود به سایت Fastly
- ایجاد سرویس جدید
- انتخاب نام برای سرویس
- وارد کردن دامنه جعلی (fake domain)


۳. فعال‌سازی تنظیمات
- انتخاب CDN ساخته شده
- فعال کردن Web Socket
- ایجاد VCL جدید با کد:
```
if(req.http.Upgrade)
{
return (upgrade);
}
```
- فعال‌سازی نهایی سرویس

۴. تغییر کانفیگ اولیه
- جایگزینی IP با IP Fastly
- استفاده از دامنه جعلی برای Host و SNI

نکات مهم:
- دقت به جزئیات تنظیمات
- استفاده از دامنه‌های جعلی برای افزایش امنیت
- می‌توانید از این روش برای سرورهای شخصی نیز استفاده کنید

امیدوارم این آموزش مفید باشد. به امید روزهای بهتر.


## توماج صالحی

<iframe width="100%" height="300" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/1307140042&color=%23ff5500&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true&visual=true"></iframe><div style="font-size: 10px; color: #cccccc;line-break: anywhere;word-break: normal;overflow: hidden;white-space: nowrap;text-overflow: ellipsis; font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;font-weight: 100;"><a href="https://soundcloud.com/toomajsalehi" title="Toomaj" target="_blank" style="color: #cccccc; text-decoration: none;">Toomaj</a> · <a href="https://soundcloud.com/toomajsalehi/bebakhshid" title="Bebakhshid" target="_blank" style="color: #cccccc; text-decoration: none;">Bebakhshid</a></div>

## آموزش ساخت پنل BPB با فستلی

آموزش ساخت پنل BPB با Fastly

### مقدمه
اگر با این پنل آشنایی ندارید، توصیه می‌شود ابتدا ویدیوی معرفی را مشاهده کنید.
- [مشاهده ویدیوی معرفی BPB](https://www.youtube.com/watch?v=SSGt303DzVg)

### پیش‌نیازها

۱. ایمیل یکبار مصرف
- [سایت temp-mail.org](https://temp-mail.org/en) را استفاده کنید
- برای هر اکانت، Cloudflare و Fastly جداگانه ایجاد کنید

۲. اکانت Cloudflare
- [آموزش ساخت اکانت Cloudflare](https://www.youtube.com/watch?v=ltCe31Y3wgg&t=158s)
- نیازی به استفاده از جیمیل نیست و ایمیل یکبار مصرف کافی است

### مراحل نصب

۱. نصب BPB Worker
- [نصب از طریق Cloudflare Workers](https://github.com/bia-pain-bache/BPB-Worker-Panel/blob/main/docs/worker_installation_fa.md)
- [دانلود نسخه 2.7.3 BPB Panel](https://github.com/bia-pain-bache/BPB-Worker-Panel/releases/download/v2.7.3/worker.js)

۲. تغییر UUID
- تغییر UUID الزامی است
- [تولید UUID جدید](https://www.uuidgenerator.net/)
- خط ۴۲۰۲
- محل تغییر: `userID = env.UUID || "123XXXXXXXXXXXXXXXX"`

۳. ساخت اکانت Fastly
- [ثبت‌نام در fastly.com](https://fastly.com)
- [آموزش ساخت اکانت Fastly](https://www.youtube.com/watch?v=O3cl5MifBZo)

### نکات مهم
- حتماً UUID پیش‌فرض را تغییر دهید
- از کانفیگ‌های پیش‌فرض استفاده نکنید
- برای جلوگیری از شناسایی توسط چینی‌ها، تنظیمات را شخصی‌سازی کنید

موفق باشید!

https://x.com/GhostOfSarina/status/1862575995556958459


## Websites using Fastly

https://trends.builtwith.com/websitelist/Fastly


## free config

https://github.com/soroushmirzaei/telegram-configs-collector

فقط کافیه کانفیگ ها رو دستی به فستلی وصل کنید  و تمام