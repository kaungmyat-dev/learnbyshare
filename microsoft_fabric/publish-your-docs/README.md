---
icon: book-blank
---

# Introduction to Pipeline

Data pipeline တွေဟာ ဒေတာတွေကို တစ်နေရာကနေ တစ်နေရာကို ရွှေ့ပြောင်းဖို့ (data copying/moving) ၊ပြောင်းလဲဖို့(data transforming) နဲ့ စီမံခန့်ခွဲဖို့အတွက် အသုံးပြုတဲ့ အလိုအလျောက် (automated) လုပ်ဆောင်ချက် အစုအဝေးတစ်ခု ဖြစ်ပါတယ်။

ရိုးရိုးရှင်းရှင်းပြောရရင် data တွေကို စနစ်တကျနဲ့ စဥ်ဆက်မပြတ် စီးဆင်းအောင်လုပ်ဆောင်ပေးတဲ့ လမ်းကြောင်းတွေလို့ ပြောလို့ရပါတယ်။

Data pipeline တွေဟာ ဒေတာအမျိုးမျိုးကို (ဥပမာ- cloud storage, on-premise database, streaming data) ပုံစံတစ်မျိုးကနေ တစ်မျိုးကို ပြောင်းလဲပေးနိုင်ပြီး၊ ဒီပြောင်းလဲထားတဲ့ ဒေတာတွေကို နောက်ထပ် ခွဲခြမ်းစိတ်ဖြာဖို့ (analytics) ဒါမှမဟုတ် အစီရင်ခံစာတွေ (reporting) ထုတ်ဖို့အတွက် အသင့်ဖြစ်အောင် ပြင်ဆင်ပေးပါတယ်။

အောက်မှာ အဓိကနားလည်ဖို့လိုအပ်တဲ့ core pipeline concepts အချို့ကိုဖော်ပြပါမယ်။

### Activities

#### data transformation activities

Pipeline တစ်ခုစီမှာ တစ်ခု ဒါမှမဟုတ် တစ်ခုထက်ပိုတဲ့ Activities တွေ ပါဝင်ပါတယ်။ Activity တစ်ခုစီဟာ သီးခြားလုပ်ဆောင်ချက်တစ်ခုကို ကိုယ်စားပြုပါတယ်။ e.g

* Copy Data Activity: ဒေတာတွေကို တစ်နေရာကနေ တစ်နေရာကို ကူးယူဖို့။
* Data Flow Activity: ဒေတာတွေကို ပုံစံပြောင်းလဲဖို့ (no code)။
* Notebook Activity: Spark notebook တွေ run ပြီး ဒေတာကို စီမံဖို့။
* Stored Procedure Activity: Database ထဲက Stored Procedure တွေ run ဖို့။

#### control flow activities (orchestration)

Pipelines တွေဟာ Activity တွေရဲ့ အစီအစဉ်ကို ထိန်းချုပ်ပါတယ်။ ဥပမာ- Activity တစ်ခု ပြီးမှ နောက်တစ်ခုကို ဆက်လုပ်မလား၊ Activity နှစ်ခုကို တစ်ပြိုင်နက်တည်း လုပ်ဆောင်မလား စသည်ဖြင့် သတ်မှတ်နိုင်ပါတယ်။

### Pipeline တွေရဲ့ အသုံးဝင်ပုံ

* Data Movement: မတူညီတဲ့ data sources တွေကြားမှာ ဒေတာတွေကို လုံခြုံစွာနဲ့ ထိရောက်စွာ ကူးယူရွှေ့ပြောင်းနိုင်ပါတယ်။
* Data Transformation: ဒေတာတွေကို သန့်စင်ဖို့ (clean)၊ စုစည်းဖို့ (organize)၊ ပြန်စီဖို့ (reorder) ဒါမှမဟုတ် ခွဲခြမ်းစိတ်ဖြာ(analysis) လုပ်ဖို့အတွက် လိုအပ်တဲ့ ပုံစံတွေအဖြစ် ပြောင်းလဲနိုင်ပါတယ်။
* Automation: data processing တွေကို Manual လုပ်ဆောင်နေစရာမလိုဘဲ အချိန်ဇယားနဲ့ အလိုအလျောက် run စေနိုင်ပါတယ်။
* Orchestration: ရှုပ်ထွေးတဲ့ data process တွေကို အဆင့်ဆင့် စီမံခန့်ခွဲပြီး မှန်ကန်တဲ့ အစီအစဉ်အတိုင်း လုပ်ဆောင်နိုင်ပါတယ်။

ဥပမာ အနေနဲ့sales data တွေကို နေ့စဥ် excel file တွေကနေ ရယူပြီး database ထဲကို import လုပ်ချင်တယ်ဆိုပါစို့။\
ဒီလိုလုပ်ဖို့ လိုအပ်တဲ့ process တွေကို pipeline တစ်ခုနဲ့ အောက်ပါအတိုင်းလုပ်လို့ရပါတယ်။

1. Linked Service (Excel): Excel file တွေရှိတဲ့ storage location ကို ချိတ်ဆက်ဖို့။
2. Dataset (Excel): Excel file တွေရဲ့ format နဲ့ location ကို သတ်မှတ်ဖို့။
3. Linked Service (Database): ဒေတာထည့်သွင်းမယ့် database ကို ချိတ်ဆက်ဖို့။
4. Dataset (Database Table): ဒေတာထည့်သွင်းမယ့် database table ကို သတ်မှတ်ဖို့။
5. Copy Data Activity: Excel Dataset ကနေ Database Dataset ကို ဒေတာတွေ ကူးယူဖို့။
6. Schedule: ဒီ Pipeline ကို နေ့စဉ် (ဥပမာ- ည ၁၂ နာရီ) မှာ အလိုအလျောက် run ဖို့ သတ်မှတ်ပေးမယ်။

ဒီလို pipeline တစ်ခု တည်ဆောက်ထားခြင်းအားဖြင့် နေ့စဥ် manual လုပ်ရမယ့် process တွေကို အချိန်ကုန်သက်သာပြီး ပိုမိုထိရောက်အောင် လုပ်လို့ရပါတယ်။
