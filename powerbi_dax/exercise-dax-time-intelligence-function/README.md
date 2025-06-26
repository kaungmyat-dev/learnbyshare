---
icon: binary-circle-check
---

# Exercise - DAX time intelligence function

### Time Intelligence Functions

Time intelligence ဆိုတာ ပုံမှန် date/time တွေပေါ်မူတည်ပြီး ပေါင်း၊ နုတ်၊ မြှောက်၊ စား တာတွေလုပ်တာထပ်ပိုပြီး\
DAX မှာ အချိန်အပေါ် အခြေခံပြီး data တွေကို ခွဲခြမ်းစိတ်ဖြာနိုင်ဖို့ လုပ်ထားတဲ့ functions တွေပါ။

Time Intelligence Functions တွေက data တွေကို အောက်ပါ နည်းလမ်းတွေနဲ့ analysis လုပ်နိုင်ဖို့ ကူညီပေးပါတယ်။

* Period-over-period Comparisons : ဥပမာ- ဒီလရဲ့ ရောင်းအားကို မနှစ်က ဒီလရဲ့ ရောင်းအားနဲ့ နှိုင်းယှဉ်တာမျိုး။
* Running Totals : နှစ်အစကနေ လက်ရှိကာလအထိ စုစုပေါင်း ရောင်းအား (Year-To-Date - YTD) လိုမျိုး။
* Moving Averages : နောက်ဆုံး ၃ လရဲ့ ပျမ်းမျှ ရောင်းအား စသဖြင့်။
* Parallel Periods : ဒီနှစ်နဲ့ မနှစ်က စာရင်းတွေကို ဘေးချင်းယှဉ်ပြီး ကြည့်တာမျိုး။

#### Time Intelligence Functions တွေက ဘာကြောင့်အရေးကြီးလဲ။ (ဘာလို့ သုံးဖို့လိုအပ်လဲ)

Business Report တွေမှာ business ရဲ့ performance, progress တွေကို ယခင်ကာတွေနဲ့ နှိုင်းယှဥ်ကြည့်နိုင်ဖို့အတွက် အချိန်နဲ့ပတ်သက်တဲ့ analysis တွေက မရှိမဖြစ်လိုအပ်ပါတယ်။ e.g

* "ဒီလ ရောင်းအားက မနှစ်က ဒီလထက် ဘယ်လောက် ပိုများလာသလဲ။"
* "ဒီနှစ်ရဲ့ စုစုပေါင်းအမြတ်က ဘယ်လောက်လဲ။"
* "လွန်ခဲ့တဲ့ ၇ ရက်အတွင်း ဝယ်ယူမှု ပမာဏ ပျမ်းမျှ ဘယ်လောက်ရှိလဲ။"
* "ဒီလရဲ့ အရောင်းပစ်မှတ်ကို ပြည့်မီပြီလား။"

ဒီလိုမေးခွန်းတွေကို အဖြေရှာဖို့အတွက် DAX Time Intelligence Functions တွေက အကောင်းဆုံး tools တွေဖြစ်ပါတယ်။

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

#### Time Intelligence Functions တွေအလုပ်လုပ်ဖို့ ဘာလိုအပ်လဲ။

Time Intelligence Functions တွေကောင်းမွန်စွာအလုပ်လုပ်ဖို့ data model မှာ 'date table' တစ်ခုမရှိမဖြစ်လိုအပ်တယ်။\
Date Table ရဲ့ လိုအပ်ချက်များ:

* Date Table မှာ Column တစ်ခု ရှိရပါမယ်။ အဲဒီ Column က Date Data Type ဖြစ်ရပါမယ်။
* အဲဒီ Date Column မှာ မရှိမဖြစ် ထူးခြားသော တန်ဖိုးများ (unique values) ပါဝင်ရပါမယ်။ _ဆိုလိုတာက ရက်စွဲတစ်ခုစီဟာ တစ်ကြိမ်ပဲ ပေါ်ရပါမယ် (duplicate မဖြစ်ရပါဘူး)။_
* အဲဒီ Date Column မှာ ရက်စွဲတွေ ဆက်တိုက်ပါဝင်ရပါမယ် (no missing dates)။ _`ဥပမာ- ဇန်နဝါရီ ၁ ရက်ကနေ ၃၁ ရက်အထိဆိုရင် အလယ်မှာ ပျောက်နေတဲ့ရက် မရှိရပါဘူး။`_
* အဲဒီ Date Column မှာ တစ်နှစ်ပြည့် ရက်စွဲများ (full years of data) ပါဝင်သင့်ပါတယ်။ _ဆိုလိုတာက ဇန်နဝါရီ ၁ ရက်ကနေ ဒီဇင်ဘာ ၃၁ ရက်အထိ အပြည့်အစုံ ပါဝင်ရပါမယ်။ `(ဥပမာ- 2022-01-01 ကနေ 2022-12-31 အထိ)`_
* Date Table ကို Power BI Desktop မှာ "`Mark as Date Table`" အဖြစ် သတ်မှတ်ပေးရပါမယ်။ _ဒါမှ Power BI က အဲဒီ Table ကို Time Intelligence Operations တွေအတွက် သုံးဖို့ သိမှာပါ။_

> Date Table မရှိရင် ဘာလုပ်မလဲ။\
>
>
> Source Data မှာ Date Table မပါလာရင် DAX ရဲ့ CALENDAR ဒါမှမဟုတ် CALENDARAUTO Function တွေကို အသုံးပြုပြီး Calculated Table တစ်ခုအနေနဲ့ Date Table ကို ဖန်တီးနိုင်ပါတယ်။ _`ဥပမာ: Date Table = CALENDARAUTO()`_

#### &#x20;Time Intelligence Functions အချို့ ဥပမာများ :

* TOTALYTD: တစ်နှစ်တာ စုစုပေါင်း (Year-To-Date)
* TOTALMTD: တစ်လတာ စုစုပေါင်း (Month-To-Date)
* TOTALQTD: သုံးလပတ်တာ စုစုပေါင်း (Quarter-To-Date)
* DATESYTD: တစ်နှစ်တာ စုစုပေါင်းအတွက် ရက်စွဲများ
* SAMEPERIODLASTYEAR: မနှစ်က ဒီကာလအတွက် ရက်စွဲများ
* DATEADD: ရက်စွဲတွေကို သတ်မှတ်ထားတဲ့ ကာလတစ်ခု (ရက်၊ လ၊ နှစ်) အလိုက် ရှေ့ သို့မဟုတ် နောက်ကို ရွှေ့ပြောင်းခြင်း
* DATESBETWEEN: သတ်မှတ်ထားတဲ့ ရက်စွဲနှစ်ခုကြားက ရက်စွဲများ
