# Configure Relationships

model ထဲမှာ tables တစ်ခုထက်ပိုနေပြီဆိုရင်၊ tables တွေကြားမှာ သင့်တော်တဲ့ relationships (ဆက်နွယ်မှုတွေ) ရှိနေဖို့ လိုအပ်ပါတယ်။

ဒီ relationships တွေက filter ကို table တစ်ခုကနေ နောက် table တစ်ခုဆီကို ပို့ပေးတဲ့ အလုပ်ကို လုပ်ပါတယ်။ relationship path ရှိနေသရွေ့ ဒီလို filter တွေ ပို့တာက ဆက်ပြီး ဖြစ်နေမှာဖြစ်ပြီး၊ tables အများကြီးဆီကိုပါ effect ဖြစ်နိုင်ပါတယ်။

ဥပမာအားဖြင့်၊ report တစ်ခုမှာ Date table ထဲက Year column ကို filter လုပ်လိုက်တဲ့အခါ၊ အဲဒီ filter က Sales table နဲ့ ဆက်စပ်နေတဲ့ relationship ကြောင့် Sales table ထဲကိုပါ အလိုအလျောက် ရောက်သွားပါတယ်။ အဲဒါကြောင့် အဲဒီနှစ်အတွက် ရောင်းအားတွေကိုပဲ စုပေါင်းဖော်ပြပေးမှာ ဖြစ်ပါတယ်။

အနှစ်ချုပ်ပြောရရင်:

* Tables အများကြီးပါတဲ့အခါ relationships တွေ မဖြစ်မနေလိုပါတယ်။
* Relationships တွေက tables တွေကြားမှာ filter တွေကို ပို့ပေးပါတယ်။
* Filter တစ်ခုဟာ relationship path အတိုင်း tables အများကြီးဆီကို effect ဖြစ်နိုင်ပါတယ်။
* အဲ့လို effect ဖြစ်တာကြောင့် data တွေက အလိုအလျောက် filter လုပ်ပြီး စနစ်တကျ ပြသပေးတာပါ။
*

    <figure><img src="../.gitbook/assets/image (3).png" alt="" width="375"><figcaption></figcaption></figure>

Power Query queries တွေကို အသုံးပြုပြီး model ထဲကို data တွေ မသွင်းခင်မှာ Power BI Desktop ရဲ့ Data load options တွေကို အရင်စစ်ဆေးပြီး လိုအပ်ရင် ပြင်ဆင်သင့်ပါတယ်။

အထူးသဖြင့် relationship settings တွေကို ဖွင့်မလား၊ ပိတ်မလားဆိုတာ ဆုံးဖြတ်နိုင်ပါတယ်။\
ဒီ settings တွေကို ဖွင့်ထားရင် source data မှာ တွေ့ရှိရတဲ့ relationships တွေကို အလိုအလျောက် import လုပ်ပေးနိုင်တယ်၊ data refresh လုပ်တဲ့အခါ relationships တွေကို update လုပ်တာ ဒါမှမဟုတ် ဖျက်တာတွေ လုပ်နိုင်ပြီး၊ relationships အသစ်တွေကိုလည်း အလိုအလျောက် ရှာဖွေပေးနိုင်ပါတယ်။

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

တကယ်လို့ relationships တွေ အလိုအလျောက် မဖန်တီးနိုင်ဘူးဆိုရင် Manage relationships window ဒါမှမဟုတ် Model view ကို ပြောင်းပြီး ကိုယ်တိုင် ဖန်တီးနိုင်ပါတယ်။

တစ်ခါတစ်ရံမှာ table တစ်ခုက တခြား table တစ်ခုနဲ့ relationship မလိုတာမျိုး ရှိနိုင်ပါတယ်။ ဒါကို disconnected table လို့ ခေါ်ပါတယ်။ Disconnected table တွေက what-if scenario တွေ ဒါမှမဟုတ် field parameters တွေကို အထောက်အပံ့ပေးတဲ့အခါမှာ အသုံးဝင်ပါတယ်။ ဒီအကြောင်းအရာတွေကိုတော့ ဒီ module ရဲ့ နောက်ပိုင်းမှာ ထပ်ရှင်းပြသွားမှာပါ။

အနှစ်ချုပ်ပြောရရင်:

* Data load မလုပ်ခင် Power BI Desktop ရဲ့ Data load options တွေကို စစ်ပါ။
* Relationship settings တွေက source data က relationships တွေကို အလိုအလျောက် detect (ရှာဖွေ)၊ import နဲ့ update လုပ်ပေးနိုင်ပါတယ်။
* အလိုအလျောက်မဖန်တီးနိုင်ရင် Manage relationships window ဒါမှမဟုတ် Model view ကနေ ကိုယ်တိုင် ဖန်တီးနိုင်ပါတယ်။
* Disconnected table (ဆက်နွယ်မှုမရှိသော table) ဆိုတာ တခြား table နဲ့ relationship မလိုတဲ့ table ဖြစ်ပြီး what-if scenarios တွေအတွက် အသုံးဝင်ပါတယ်။
