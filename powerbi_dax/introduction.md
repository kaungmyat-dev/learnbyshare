---
icon: book-blank
---

# Introduction

DAX ( Data Analysis Expressions) ဆိုတာ Power BI မှာ data တွေကို ခွဲခြမ်းစိတ်ဖြာဖို့နဲ့ တွက်ချက်မှုအသစ်တွေ ဖန်တီးဖို့အတွက် အသုံးပြုတဲ့ Formula Language ဖြစ်ပါတယ်။\
Excel မှာ ဖော်မြူလာတွေ ရေးတာနဲ့ဆင်တူပြီး၊ DAX က ဒေတာပမာဏ အများကြီးနဲ့ လုပ်ဆောင်နိုင်ပြီး ပိုပြီး ရှုပ်ထွေးတဲ့ တွက်ချက်မှုတွေကိုလည်း လုပ်နိုင်ပါတယ်။

Power BI မှာ data တွေကို load လုပ်ပြီးတာနဲ့ basic report အချို့ကို လုပ်နိုင်ပေမယ့် ပိုနက်နဲ့ပြီး ရှုပ်ထွေးတဲ့ calculation/analysis တွေလုပ်ချင်ရင် DAX ကမရှိမဖြစ်လိုအပ်ပါတယ်။

> ဥပမာ -
>
> * item တစ်ခုချင်းရဲ့ ရောင်းအားက စုစုပေါင်းရောင်းအားရဲ့ ဘယ်လောက် ရာခိုင်နှုန်းရှိလဲ။
> * ဒီနှစ်ရောင်းအားက ပြီးခဲ့တဲ့နှစ်ထက် ဘယ်လောက် တိုးတက်လာလဲ။
> * လွန်ခဲ့တဲ့ ရက် ၃၀ အတွင်း ရောင်းအားစုစုပေါင်း ဘယ်လောက်ရှိလဲ။\
>   စတဲ့ ခွဲခြမ်းစိတ်ဖြာမှုတွေကို DAX ကိုသုံးပြီးတော့ လွယ်လွယ်ကူကူလုပ်လို့ရတယ်။

#### DAX မှာ ဘာတွေ ပါဝင်လဲ

DAX formula တွေကို အောက်ပါ အစိတ်အပိုင်းတွေနဲ့ ဖွဲစည်းထားတယ်။

* **Functions** : SUM, AVERAGE, CALCULATE, FILTER စသဖြင့် ကြိုတင်သတ်မှတ်ထားတဲ့ လုပ်ဆောင်ချက်တွေ ဖြစ်ပါတယ်။ _ဒီ Function တွေကို အသုံးပြုပြီး ဒေတာတွေကို တွက်ချက်၊ ပေါင်း၊ နုတ်၊ စစ်ထုတ် စတာတွေ လုပ်နိုင်ပါတယ်။_
* **Operators** : + (ပေါင်း), - (နုတ်), \* (မြှောက်), / (စား), = (ညီမျှခြင်း) စတဲ့ သင်္ကေတတွေ ဖြစ်ပါတယ်။
* **Constants** : ကိန်းဂဏန်းတွေ (ဥပမာ- 100, 3.14)၊ စာသားတွေ (ဥပမာ- "Hello")၊ ဒါမှမဟုတ် Date/Time တန်ဖိုးတွေ ဖြစ်ပါတယ်။
* **Column References** : ဒေတာ Model ထဲက ကော်လံတွေ။ ဥပမာ- \[Sales Amount] လိုမျိုး။
* **Table References** : ဒေတာ Model ထဲက Table တွေ။ ဥပမာ- Sales\[Amount] လိုမျိုး။

#### Calculated Tables, Calculated Columns, Measures

DAX ကို အဓိကအားဖြင့် Calculated Tables, Calculated Columns နဲ့ Measures ဆိုပြီး ခွဲခြားအသုံးပြုနိုင်ပါသည်။

{% tabs %}
{% tab title="Calculated Tables" %}
Power BI မှာ Time Intelligence (အချိန်နဲ့ပတ်သက်တဲ့ တွက်ချက်မှုတွေ - ဥပမာ: YTD, MTD, QTD) လုပ်ဆောင်ဖို့အတွက် Date Table က မရှိမဖြစ်လိုအပ်ပါတယ်။ မူရင်း data source မှာ ပြည့်စုံတဲ့ date table ပါမလာခဲ့ရင် DAX ကိုအသုံးပြုပြီး Year, Quarter, Month, Day စတဲ့ Columns တွေပါဝင်တဲ့ calculated table တစ်ခု DAX ကိုအသုံးပြုပြီး ဖန်တီးနိုင်တယ်။

မူရင်း Table တစ်ခုလုံးကို မသုံးချင်ဘဲ၊ အဲဒီထဲက ဒေတာအချို့ကိုပဲ ရွေးထုတ်ပြီး Table အသစ်တစ်ခု ဖန်တီးချင်တဲ့အခါမှာလည်း သုံးနိုင်တယ်။ (ဥပမာ- "Sales" Table ထဲက "High-Value Customers" တွေရဲ့ ဒေတာကိုပဲ သီးသန့် Table တစ်ခုအနေနဲ့ ဖန်တီးချင်တာမျိုး။)

Parameter tables (ဥပမာ - slicer မှာအသုံးပြုဖို့အတွက် "Sales by Year", "Sales by Month" လိုမျိုး Report ရဲ့ Type ကို ရွေးချယ်နိုင်တဲ့ Options တွေ) တွေဖန်တီးဖို့လဲ အသုံးပြုနိုင်တယ်။
{% endtab %}

{% tab title="Calculated Columns" %}
* Filter လုပ်ဖို့ ဒါမှမဟုတ် Slice လုပ်ဖို့ လိုအပ်တဲ့ ကော်လံအသစ်တစ်ခု ဖန်တီးချင်တဲ့အခါ (ဥပမာ- "Product Category" ကို "High Value" နဲ့ "Low Value" လို့ ခွဲခြားချင်တာ)
* Row by Row တွက်ချက်မှုတွေ လိုအပ်တဲ့အခါ။
* Column တစ်ခုကို Graph ရဲ့ Axis အဖြစ် အသုံးပြုချင်တဲ့အခါ။

စတဲ့ အခြေအနေတွေမှာ Calculated Columns ကိုအသုံးပြုနိုင်တယ်။

Calculated Columns ရဲ့ အလုပ်လုပ်ပုံက:

* ဒေတာ Table ထဲမှာ ကော်လံအသစ်တစ်ခု ဖန်တီးတာပါ။
* Row တစ်ခုချင်းစီ အတွက် တွက်ချက်မှု ပြုလုပ်ပါတယ်။
* ဒေတာ Model ထဲမှာ Physical (အမှန်တကယ်) ကော်လံအဖြစ် သိမ်းဆည်းထားပြီး Storage နေရာယူပါတယ်။

```
ဥပမာ- [Total Price] = [Quantity] * [Unit Price]
```

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Measures" %}
* Aggregation (စုပေါင်းတွက်ချက်မှု) တွေ ပြုလုပ်ချင်တဲ့အခါ (ဥပမာ- စုစုပေါင်း ရောင်းအား၊ ပျမ်းမျှ အမြတ်)။
* Context ပေါ်မူတည်ပြီး Dynamic ဖြစ်တဲ့ တွက်ချက်မှုတွေ လိုအပ်တဲ့အခါ။
* Report မှာ Value တွေကို ပြသချင်တဲ့အခါ။

စတဲ့ အခြေအနေတွေမှာ Calculated Columns ကိုအသုံးပြုနိုင်တယ်။

Measures ရဲ့ အလုပ်လုပ်ပုံက

* Report ထဲမှာ အသုံးပြုတဲ့ Dynamic calculations
* Report ရဲ့ Context (Filter လုပ်ထားတဲ့ အခြေအနေ၊ Graph ရဲ့ Axis တွေ) ပေါ်မူတည်ပြီး filter ပြောင်းလိုက်တိုင်းမှာ လိုက်ပြီးတွက်ချက်ပေးတယ်။
* Physical Column အနေနဲ့ Storage မယူပဲနဲ့ တွက်ချက်ဖို့ လိုအပ်တဲ့အခါမှ တွက်ချက်ပြီး ရလဒ်ကို ပြသတာပါ။

```
ဥပမာ- Total Sales = SUM('Sales'[Sales Amount])
```

<figure><img src=".gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>
{% endtab %}
{% endtabs %}

#### Calculated Tables, Calculated Columns နဲ့ Measures‌ တွေရဲ့ကွာခြားချက်

* **Calculated Column**: Table ထဲက Row တိုင်းအတွက် တွက်ချက်ပြီး ရလဒ်ကို ကော်လံတစ်ခုအနေနဲ့ သိမ်းထားတယ်။ Storage ယူတယ်။
* **Measure**: Context ပေါ်မူတည်ပြီး Dynamic ဖြစ်တဲ့ တွက်ချက်မှုတွေ လုပ်တယ်။ Report မှာ ပြသတဲ့အချိန်မှ တွက်တာမို့ Storage မယူဘူး။
* **Calculated Table**: Table အသစ်တစ်ခုလုံး ကို ဖန်တီးတာ။ ဒီ Table အသစ်ထဲမှာ Columns နဲ့ Rows တွေ ပါဝင်တယ်။ Data Model ရဲ့ အစိတ်အပိုင်းအဖြစ် Storage ယူတယ်။
