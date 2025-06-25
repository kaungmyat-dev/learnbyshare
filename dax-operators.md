---
icon: binary-circle-check
---

# DAX Operators

DAX Operators ဆိုတာ ဖော်မြူလာတွေထဲမှာ တန်ဖိုးတွေကို ပေါင်းစပ်ဖို့၊ နှိုင်းယှဉ်ဖို့၊ ဒါမှမဟုတ် Logic တွေ ထည့်သွင်းဖို့အတွက် အသုံးပြုတဲ့ သင်္ကေတတွေပဲ ဖြစ်ပါတယ်။ Excel မှာ Plus (+) ၊ Minus (-) သင်္ကေတတွေ သုံးသလိုမျိုးပါပဲ။

DAX မှာ အဓိက  Operators ၄ မျိုးရှိပါတယ်။

* **Arithmetic Operator**  &#x20;: +, - , \*, / , ^(power)
* **Comparison Operators** : =, >, >=, <, <=, <>
* **Text Concatenation Operator** : Text Concatenation Operator ဟာ စာသားအပိုင်းအစ နှစ်ခု သို့မဟုတ် နှစ်ခုထက်ပိုတာတွေကို ပေါင်းစပ်ပြီး စာသားတစ်ခုတည်းအဖြစ် ဖန်တီးရာမှာ အသုံးပြုပါတယ်။ '&' ကိုအသုံးပြုပါတယ်။  \
  &#xNAN;_`[First Name] & " " & [Last Name]`_
* &#x20;**Logical Operators** : `&& (AND)`, `|| (OR)`

#### Operators Precedence

DAX ဖော်မြူလာတစ်ခုထဲမှာ Operators မျိုးစုံ ပါဝင်နေရင် ဘယ် Operator ကို အရင်တွက်မလဲဆိုတာကို သတ်မှတ်ပေးတဲ့ ဦးစားပေးအစီအစဉ် (Precedence) ရှိပါတယ်။ ဒီအစီအစဉ်က သင်္ချာမှာ မြှောက်၊ စား ကို အရင်လုပ်ပြီးမှ ပေါင်း၊ နုတ် ကို လုပ်တာနဲ့ ဆင်တူပါတယ်။

အကြမ်းဖျင်းအားဖြင့် ဦးစားပေးအစီအစဉ်ကတော့-

1. Parentheses (): ကွင်းစကွင်းပိတ်ထဲက Expression တွေကို အရင်ဆုံး တွက်ချက်ပါတယ်။ ဒါကြောင့် ဦးစားပေး အစီအစဉ်ကို ပြောင်းလဲချင်ရင် ကွင်းခတ်နိုင်ပါတယ်။
2. Power `^`
3. Multiplication `*` and Divisio&#x6E;_`/`_
4. Addition `+` and Subtraction `-`
5. Text Concatenation `&`
6. Comparison Operators `= < > <= >= <>`
7. Logical AND `&&`
8. Logical OR `||`

_<mark style="background-color:yellow;">`ဘယ် Operator ကို အရင်တွက်မလဲဆိုတာ မသေချာရင် ဒါမှမဟုတ် တွက်ချက်မှု စနစ်တကျ ဖြစ်စေချင်ရင် Parentheses () (ကွင်းစကွင်းပိတ်) တွေနဲ့ လိုအပ်တဲ့ Expression တွေကို ခတ်ပေးပါ။ ဒါက ဖော်မြူလာရဲ့ ရည်ရွယ်ချက်ကို ပိုမို ရှင်းလင်းစေပြီး မှန်ကန်တဲ့ ရလဒ်ကို ရစေမှာပါ။`</mark>_

#### &#x20;Implicit Conversion

Implicit conversion ဆိုတာ data type တွေကို ပြောင်းစရာမလိုဘဲ အလိုအလျောက် Data Type ကို သင့်လျော်အောင် ပြောင်းလဲပေးတဲ့ လုပ်ငန်းစဉ် ကို ဆိုလိုတာပါ။ _DAX ဟာ ရည်ညွှန်းထားတဲ့ Model Object (Columns, Measures) တွေရဲ့ Data Type တွေကို အလိုအလျောက် မှတ်မိပြီး၊ လိုအပ်တဲ့ Operation ကို ပြီးမြောက်စေဖို့ Data Type တွေကို ပြောင်းလဲပေးပါတယ်။_ ဥပမာ:

* `[Sales Amount] + [Tax Rate]` လို့ ရေးတဲ့အခါ `[Sales Amount]` က `Currency` ဖြစ်ပြီး `[Tax Rate]` က `Decimal Number` ဖြစ်နိုင်ပါတယ်။ `DAX` က ဒီနှစ်ခုကို ပေါင်းဖို့အတွက် သူတို့ရဲ့ `Data Type` တွေကို အလိုအလျောက် ချိန်ညှိပေးပါလိမ့်မယ်။
* `[Order Date] = "2023-01-01"` လို့ ရေးတဲ့အခါ `[Order Date]` က `Date/Time` ဖြစ်ပြီး `"2023-01-01"` က `Text` ဖြစ်ပေမယ့် `DAX` က `Text` ကို `Date` အဖြစ် အလိုအလျောက် ပြောင်းလဲပြီး နှိုင်းယှဉ်ပေးပါလိမ့်မယ်။

BLANK Data Type ကို DAX က ကိုင်တွယ်ပုံက Operator အမျိုးအစားပေါ် မူတည်ပြီး ကွာခြားပါတယ်။\
Arithmetic Operators  နဲ့ တွက်ချက်တဲ့အခါ BLANK ကို `0` အဖြစ် သတ်မှတ်ပြီး တွက်ချက်ပါတယ်။

```dax
ဥပမာ: [Sales] + [Bonus] မှာ [Bonus] က BLANK ဖြစ်နေရင် [Sales] + 0 လို့ တွက်ချက်ပါလိမ့်မယ်။
```

Text Concatenation Operator `(&)` နဲ့ ပေါင်းစပ်တဲ့အခါ BLANK ကို `Empty String` အဖြစ် သတ်မှတ်ပြီး ပေါင်းစပ်ပါတယ်။

{% code overflow="wrap" %}
```dax
[First Name] & [Middle Name] & [Last Name] မှာ [Middle Name] က BLANK ဖြစ်နေရင် First Name နဲ့ Last Name ကိုပဲ ပေါင်းစပ်ပေးပါလိမ့်မယ်။ (ဥပမာ: "John" & BLANK & "Doe" ဆို "JohnDoe" ရပါမယ်။ Space လိုရင် [First Name] & " " & [Last Name] လို ရေးရပါမယ်)။
```
{% endcode %}
