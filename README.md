# راهنمای اندرو برای ساخت ربات‌های استیم

[![Codacy][codacy-img]][codacy-url]  
[![PayPal][paypal-img]][paypal-url]  
[![Steam Donate][steam-img]][steam-url]

[![Creative Commons][cc-img]][cc-url]

یک راهنمای کامل برای ساخت ربات‌های استیم با استفاده از Node.js.

## فهرست مطالب

- [فصل 1 - مبانی](./Chapter%201%20-%20Basics)
    - [فصل 1.1 - مقدمه](./Chapter%201%20-%20Basics/Chapter%201.1%20-%20Introduction)
    - [فصل 1.2 - پیش‌نیازها](./Chapter%201%20-%20Basics/Chapter%201.2%20-%20Prerequisites)
    - [فصل 1.3 - شروع به کدنویسی](./Chapter%201%20-%20Basics/Chapter%201.3%20-%20Starting%20to%20Code)
    - [فصل 1.4 - TOTP](./Chapter%201%20-%20Basics/Chapter%201.4%20-%20TOTP)
    - [فصل 1.5 - خطاها](./Chapter%201%20-%20Basics/Chapter%201.5%20-%20Errors)
- [فصل 2 - تجارت](./Chapter%202%20-%20Trading)
    - [فصل 2.1 - پیش‌نیازها](./Chapter%202%20-%20Trading/Chapter%202.1%20-%20Prerequisites)
    - [فصل 2.2 - مدیریت پیشنهادهای تجارت](./Chapter%202%20-%20Trading/Chapter%202.2%20-%20Handling%20Trade%20Offers)
    - [فصل 2.3 - ارسال پیشنهادهای تجارت](./Chapter%202%20-%20Trading/Chapter%202.3%20-%20Sending%20Trade%20Offers)
    - [فصل 2.4 - پذیرش اهداها](./Chapter%202%20-%20Trading/Chapter%202.4%20-%20Accepting%20Donations)
- [فصل 3 - تعامل با کاربران](./Chapter%203%20-%20User%20Interaction)
    - [فصل 3.1 - درخواست‌های دوستی](./Chapter%203%20-%20User%20Interaction/Chapter%203.1%20-%20Friend%20Requests)
- [فصل 4 - مبانی توسعه وب](./Chapter%204%20-%20Basics%20of%20Web%20Development)
    - [فصل 4.1 - پیش‌نیازها](./Chapter%204%20-%20Basics%20of%20Web%20Development/Chapter%204.1%20-%20Prerequisites)
    - [فصل 4.2 - برنامه پایه](./Chapter%204%20-%20Basics%20of%20Web%20Development/Chapter%204.2%20-%20Base%20App)
    - [فصل 4.3 - الگوها](./Chapter%204%20-%20Basics%20of%20Web%20Development/Chapter%204.3%20-%20Templates)
    - [فصل 4.4 - پایگاه‌های داده](./Chapter%204%20-%20Basics%20of%20Web%20Development/Chapter%204.4%20-%20Databases)
    - [فصل 4.5 - WebSockets](./Chapter%204%20-%20Basics%20of%20Web%20Development/Chapter%204.5%20-%20WebSockets)
- [فصل 5 - توسعه وب پیشرفته](./Chapter%205%20-%20Advanced%20Web%20Development)
    - [فصل 5.1 - پیش‌نیازها](./Chapter%205%20-%20Advanced%20Web%20Development/Chapter%205.1%20-%20Prerequisites)
    - [فصل 5.2 - احراز هویت](./Chapter%205%20-%20Advanced%20Web%20Development/Chapter%205.2%20-%20Authentication)
- [فصل 6 - اتصال سایت‌ها و ربات‌ها](./Chapter%206%20-%20Connecting%20Sites%20and%20Bots)
    - [فصل 6.1 - پیش‌نیازها](./Chapter%206%20-%20Connecting%20Sites%20and%20Bots/Chapter%206.1%20-%20Prerequisites)
    - [فصل 6.2 - شروع کار](./Chapter%206%20-%20Connecting%20Sites%20and%20Bots/Chapter%206.2%20-%20Getting%20Started)
    - [فصل 6.3 - شروع اتصال](./Chapter%206%20-%20Connecting%20Sites%20and%20Bots/Chapter%206.3%20-%20Beginning%20the%20Connection)

*(فصول بیشتری در راه است)*

## الهام‌بخش

بسیاری از افراد در جوامع [/r/SteamBot](https://reddit.com/r/SteamBot) و
[/r/SteamBotMarket](https://reddit.com/r/SteamBotMarket) به دنبال یک راهنمای کامل برای ساخت ربات‌های استیم با استفاده از Node.js بودند، اما هیچ آموزش کامل و به‌روزی در اینترنت وجود نداشت. این راهنما به منظور کمک به هر کسی که می‌خواهد در مورد ساخت ربات‌های استیم یاد بگیرد تهیه شده است.

زمانی که من شروع به ساخت ربات‌های استیم در اوایل حدود دو سال پیش کردم،
این کار برایم کمی گیج‌کننده بود. ترکیب ماژول‌های مختلف برای ساخت یک ربات کارآمد واقعا دشوار بود، اما هدف من این است که از دردسرهای یادگیری فناوری‌های جدید و مدرن استیم برای تازه‌واردان جلوگیری کنم.

با هم یاد خواهیم گرفت که چطور ربات بسازیم و آن‌ها را به وب‌سایت‌ها متصل کنیم در این راهنمای چند فصلی.

## پروژه‌ها

در این دوره، شما چندین پروژه کوچک خواهید ساخت که همه با هم
وب‌سایت نهایی را تشکیل می‌دهند. در نهایت ما به سایتی خواهیم رسید که
می‌توان از آن برای کسب درآمد از طریق خرید و فروش اسکین‌های TF2 یا CS:GO استفاده کرد، مشابه سایت
http://cs.money/.

## مشارکت

لطفا قبل از ایجاد درخواست کشش (Pull Request)، [راهنمای مشارکت](/CONTRIBUTING.md) را مطالعه کنید.

## اهدا

اگر این راهنما برای شما مفید بود، چند روش برای حمایت از من و ادامه دادن این پروژه وجود دارد:

- [Steam](https://steamcommunity.com/tradeoffer/new/?partner=132224795&token=HuEE9Mk1)
- [Patreon](https://www.patreon.com/andrewda)

<!-- Badge URLs -->

[codacy-img]: https://img.shields.io/codacy/grade/5822ba91cc994725932f71ee6b926400.svg?style=flat-square
[codacy-url]: https://www.codacy.com/app/andrewda/node-steam-guide
[paypal-img]: https://img.shields.io/badge/donate-PayPal-blue.svg?style=flat-square
[paypal-url]: https://www.paypal.me/andrewda/5
[steam-img]:  https://img.shields.io/badge/donate-Steam-lightgrey.svg?style=flat-square
[steam-url]:  https://steamcommunity.com/tradeoffer/new/?partner=132224795&token=HuEE9Mk1
[cc-img]:     https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-url]:     https://creativecommons.org/licenses/by/4.0/
