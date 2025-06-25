---
icon: input-text
---

# Work with DAX functions

DAX Function Library မှာ Function ရာပေါင်းများစွာ ပါဝင်ပြီး တစ်ခုချင်းစီမှာ သူ့ရဲ့ သတ်မှတ်ထားတဲ့ ရည်ရွယ်ချက် ရှိပါတယ်။

DAX ဟာ Microsoft Excel 2010 အတွက် Power Pivot Add-in ကနေ စတင်ဆင်းသက်လာတာဖြစ်လို့ Excel မှာရှိတဲ့ functions ပေါင်း ၈၀ ကျော်ကိုလည်း DAX မှာအသုံးပြုနိုင်ပါတယ်။ ဒါပေမယ့် Excel မှာ မတွေ့ရဘဲ Data Modeling အတွက် သီးသန့် Functions တွေ အများကြီး ရှိပါသေးတယ်။

* **Relationship Navigation Functions**: Table တွေကြားက ဆက်နွယ်မှုတွေကနေ ဒေတာတွေကို ရှာဖွေ ရယူဖို့။
* **Filter Context Modification Functions**: DAX ရဲ့ Filter Context (တွက်ချက်မှုပြုလုပ်မယ့် ဒေတာတွေကို စစ်ထုတ်ထားတဲ့ အခြေအနေ) ကို ပြောင်းလဲဖို့။ CALCULATE function က အကောင်းဆုံး ဥပမာတစ်ခုပါပဲ။
* **Iterator Functions**: Table တစ်ခုချင်းစီရဲ့ Row တွေကို တစ်ခုချင်းစီ စီစစ်ပြီး တွက်ချက်ဖို့။ (SUMX, AVERAGEX လိုမျိုး X ပါတဲ့ Functions တွေ)
* **Time Intelligence Functions**: ရက်စွဲနဲ့ အချိန်ပေါ်အခြေခံပြီး တွက်ချက်မှုတွေ လုပ်ဆောင်ဖို့ (ဥပမာ- နှစ်အလိုက်၊ လအလိုက် ပေါင်းခြင်း၊ နှိုင်းယှဉ်ခြင်း)။
* **Path Functions**: Parent-Child Hierarchy တွေမှာ Path တွေကို ရှာဖွေဖို့။

Excel မှာပါဝင်တဲ့ functions တွေ (SUM, COUNT, AVERAGE, MIN, MAX, etc..) ကို DAX မှာသုံးလို့ရတယ်။

_`ကွာခြားချက်အနေနဲ့ကတော့ Excel မှာ Cell Range (ဥပမာ: A1:A10) ကို ပေးရပေမယ့် DAX မှာတော့ Column Reference (ကော်လံ ကိုးကားချက်) ကို ပေးရပါတယ်။ ဥပမာ: SUM('Sales'[Sales Amount])`_

&#x20;DAX မှာ Data Modeling အတွက် သီးသန့်မဟုတ်ပေမယ့် Excel မှာ မရှိဘဲ DAX မှာ အသုံးဝင်တဲ့ Functions နှစ်ခုကတော့ **DISTINCTCOUNT** နဲ့ **DIVIDE** တို့ ဖြစ်ပါတယ်။

#### DISTINCTCOUNT Function

* DISTINCTCOUNT DAX Function ကို Column တစ်ခုထဲမှာရှိတဲ့ ထပ်မနေတဲ့ တန်ဖိုးအရေအတွက် (Distinct Values) ကို ရေတွက်ဖို့ အသုံးပြုပါတယ်။

#### DIVIDE Function

* DIVIDE DAX Function ကို စားခြင်း (Division) ပြုလုပ်ဖို့ အသုံးပြုပါတယ်။
* numerator (အကြွင်း) နဲ့ denominator (စားကိန်း) Expression တွေကို ပေးရပါမယ်။
* alternate\_result (အစားထိုးရလဒ်) ကို Optionally ထည့်ပေးနိုင်ပါတယ်။

```dax
DIVIDE(<numerator>, <denominator>[, <alternate_result>])
```

> _<mark style="background-color:yellow;">DIVIDE Function ရဲ့ အကြီးမားဆုံး အားသာချက်က 0 (သုည) နဲ့ စားတဲ့အခါ ဖြစ်ပေါ်လာတဲ့ ပြဿနာတွေကို အလိုအလျောက် ကိုင်တွယ်ပေးခြင်း ဖြစ်ပါတယ်။</mark>_
>
> _<mark style="background-color:yellow;">DIVIDE Function ကို denominator က 0 ဒါမှမဟုတ် BLANK ဖြစ်နိုင်တဲ့ Expression တစ်ခု ဖြစ်နေရင် အမြဲတမ်း အသုံးပြုသင့်ပါတယ်။</mark>_
> \
> _<mark style="background-color:yellow;">denominator က အမြဲတမ်း တိကျတဲ့ တန်ဖိုး (constant value) ဖြစ်နေရင်တော့ / (divide operator) ကိုပဲ သုံးနိုင်ပါတယ်</mark>_
> \
> _<mark style="background-color:yellow;">။ ဒီလိုအခြေအနေမျိုးမှာ 0 ဖြစ်နိုင်ခြေမရှိလို့ DIVIDE Function ရဲ့ စစ်ဆေးမှု လုပ်ငန်းစဉ်ကို ရှောင်ရှားနိုင်ပြီး Performance ပိုကောင်းစေပါတယ်။</mark>_

