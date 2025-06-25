---
icon: timeline-arrow
---

# Run and monitor pipelines

Pipeline တွေကို တည်ဆောက်ပြီးတာနဲ့ သူတို့ရဲ့ လုပ်ဆောင်ပုံကို စစ်ဆေးဖို့နဲ့ ပြဿနာတွေကို ဖြေရှင်းဖို့အတွက် မှန်ကန်စွာ run ပြီး monitor လုပ်ဖို့ လိုအပ်ပါတယ်။

#### Running Pipeline&#xD;

#### Microsoft Fabric မှာ Pipeline တွေကို run နိုင်တဲ့ နည်းလမ်းများစွာရှိပါတယ်။

* Manual Trigger: Pipeline ကို ဖန်တီးနေစဉ် ဒါမှမဟုတ် တည်ဆောက်ပြီးနောက် "Run" ဒါမှမဟုတ် "Debug" ခလုတ်ကို နှိပ်ပြီး ချက်ချင်း run နိုင်ပါတယ်။
* Debug Run: Pipeline ကို စမ်းသပ် run တာမျိုးပါ။ ဒီ run တွေဟာ monitoring history မှာ မှတ်တမ်းတင်ထားခြင်း မရှိဘဲ၊ Pipeline ရဲ့ လုပ်ဆောင်ချက်ကို ချက်ချင်း မြင်နိုင်ဖို့ အသုံးဝင်ပါတယ်။
* Trigger Now: Pipeline ကို publish လုပ်ပြီးနောက် manual စတင် run တာမျိုးပါ။ ဒါဟာ Pipeline ကို တကယ်တမ်း execute လုပ်တာဖြစ်ပြီး monitoring history မှာ မှတ်တမ်းတင်ထားပါတယ်။
* Scheduled Trigger :  &#x20;Pipeline တွေကို သတ်မှတ်ထားတဲ့ အချိန်အပိုင်းအခြားအလိုက် (ဥပမာ- နေ့စဉ်၊ အပတ်စဉ်၊ လစဉ်) အလိုအလျောက် run စေရန် သတ်မှတ်နိုင်ပါတယ်။ ဒါက data processing တွေကို အလိုအလျောက်လုပ်ဆောင်ဖို့ အသုံးအများဆုံးနည်းလမ်း ဖြစ်ပါတယ်။
* Event-based Trigger :  &#x20;သတ်မှတ်ထားတဲ့ ဖြစ်ရပ်တစ်ခု (ဥပမာ- file အသစ်တစ်ခု storage ထဲ ရောက်လာတာ) ဖြစ်ပေါ်လာတဲ့အခါ Pipeline ကို အလိုအလျောက် run စေရန် သတ်မှတ်နိုင်ပါတယ်။
* Tumbler Window Trigger:  &#x20;ဒေတာများကို ပုံမှန် အချိန်အပိုင်းအခြား (ဥပမာ- နေ့တိုင်း၏ နာရီတိုင်း) အလိုက် စီမံဆောင်ရွက်ရန်အတွက် အသုံးပြုပါတယ်။

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>
