``` mermaid
sequenceDiagram
    autonumber
    actor User as کاربر
    participant UI as رابط کاربری
    participant Booking as سرویس رزرو
    participant Pricing as سرویس قیمت‌گذاری
    participant Contract as سرویس قرارداد
    participant Payment as سرویس پرداخت
    participant Notify as سرویس اعلان

    User->>UI: انتخاب سالن، تاریخ و ساعت
    UI->>Booking: درخواست زمان‌های آزاد
    Booking-->>UI: بازگرداندن اسلات‌های آزاد

    User->>UI: انتخاب اسلات و امکانات جانبی
    UI->>Pricing: محاسبه قیمت بر اساس زمان/امکانات
    Pricing-->>UI: قیمت نهایی + جزئیات هزینه‌ها

    UI->>Contract: دریافت خلاصه قرارداد و شرایط لغو/جریمه
    Contract-->>UI: متن قرارداد برای تأیید کاربر

    User->>UI: تأیید قرارداد و ادامه پرداخت
    UI->>Payment: ایجاد تراکنش پرداخت آنلاین
    Payment-->>UI: نتیجه پرداخت و رسید

    UI->>Booking: ثبت رزرو نهایی
    Booking-->>UI: شناسه رزرو + وضعیت

    UI->>Notify: ارسال اعلان تأیید به ایمیل/پیامک/نوتیفیکیشن
    Notify-->>User: اعلان تأیید رزرو با جزئیات
