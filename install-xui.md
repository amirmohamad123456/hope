# نصب پلتفرم Xray 
در این مقاله کوتاه آموزش می‌دهیم که چگونه می‌توانیم پلتفرم Xray را بر روی لینوکس نصب کنیم. اگر دسترسی به لینوکس ندارید، می توانید برای تهیه سیستم لینوکسی به مستندات ما در این زمینه رجوع کنید.

پیش از پرداختن به قسمت بعدی لازم است اشاره کنیم که Xray به خودی خود هیچگونه رابط کاربری (User Interface) ندارد و ما مجبور خواهیم بود که برای ساخت اکانت به صورت دستی فایل‌های تنظیمات را تغییر دهیم. از آنجا که انجام این کار برای کاربران تازه‌کار کمی سخت خوهد بود، ما به جای نصب مستقیم Xray، [اپلیکیشنی به نام X-UI](https://github.com/vaxilu/x-ui) را نصب خواهیم کرد که در کنار نصب Xray به ما یک رابط کاربری بسیار راحت برای مدیریت کاربران خواهد داد. به طور مثال، در عکس زیر، داشبورد X-UI به شما خواهد گفت که منابع سیستم چگونه در حال استفاده هستند.

![image](https://user-images.githubusercontent.com/118040490/201552920-ed6eca0d-b89c-47ee-a4b3-c65a0b36b90a.png)

# نصب اپلیکیشن X-UI
خب، رسیدیم به اصل ماجرا. مجددا تاکید کنیم که از اینجا به بعد پیش‌فرض ما این هست که شما سیستم لینوکسی خود را تهیه کرده، آدرس IP سرور خود را می‌دانید و موفق شدید به آن SSH کنید. در اینجا فرض می‌کنیم آدرس IP شما مثلا 24.30.41.50 می‌باشد.

۱. ابتدا با دستور زیر، سطح اختیارات را بالا می‌بریم.

```bash
sudo -i
```


۲. با دستور زیر، بانک اطلاعاتی اپلیکیشن‌های لینوکس را به روز می‌کنیم.



```bash
apt update && apt upgrade -y
```


۳. با دستور زیر، فایل نصب X-UI را دانلود می‌کنیم.


```bash
wget https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh
```


۴. با دستور زیر، فایل نصب را اجرا می‌کنیم.


```bash
bash install.sh
```

۵. در جواب سوال 确认是否继续 (آیا مایل به ادامه هستید؟) دکمه y را بزنید.

۶. در جواب سوال 请设置您的账户名 (نام کاربری را مشخص کنید.) باید نام کاربری برای ورود به X-UI بسازید. می‌توانید از نامی مثل admin استفاده کنید.

۷. در جواب سوال 请设置您的账户密码 (رمز عبور را مشخص کنید.) باید رمزعبور را مشخص کنید. هر رمز عبور دلخواهی می‌توانید تعریف کنید. نام‌کاربری و رمزعبور را یادداشت کنید تا بعدا از آن برای ورود به X-UI استفاده کنیم.

۸. در جواب سوال 请设置面板访问端口 (پورت را مشخص کنید.) باید پورتی را مشخص کنیم که از آن برای وصل شدن به X-UI استفاده خواهیم کرد. پورت می‌تواند هر عددی بین 8000 تا 64000 باشد. مثلا می‌توانید پورت 34567 را انتخاب کنید.

۹. تمام. در اینجا کار تمام هست و شما X-UI را نصب کرده‌اید. پیامی شبیه زیر بر روی صفحه باید ظاهر شده باشد.

۱۰. در صورتی که همه چی موفقیت آمیز پیش‌ رفته باشد، حالا باید بتوانیم که X-UI را بر روی مرورگر Chrome و Edge باز کنیم. مثلا اگر آدرس IP سرور ما 24.30.41.50 باشد و پورت را 34567 انتخاب کرده باشیم، آنگاه آدرس http://{IP}:{PORT} را در مرورگر می‌توانیم وارد کنیم.



```bash
http://24.30.41.50:34567
```

![image](https://user-images.githubusercontent.com/118040490/201567547-86a55d6f-7b07-4d0a-848a-0938320e7314.png)

در این صفحه باید نام‌کاربری و رمزعبور را وارد کنید.

۱۱. بعد از ورود موفق وارد صفحه داشبورد اصلی خواهید شد که به صورت پیش‌فرض به زبان چینی می‌باشد.

![image](https://user-images.githubusercontent.com/118040490/201567723-52f3385d-f131-4ae4-81b5-8f2fc28caab7.png)


برای آنکه نوشته‌ها را به انگلیسی تغییر دهیم، کافی در صفحه Right Click کرده و گزینه Translate to English را انتخاب کنیم.

![image](https://user-images.githubusercontent.com/118040490/201567845-434ba7f5-e0e9-44f1-978a-ee994bc1017f.png)

در این لحظه باید بتوانید داشبورد را به صورت انگلیسی مشاهده کنید.

![image](https://user-images.githubusercontent.com/118040490/201567949-66812f72-e568-4eed-932f-96f4a74e0204.png)

۱۲. حالا نوبت ساخت کانفیگ برای اتصال کاربران‌تان رسیده است. در [مقاله ساخت کانفیگ]() به شما نشان می‌دهیم که چگونه انواع ارتباطات VLESS و Trojan را برای کاربران خود تهیه کنید. برای این‌ کار همه چیز از صفحه Inbound Lists شروع می‌شود. پیشنهاد می‌کنیم ادامه را از [مقاله ساخت کانفیگ]() دنبال کنید.

![image](https://user-images.githubusercontent.com/118040490/201568313-6e9e9eb5-4a09-4144-898c-6f4dc48ef44a.png)