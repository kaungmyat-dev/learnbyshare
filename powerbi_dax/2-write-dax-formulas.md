---
icon: calculator
---

# Write DAX formulas

Structure of DAX Formulas

DAX က excel formulas တွေနဲ့ ဆင်တူပါတယ်။ '=' နဲ့စပြီး functions/operator တွေနဲ့ argument (_`function အတွက် လိုအပ်တဲ့ အချက်အလက်`_) တွေကိုပေါင်းစပ်ရေးသားရပါတယ်။



`e.g Total Sales = SUM('Sales'[Sales Amount])`

<figure><img src=".gitbook/assets/image (2).png" alt="" width="188"><figcaption></figcaption></figure>

DAX Formulas တွေရေးသားတဲ့အခါမှာ သိထားသင့်တဲ့ အချက်တွေကတော့

* **Functions** : SUM, AVERAGE, COUNT, IF, CALCULATE, etc.. _<mark style="background-color:yellow;">`Power BI မှာ function name ကို အစရိုက်လိုက်တာနဲ့ autocomplete က functions တွေကို အကြံပြုပေးပါတယ်။`</mark>_
* **Column References** : column တစ်ခုကို ရည်ညွန်းချင်ရင် Square Brakets `'[ ]'` ထဲမှာရေးရပါတယ်။
  \
  &#xNAN;_<mark style="background-color:yellow;">`e.g [Sales Amount], [Order Quantity]`</mark>_
* **Table References** : Column name က Data model ထဲမှာ တူတာတွေရှိနေရင်တော့ ဘယ် table ထဲက column ဆိုတာကို ရည်ညွှန်းဖို့အတွက် table name ကို Single Quote `'  '` ရေးရပါတယ်။
  \
  &#xNAN;_<mark style="background-color:yellow;">`e.g 'Sales'[Sales Amount], 'Product'[Product Name]`</mark>_
* **Literals** (တိုက်ရိုက်တန်ဖိုးများ) : text values တွေကို double quotes `" "` ထဲမှာထည့်ရေးရပါတယ်။
  \
  &#xNAN;_<mark style="background-color:yellow;">`e.g "Hight Value", "Unknown"`</mark>_
* **Numerical values** တွေကိုတော့ တိုက်ရိုက်ရေးသားနိုင်ပါတယ်။ _`e.g 100, 0.05`_

#### &#x20;Context in DAX

DAX မှာ Context ဆိုတာ အလွန်အရေးကြီးပါတယ်။ Context ဆိုတာ ဖော်မြူလာတစ်ခုကို တွက်ချက်တဲ့အခါ ဘယ်ဒေတာတွေကို ထည့်သွင်းစဉ်းစားရမယ်ဆိုတာကို သတ်မှတ်ပေးတဲ့ အခြေအနေပဲ ဖြစ်ပါတယ်။

DAX မှာ Context နှစ်မျိုးရှိပါတယ်-

**Row Context** :&#x20;

* Calculated Columns တွေ ဖန်တီးတဲ့အခါမှာ အဓိက အသုံးပြုပါတယ်။
* ဖော်မြူလာကို Table ထဲက Row တစ်ကြောင်းချင်းစီ အတွက် တွက်ချက်ပါတယ်။

_`ဥပမာ: Total Price = [Quantity] * [Unit Price] လို့ ရေးရင်၊ Row တစ်ခုချင်းစီရဲ့ Quantity နဲ့ Unit Price ကို ယူပြီး Total Price ကို တွက်ချက်ပေးပါတယ်။`_

&#x20;**Filter Context :**

* Measures တွေ တွက်ချက်တဲ့အခါမှာ အဓိက အသုံးပြုပါတယ်။
* Report (ဥပမာ- Chart, Table) ထဲမှာ Filters တွေ၊ Slicer တွေ၊ Rows/Columns တွေမှာ ထည့်ထားတဲ့ Value တွေကနေ ဖြစ်ပေါ်လာတဲ့ Filter တွေအပေါ် မူတည်ပြီး ဒေတာတွေကို စစ်ထုတ်ပြီး တွက်ချက်ပါတယ်။

{% code overflow="wrap" %}
```
ဥပမာ: Sales Amount ကို Total Sales ဆိုတဲ့ Measure နဲ့ တွက်ထားတယ်ဆိုပါစို့။
Report မှာ Product Category ကို "Electronics" လို့ Filter လုပ်ထားရင် Total Sales က Electronics Category ထဲက Sales Amount တွေကိုပဲ ပေါင်းပေးပါမယ်။
Year ကို "2023" လို့ Filter လုပ်ထားရင် Total Sales က 2023 ခုနှစ်အတွက် Sales Amount တွေကိုပဲ ပေါင်းပေးပါမယ်။
```
{% endcode %}

_<mark style="background-color:yellow;">`CALCULATE Function က Filter Context ကို ပြောင်းလဲဖို့ အဓိက အသုံးပြုတဲ့ DAX Function တစ်ခု ဖြစ်ပါတယ်`</mark>_

#### &#x20;Types of Functions

DAX မှာ Function အမျိုးအစားပေါင်းများစွာရှိပြီး တစ်ခုချင်းစီက သီးခြားလုပ်ဆောင်ချက်တွေ လုပ်ဆောင်ကြပါတယ်

* **Aggregation Functions**: ဒေတာတွေကို စုပေါင်းတွက်ချက်ပေးတဲ့ Function တွေ (ဥပမာ: SUM, AVERAGE, MIN, MAX, COUNT)။
* **Logical Functions**: အခြေအနေတွေကို စစ်ဆေးပြီး True/False တန်ဖိုးတွေ ပြန်ပေးတဲ့ Function တွေ (ဥပမာ: IF, AND, OR)။
* **Text Functions**: စာသားတွေကို စီမံခန့်ခွဲတဲ့ Function တွေ (ဥပမာ: CONCATENATE, LEFT, RIGHT)။
  \
  Date and Time Functions: ရက်စွဲနဲ့ အချိန်တွေကို ကိုင်တွယ်တဲ့ Function တွေ (ဥပမာ: TODAY, YEAR, MONTH)။
* **Table Manipulation Functions**: Table တွေကို စီမံခန့်ခွဲတဲ့ Function တွေ (ဥပမာ: FILTER, ALL)။
  \
  Relationship Functions: Table တွေကြား ဆက်နွယ်မှုကနေ ဒေတာတွေကို ရယူတဲ့ Function တွေ (ဥပမာ: RELATED)။
