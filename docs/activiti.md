```mermaid
flowchart TD
    %% 1. تعریف نودها با سینتکس استاندارد Mermaid
    start{{شروع}} --> role{نقش کاربر؟}

    %% مسیر مهمان
    role -- "مهمان" --> ULogin[ورود/ثبت نام کاربر]
    ULogin --> UPanel[ورود به پنل کاربر]
    UPanel --> SearchHotel[جستجوی هتل‌ها]
    SearchHotel --> ViewRoom[مشاهده جزئیات اتاق]
    ViewRoom --> Booking[ثبت رزرو]
    Booking --> PayOnline[پرداخت آنلاین]
    PayOnline --> Rate{ثبت نظر و امتیاز}
    Rate --> fin(((پایان)))

    %% مسیر پذیرش
    role -- "پذیرش/رزرو‌کننده" --> RLogin[ورود پذیرش]
    RLogin --> RPanel[پنل پذیرش]
    RPanel --> ManageBooking[مدیریت رزروها]
    ManageBooking --> Checkin[تأیید ورود مهمان]
    Checkin --> Checkout[ثبت خروج مهمان]
    Checkout --> fin

    %% مسیر مدیر
    role -- "مدیر سیستم" --> AdminLogin[ورود مدیر]
    AdminLogin --> AdminPanel[پنل مدیریت]
    AdminPanel --> ViewReports[مشاهده گزارشات رزرو و پرداخت]
    ViewReports --> MonitorSystem[(نظارت بر تراکنش‌ها و فعالیت‌ها)]
    MonitorSystem --> fin

    %% 2. استایل‌دهی (برای شبیه سازی اشکال سفارشی)
    style start fill:#ecf6fb,stroke:#4682b4,stroke-width:3px
    style fin fill:#f9e79f,stroke:#b7950b,stroke-width:3px
    style role fill:#dfe3e6,stroke:#566573,stroke-width:2px
    style Booking fill:#d5f5e3,stroke:#145a32
    style Rate fill:#fdebd0,stroke:#b9770e
    style ManageBooking fill:#fef9e7,stroke:#b7950b

    %% 3. توضیحات (SubGraph for Legend)
    subgraph توضیحات [راهنما]
      direction TB
      شرح1["☑️ مسیر مهمان: سبز روشن"]
      شرح2["☑️ مسیر پذیرش: زرد روشن"]
      شرح3["☑️ مسیر مدیر: خاکستری روشن"]
    end

    
