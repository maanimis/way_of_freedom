# Tips


## روش استفاده مجدد از دامنه های فیلتر شده یا کند شده

[روش استفاده مجدد از دامنه های فیلتر شده یا کند شده](https://telegra.ph/%D8%B1%D9%88%D8%B4-%D8%A7%D8%B3%D8%AA%D9%81%D8%A7%D8%AF%D9%87-%D9%85%D8%AC%D8%AF%D8%AF-%D8%A7%D8%B2-%D8%AF%D8%A7%D9%85%D9%86%D9%87-%D9%87%D8%A7%DB%8C-%D9%81%DB%8C%D9%84%D8%AA%D8%B1-%D8%B4%D8%AF%D9%87-%DB%8C%D8%A7-%DA%A9%D9%86%D8%AF-%D8%B4%D8%AF%D9%87-02-16)


# جدا کردن اینترنت داخلی و خارجی روی ویندوز

[برای خلاص شدن از خاموش/روشن کردن فیلترشکن وقتی سایت‌های داخلی باز نمیشه، راحت‌ترین روش مستقیم کردن ترافیک داخلیه که آموزشش برای نرم‌افزار v2rayN (ویندوز) رو در ادامه میگم](https://threadreaderapp.com/thread/1776630039833936285.html)

# نصب مرورگر FireFox روی VPS

مینی آموزش ۳:
نصب مرورگر FireFox روی VPS

هدف آموزش:
بسیاری از وب‌سایت‌ها اجازه‌ی استفاده از خدمات‌شان را به کاربری که با VPN متصل شده، نمی‌دهند. این روش در بسیاری از این قبیل وب‌سایت‌ها، مشکل را برای ما حل می‌کند.

📌 در توئیت جداگانه‌ای تفاوت‌های فنی این روش با VPN را توضیح خواهم داد.

مواد لازم:
-یک VPS با IP تمیز یا غیر تمیز
شما این مرورگر را می‌توانید در سروری که برای VPN شخصی دارید استفاده کنید. هر بار نیاز داشتید، آنرا استارت و پس از انجام کار، استاپ می‌کنید تا منابع سرور آزاد شود.

ابتدا با دستور زیر داکر را نصب کنید:

apt install http://docker.io

پس از نصب داکر، فرمان زیر را برای دانلود ایمیج فایرفاکس بزنید:

docker pull jlesage/firefox

کل دستورات زیر را کپی و در خط فرمان لینوکس پیست کنید و Enter بزنید: (فعلاً فرض کرده‌ام لوکیشن سرور نیویورک است)

docker run -d \
--name=firefox \
-p 5800:5800 \
-e TZ=America/New_York \
-v /docker/appdata/firefox:/config:rw \
jlesage/firefox

حالا در کامپیوترتان یک مرور باز کرده و در نوار آدرس IP سرور و پورت 5800 را بصورت زیر وارد کنید:

http://your-server-ip:5800

حالا یک مرورگر فایرفاکس در مرورگر شما باز می‌شود. مثل آن است که شما پشت سرورتان در لوکیشن مورد نظر نشسته‌اید.
(شبیه به Remote Desktop البته فقط مرورگر)

نکات مهم:
۱-تاریخ/زمان/تایم‌زون سرور تنظیم و مطابق جئولوکیشن IP سرور باشد. مثلاً اگر لوکیشن سرور پاریس است، دستورات زیر را برای تنظیم تایم‌زون و تنظیم اتوماتیک تاریخ/زمان بزنید:

timedatectl set-timezone Europe/Paris

timedatectl set-ntp yes

(کلیدواژه linux timezones را گوگل کنید)

۲-در دستورات داکر، متناسب با لوکیشن سرورتان، عبارت America/New_York را تغییر دهید. مثلاً اگر سرور شما در پاریس است، عبارت زیر را جایگزین کنید:

Europe/Paris

۳-این روش بسته به مقدار CPU و RAM سرور ممکن است تا ۱۰۰٪ منابع را اشغال کند. پس روی VPS های با ۱ هسته و ۱ رم فقط یک تب در براوزر باز باشد.
هر چه تعداد هسته و رم بالاتر، کیفیت بهتر.

۴-پس از انجام کار، اجرای فایرفاکس را با دستور زیر متوقف کنید تا CPU و RAM سرور آزاد شود:

docker stop firefox

برای اجرای مجدد:

docker start firefox

برای حذف از روی سرور:

docker rm firefox

۵-اگر IP سرورتان فیلتر است باید از VPN برای دسترسی استفاده کنید.

۶-این روش ۱۰۰٪ امن است و ذره‌ای DNS Leak ندارد.

موفق باشید 

https://x.com/kevinzakarian/status/1831964467648741794



با آموزش نصب مرورگر روی سرور مجازی و اجرا کردن در سیستم شخصی (مناسب ترید و کارهای حساس) در خدمت شما هستم آموزشی که خیلی ها دنبالش بودن و بالاخره منتشر شده و امیدوارم تا حدودی بتونه مشکل شما رو حل کنه.

البته قبلا هم یه آموزش کیل سوییچ براتون قرار دادم مشابه همین کار که میتونه از لو رفتن آی پی شما جلوگیری کنه.
   • آموزش استفاده از کیل سوییچ در ویندوز ...  




https://www.youtube.com/watch?v=MtrkKb4ojtY


# Vpn sharing via Mypublicwifi app:

گاهی پیش می آید که وی پی ان روی یک دستگاه خاص وصل می شود ولی روی دستگاه دیگه نه.

گاهی هم برای محافظت از باتری یک دستگاه دیگر نیازهست که vpn روی ان دستگاه ران نباشه تا لود کمتری به باتریش وارد بشه.

برای این منظور روش های مختلفی وجود داره که یکی از اون روش ها استفاده از یک اپ سبک کوچک ولی کاربردی و قدرتمند برای ویندوز به نام Mypublicwifi هست.

https://telegra.ph/Vpn-sharing-via-Mypublicwifi-app-08-30-2

این برنامه خیلی باگ داره اگه روش اتصالتون دیال آپ باشه درست روت نمیکنه
استیبل ترین و کم دردسرترین برنامه ای که دیدم

Seraphinite Wifi hotspot for windows

https://www.s-sols.com/products/windows/wi-fi-hotspot


"یکی از اون روش ها استفاده از یک اپ سبک کوچک ولی کاربردی و قدرتمند برای ویندوز به نام Mypublicwifi هست."

اینو منظورم بود، میتونید بدون نیاز به اپلیکیشن خاصی از امکانات خود ویندوز استفاده کنید


virtual Router Manager v0.9 


https://x.com/GhobadiniaM/status/1832472321178603882

# whatsapp

به کارگیری پروکسی در واتس‌اپ یکی از راهکارها برای امنیت بیشتر در استفاده از این پیام‌رسان است.
در «ایران در خاموشی«، با نکات مهم #امنیت_دیجیتال آشنا شوید:
https://filter.watch/irandarkhamooshi/

https://x.com/filterbaan/status/1830888972442312862

