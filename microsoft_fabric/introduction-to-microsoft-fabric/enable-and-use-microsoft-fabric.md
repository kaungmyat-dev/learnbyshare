---
icon: user-check
---

# Enable and use Microsoft Fabric

Microsoft Fabric ကိုစပြီး မသုံးခင်မှာ ကိုယ့်ရဲ့ Organization အတွက် အောက်ပါ user roles တစ်ခုခုကနေပြီးတော့ Microsoft Fabric ကို enable လုပ်ပေးဖို့လိုတယ်။

* **Fabric admin (formerly Power BI admin)**: Manages Fabric settings and configurations.
* **Power Platform admin**: Oversees Power Platform services, including **Fabric**.
* **Microsoft 365 admin**: Manages organization-wide Microsoft services, including **Fabric**.

```
Admin portal > Tenant settings
```

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

#### Creating Fabric Workspaces

Data project တွေနဲ့ resources တွေကို စုစည်းထားဖို့အတွက် Workspaces တွေ လိုအပ်ပါတယ်။

Workspace တစ်ခုစီဟာ သီးခြားစီဖြစ်ပြီး၊ သင့်ရဲ့ data တွေ၊ report တွေနဲ့ analytic item တွေကို စနစ်တကျ စီမံခန့်ခွဲနိုင်ဖို့ ကူညီပေးပါတယ်။ ဥပမာ- 'Sales Analytics' အတွက် Workspace တစ်ခု၊ 'Marketing Data' အတွက် Workspace တစ်ခု စသည်ဖြင့် ခွဲခြားထားနိုင်ပါတယ်။

Workspace တွေဟာ team အဖွဲ့ဝင်တွေ အတူတူ ပူးပေါင်းလုပ်ဆောင်ဖို့အတွက်လည်း အထောက်အကူပြုပါတယ်။ Workspace ထဲမှာ ဘယ်သူတွေက ဘာတွေလုပ်ဆောင်ခွင့်ရှိတယ်ဆိုတာကို သတ်မှတ်နိုင်ပါတယ်။

#### Creating Lakehouses

Workspace တစ်ခု ဖန်တီးပြီးသွားပြီဆိုရင် သင့်ရဲ့ data တွေကို သိမ်းဆည်းဖို့အတွက် Lakehouse တစ်ခုကို ဖန်တီးရမှာ ဖြစ်ပါတယ်။ Lakehouse ဆိုတာက Microsoft Fabric ရဲ့ အဓိက data hub ဖြစ်ပြီး၊ OneLake ပေါ်မှာ အခြေခံပါတယ်။ ဒါဟာ data lake နဲ့ data warehouse ရဲ့ အားသာချက်တွေကို ပေါင်းစပ်ထားတဲ့ ပုံစံ ဖြစ်ပါတယ်။

#### Lakehouse ရဲ့ အစိတ်အပိုင်းများ:

* **Files**: ဒီနေရာမှာ မူရင်း data တွေကို ၎င်းတို့ရဲ့ မူရင်းပုံစံအတိုင်း (_ဥပမာ- CSV, JSON, Parquet files_) သိမ်းဆည်းထားပါတယ်။ ဒါဟာ data lake အပိုင်းဖြစ်ပါတယ်။
* **Tables**: ဒီနေရာမှာတော့ data တွေကို Delta Lake format နဲ့ သိမ်းဆည်းထားပါတယ်။ Delta Lake ဟာ data lake ပေါ်မှာ transaction နဲ့ schema enforcement (data consistency) တွေကို လုပ်ဆောင်နိုင်တဲ့ open-source storage layer တစ်ခုပါ။ ဒါဟာ data warehouse ကဲ့သို့ SQL နဲ့ query လုပ်နိုင်အောင် ကူညီပေးပါတယ်။
* **OneLake**: create လုပ်လိုက်တဲ့ Lakehouse ထဲက files and tables အားလုံးက Onelake ထဲမှာ သိမ်းဆည်းထားတာဖြစ်ပါတယ်။
* **Item importing** : Lakehouse ဖန်တီးပြီးတာနဲ့  Data Factory pipelines တွေ၊ Spark notebooks တွေ ဒါမှမဟုတ် အခြား Fabric tool တွေကနေတဆင့် data တွေကို Lakehouse ထဲကို ထည့်သွင်းနိုင်ပါတယ်။

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

#### Microsoft Fabric ရဲ့ Analytics Item များကို အသုံးပြုခြင်း

* Lakehouse ထဲမှာ data တွေ ရှိနေပြီဆိုရင်တော့ Fabric ရဲ့ ကွဲပြားခြားနားတဲ့ analytic item တွေကို အသုံးပြုပြီး data တွေကို စီမံခန့်ခွဲတာ၊ ခွဲခြမ်းစိတ်ဖြာတာနဲ့ visualization တွေ ဖန်တီးတာတွေ လုပ်ဆောင်နိုင်ပါတယ်။ ဒီ Item တွေက Lakehouse ထဲက data တွေကို တိုက်ရိုက် access လုပ်ပါတယ်။

ဥပမာ-

* Data Factory Pipeline: Data တွေကို Lakehouse ထဲကို ingest လုပ်ဖို့။
*  Notebook: Data တွေကို cleanse and transform လုပ်ဖို့၊ ဒါမှမဟုတ် machine learning model တွေတည်ဆောက်ဖို့။
* Data Warehouse: Structured data တွေကို SQL နဲ့ query လုပ်ဖို့။
* Power BI Report: Lakehouse ထဲက data တွေကို အသုံးပြုပြီး interactive reports and dashboards တွေ ဖန်တီးဖို့။
