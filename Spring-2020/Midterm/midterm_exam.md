# شبیه‌سازی بسکتبال خیابانی

## مقدمه

رها پیش‌بینی مسابقات بسکتبال خیابانی را دوست دارد، محمدحسن و پرهام این بازی را دنبال می‌کنند اما می‌خواهند رها را خوشحال کنند برای این کار تصمیم می‌گیرند یک شبیه‌ساز برای این پیش‌بینی‌های این بازی بنویسند تا رها بتواند با آن بازی کند. پرهام و محمدحسن که مشغول پروژه‌های شخصی هستند، این فرصت را به شما می‌دهند که به عنوان امتحان میان‌ترم، این شبیه‌سازی را پیاده‌سازی کنید.

## در مورد شبیه‌ساز

روش کار این شبیه‌ساز به این صورت است که تعدادی تیم در مسابقه وجود دارند (تیم‌ها ویژگی خاصی ندارد و با ترتیب ورودشان از هم جدا می‌شوند)  و بازی می‌کنند و به صورت رندوم برنده مشخص می‌شود و تعدادی کاربر روی برد این تیم‌ها پیش‌بینی می‌کنند. در صورتی که تیمی که کاربر روی آن پیش‌بینی کرده **قهرمان** شود، وی برنده می‌شود.

کاربر تعداد تیم‌های داخل بازی را یکی یکی در شبیه‌ساز اضافه می‌کند. سپس کاربر، پیش‌بینی افراد متفاوتی را با **کدملی** های مختلف در ورودی وارد می‌کند. هر فرد (که با کدملی شناخته می‌شود) می‌تواند حداکثر 2 پیش‌بینی انجام دهد، یعنی بگوید تیم X برنده می‌شود یا تیم Y. در صورتی که تیم X یا Y برنده شوند، این کاربر پیروز شده‌است.

در نهایت بعد از وارد شدن اطلاعات تیم‌ها و  افراد پیش‌بینی کننده، با درخواست کاربر، شبیه‌سازی انجام می‌شود و بازی بین دو به دوی تیم‌ها برگزار می‌کند. این بازی‌ها به صورت **امتیازی و یک طرفه** بوده و احتمال برد هر تیم‌، یکسان و برابر با
$$
\frac{1}{2}
$$
 است. (دقت کنید که حالت مساوی نداریم و حتما یک تیم برنده می‌شود و یک تیم بازنده.) امتیاز تیم برنده برابر با ۱ و تیم بازنده برابر با صفر خواهد بود. روند بازی‌ها برای چهار تیم به شکل زیر خواهد بود:

```
0 plays with 1
0 plays with 2
0 plays with 3

1 plays with 2
1 plays with 3

2 plays with 3
```

## پیاده‌سازی

در ادامه روند اجرای شبیه‌ساز را مرور می‌کنیم:

منو ابتدایی:
```
Welcome to our simulator [n_participants: 0] [n_teams: 0]

1) Add Team
2) Vote for a Winner
3) Execute simulation and report a winner
```

در ابتدا منو فوق نمایش داده می‌شود که در آن از کاربر خواسته می‌شود از بین عملیات‌های زیر یک عملیات را انتخاب کند:

1. عملیات افزودن تیم:  یک تیم به شمار تیم‌های موجود در شبیه‌سازی می‌افزاید. برای تیم لازم نیست هیچ اطلاعات از کاربر گرفته‌شود. این عملیات خروجی خاصی ندارد. 

2. عملات پیش‌بینی یک کاربر برای برد یک تیم: کاربر برنامه کدملی یک شخص را وارد می‌کند و در ادامه یک شماره یک تیم را وارد می‌کند که در واقع فردی که کد ملی‌اش وارد شده پیش‌بینی می‌کند آن تیم برنده می‌شود. یک کد ملی حداکثر می‌تواند دو پیش‌بینی داشته باشد یعنی ۲ بار از گزینه `Vote for a Winner` استفاده کند. در نظر داشته باشید که در انتهای این عملیات می‌بایست به کاربر اطلاع دهید که پیش‌بینی ایشان به درستی اضافه شده است یا خیر.

##### برنامه شما باید بررسی کند کد ملی یک عدد حداکثر ۱۰ رقمی بوده و شماره تیم نیز در بازه تعداد تیم‌ها باشد.

3. با انتخاب این گزینه شبیه‌ساز اجرا شده و به صورت تصادفی تیم‌ها برنده یا بازنده می‌شود و در نهایت برنده لیگ گزارش می‌شود. همچنین شبیه‌ساز اعلام می‌کند چه کد ملی‌هایی پیش‌بینی صحیح داشتند و در نهایت برنامه خاتمه پیدا می‌کند.

بعد از انجام گزینه ۱ یا ۲ دوباره منو ابتدایی نمایش داده می‌شود.

### نمونه ورودی و خروجی

فرض کنید در اولین گام، کاربر اصلی ۴ تیم را وارد کنید یعنی از گزینه ۱ چهار بار  استفاده کند:

```
Welcome to our simulator [n_participants: 0] [n_teams: 1]

1) Add Team
2) Vote for a Winner
3) Execute simulation and report a winner
```

```
Welcome to our simulator [n_participants: 0] [n_teams: 2]

1) Add Team
2) Vote for a Winner
3) Execute simulation and report a winner
```

```
Welcome to our simulator [n_participants: 0] [n_teams: 3]

1) Add Team
2) Vote for a Winner
3) Execute simulation and report a winner
```

```
Welcome to our simulator [n_participants: 0] [n_teams: 4]

1) Add Team
2) Vote for a Winner
3) Execute simulation and report a winner
```

در ادامه فرض کنید به اشتباه عدد ۵ (که در گزینه‌ها موجود نیست) را وارد کند:

```
Invalid Choice
Welcome to our simulator [n_participants: 0] [n_teams: 4]

1) Add Team
2) Vote for a Winner
3) Execute simulation and report a winner
```

در ادامه می‌خواهیم پیش‌بینی تیم برنده را انجام دهیم، برای اینکار گزینه‌ی ۲ را وارد می‌کنیم:

```
ID: 0017784646
Bet: 1
insertion success
Welcome to our simulator [n_participants: 1] [n_teams: 4]

1) Add Team
2) Vote for a Winner
3) Execute simulation and report a winner
```

در ادامه همین شرکت‌کننده می‌خواهد روی تیم شماره صفر نیز پیش‌بینی انجام دهد و به این ترتیب داریم:

```
ID: 0017784646
Bet: 0
insertion success
Welcome to our simulator [n_participants: 2] [n_teams: 4]

1) Add Team
2) Vote for a Winner
3) Execute simulation and report a winner
```

حال ایشان به اشتباه می‌خواهد سومین پیش‌بینی خود را نیز ثبت کند که با خطا مواجه می‌شود:

```
ID: 0017784646
Bet: 2
insertion failed
Welcome to our simulator [n_participants: 2] [n_teams: 4]

1) Add Team
2) Vote for a Winner
3) Execute simulation and report a winner
```

در ادامه یک شرکت‌کننده دیگر می‌خواهد روی تیم‌های شماره‌ی ۲ و ۳ پیش‌بینی انجام دهد:

```
1) Add Team
2) Vote for a Winner
3) Execute simulation and report a winner
2
ID: 0022552898
Bet: 2
insertion success
Welcome to our simulator [n_participants: 3] [n_teams: 4]

1) Add Team
2) Vote for a Winner
3) Execute simulation and report a winner
2
ID: 0022552898
Bet: 3
insertion success
Welcome to our simulator [n_participants: 4] [n_teams: 4]

1) Add Team
2) Vote for a Winner
3) Execute simulation and report a winner
```

در نهایت با استفاده از گزینه ۳ شبیه‌سازی را اجرا می‌کنیم. با انتخاب این گزینه شبیه‌ساز اجرا شده و به صورت تصادفی تیم‌ها برنده یا بازنده می‌شود و در نهایت برنده لیگ گزارش می‌شود. همچنین شبیه‌ساز اعلام می‌کند چه کد ملی‌هایی پیش‌بینی صحیح داشتند و در نهایت برنامه خاتمه پیدا می‌کند.

```
team 2 is a winner
teams[0]: 0
teams[1]: 2
teams[2]: 3
teams[3]: 1
0022552898 win
```

و برنامه به پایان می‌رسد. در پایان تیم برنده اعلام شده و امتیاز همه تیم‌ها لیست می‌شود. در صورتی که چند تیم امتیاز برابر داشته باشند به دلخواه یکی از آن‌ها برنده اعلام می‌شود.

## نکات پیاده‌سازی

- تا جایی که می‌توانید برنامه‌ی خود را به توابع معنی‌دار بشکنید. بهتر است هر تابع یک کار معین را انجام دهد.

- تعداد شرکت‌کننده‌ها و تیم‌ها هر کدام حداکثر ۱۰۰ می‌باشد و تضمین می‌شود بیشتر از این تعداد نخواهند بود.

- دقت کنید که کد ملیَ برنده‌ها باید به شکل صحیح (با صفرهای ابتدایی) چاپ شود. برای این موضوع در نظر داشته باشید که کد ملی با صفرهای ابتدایی دقیقا ۱۰ رقم است.

- برای نگهداری کد ملی از متغیر صحیح استفاده کنید و در نظر داشته باشید که کد ملی از نظر عددی بزرگ می‌باشد.

- برای پیاده‌سازی این پروژه تنها نیاز به آنچه **تا انتهای توابع** بحث شده است دارید اما استفاده از تمام ویژگی‌های زبان سی آزاد می‌باشد.

- در پیاده‌سازی این پروژه فقط از **زبان سی** استفاده کنید. در صورتی که برنامه شما برای اجرا نیاز به تنظیمات خاصی دارد یک راهنما برای اجرای برنامه بنویسید در فایل زیپتان همراه برنامه ارسال کنید.

- از آنجایی که این پروژه در قالب **امتحان میانترم** می‌باشد از تغییر دادن صورت مساله یا انجام موارد خارج از موارد مطرح شده خودداری کنید.

## موارد امتیازی

1. شرکت‌کننده بتواند از پیش‌بینی انصراف دهد. انصراف به این ترتیب خواهد بود که تمامی پیش‌بینی‌های ایشان از لیست پیش‌بینی‌ها حذف خواهد شد. برای اینکار گزینه جدایی مثلا 4 را در نظر بگیرید.

2. چاپ جدول بازی‌ها: در انتهای بازی، همراه لیست برنده‌ها، جدول بازی‌ها و به همراه نتیجه‌شان چاپ شود.

3. بازی‌ها به صورت حذفی باشند. به این ترتیب که تیم بازنده از دور بازی‌ها خارج شده و دیگر در بازی‌ها شرکت نمی‌کند.
  {dir=rtl}