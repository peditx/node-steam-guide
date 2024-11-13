# فصل 1.4 - Steam TOTP

همانطور که احتمالاً می‌دانید، استیم اکنون 2FA را اجباری کرده است. خوشبختانه این را می‌توان با استفاده از ماژول [`steam-totp`](https://github.com/DoctorMcKay/node-steam-totp) به صورت خودکار انجام داد. دوباره، این ماژول را می‌توان با دستور `npm install steam-totp` نصب کرد.

سپس ما دو خط کد به اسکریپت خود اضافه می‌کنیم. وقتی این کار را انجام دهیم، کد به این شکل خواهد بود:

```js
const SteamUser = require('steam-user');
const SteamTotp = require('steam-totp');

const client = new SteamUser();

const logOnOptions = {
  accountName: 'your_steam_username',
  password: 'your_steam_password',
  twoFactorCode: SteamTotp.generateAuthCode('your_steam_shared_secret')
};

client.logOn(logOnOptions);

client.on('loggedOn', () => {
  console.log('Logged into Steam');

  client.setPersona(SteamUser.EPersonaState.Online);
  client.gamesPlayed(440);
});
```

اگر همه چیز به درستی انجام شود، با اجرای دستور `node project1.js` ربات به طور خودکار وارد استیم می‌شود بدون اینکه نیازی به وارد کردن دستی کد 2FA باشد.

حالا بیایید مرحله به مرحله بررسی کنیم که چه چیزی اضافه کردیم. دو خط مهم به فایل اضافه کردیم:

```js
const SteamTotp = require('steam-totp');

[...]

const logOnOptions = {
	[...]
	twoFactorCode: SteamTotp.generateAuthCode('your_steam_shared_secret')
};
```

اولین خط، ماژول `steam-totp` را `require` می‌کند، در حالی که خط دوم کد 2FA ما را با استفاده از الگوریتم TOTP استیم با استفاده از کد مخفی مشترک شما تولید می‌کند. این به عنوان یک کلید به شیء `logOnOptions` اضافه می‌شود.

## چگونه کدهای مخفی خود را پیدا کنید

شاید شما بپرسید که کد مخفی را از کجا پیدا کنید و در واقع روش‌های مختلفی برای این کار بسته به دستگاه شما وجود دارد. اگر از iPhone استفاده می‌کنید، می‌توانید از روش [این لینک](http://forums.backpack.tf/index.php?/topic/45995-guide-how-to-get-your-shared-secret-from-ios-device-steam-mobile/) استفاده کنید، در حالی که اگر از دستگاه Android استفاده می‌کنید، می‌توانید از [این آموزش](https://www.reddit.com/r/SteamBot/comments/3w5zwb/info_get_your_2fa_codes_from_android_no_root/) کمک بگیرید. تنها چیزی که باید بدانید این است که کد مخفی برای تولید کد ورود 2FA استفاده می‌شود، در حالی که کد مخفی هویت برای تایید تراکنش‌ها و بازار استفاده می‌شود. ما از کد هویت در مراحل بعدی زمانی که لازم باشد استفاده خواهیم کرد. به یاد داشته باشید که هیچ‌گاه این کدها را با کسی به اشتراک نگذارید زیرا می‌توانند به راحتی حساب شما را خراب کنند.

[ادامه مطلب](../Chapter%201.5%20-%20Errors)
