---
icon: copy
---

# Copy Data Activity

### Copy Data Activity

Fabric Data Pipeline တွေထဲမှာ အသုံးအများဆုံး activity တစ်ခုကတော့ data copy လုပ်ခြင်းပါပဲ။\
Copy Data Activity ဟာ data တွေကို source ကနေ destination ကို ကူးယူဖို့အတွက် အသုံးပြုတဲ့ အခြေခံ လုပ်ဆောင်ချက်ဖြစ်ပါတယ်။\
ဒေတာတွေကို ပုံစံအမျိုးမျိုးနဲ့ နေရာအမျိုးမျိုးကနေ ကူးယူနိုင်ပါတယ်။ ဥပမာ-

* Databases (SQL, NoSQL)
* File storage (Azure Data Lake Storage, Azure Blob Storage)
* SaaS applications (Salesforce)
* Web APIs

ကူးယူတဲ့အခါမှာ data တွေကို ပြောင်းလဲခြင်း (transformations) လုပ်ဖို့လိုအပ်ရင်လဲ pipeline ထဲမှာ လုပ်ပြီးတော့ ကူးယူနိုင်တယ်။

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

### Supported Data Store Types

* Azure Services: Azure Blob Storage, Azure Data Lake Storage Gen2, Azure SQL Database, Azure
* Synapse Analytics, Azure Cosmos DB, etc.
* Databases: SQL Server, Oracle, MySQL, PostgreSQL, etc.
* File Systems: Delimited text, JSON, Parquet, ORC, XML files, etc.
* Generic Protocols: HTTP, FTP, REST

### Source နှင့် Sink

Copy Data activity မှာ အဓိက အစိတ်အပိုင်းနှစ်ခု ပါဝင်ပါတယ်။

* **Source**: ဒေတာတွေ ကူးယူမယ့် data source ကို သတ်မှတ်ပါတယ်။ _ဥပမာ- SQL database ထဲက Table တစ်ခု၊ ဒါမှမဟုတ် Storage account ထဲက File တစ်ခု ဖြစ်နိုင်ပါတယ်။_
* **Sink**: ကူးယူထားတဲ့ ဒေတာတွေကို သိမ်းဆည်းမယ့် destination ကို သတ်မှတ်ပါတယ်။ _ဥပမာ- Data Lake ထဲက Folder တစ်ခု၊ ဒါမှမဟုတ် Synapse Analytics ထဲက Table တစ်ခု ဖြစ်နိုင်ပါတယ်။_

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

### Data Integration ၏ အခြေခံ

Copy Data activity ဟာ extract, transform, load (ETL) သို့မဟုတ် extract, load, transform (ELT) လုပ်ငန်းစဉ်တွေရဲ့ "extract" နဲ့ "load" အဆင့်တွေကို အဓိကအားဖြင့် လုပ်ဆောင်ပေးပါတယ်။ ဒေတာတွေကို ရွှေ့ပြောင်းရာမှာ အခြေခံအကျဆုံးနဲ့ အရေးအပါဆုံး လုပ်ဆောင်ချက်တစ်ခု ဖြစ်ပါတယ်။
