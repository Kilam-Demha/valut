إيوا هادي هي الطريقة اللي غادي نخدمو بها 👌  
غادي نعتابرو راسك **Junior JavaScript Developer خدام فشركة E-commerce**، وعندك database فيها **1000 orders** بحال الـJSON اللي عطيتيني.

أنا غادي نكون **Manager / Team Lead**، وكل Task نعطيك فيه:

- 👨‍💼 **شنو قال المدير**
- 🎯 **شنو مطلوب منك**
- 📦 **شنو خاصك تخرج**
- 🧠 **شنو concept غادي تتعلم**
- 🚫 **بلا solution** — نتا اللي غادي تكتب الكود

---

# 🏢 المشروع: E-commerce Data Processing

عندك:

```
orders.json
└── 1000 orders
```

كل Order فيه:

```
order
├── order_id
├── created_at
├── customer
│   ├── customer_id
│   ├── name
│   ├── email
│   ├── phone
│   ├── segment
│   └── address
├── items[]
├── pricing
├── payment
├── shipping
└── metadata
```

---

# 🟢 PHASE 1 — Order Search

## TASK 01 — Find an Order

👨‍💼 **Manager:**

> "Ahmed، support team عطاوني `ORD-000157`. بغيتك تلقى ليا هاد الطلب وترجع ليا المعلومات ديالو كاملة."

### المطلوب منك:

كتب function كتستقبل:

```
order_id
```

وترجع:

```
order object
```

إلا ما لقاتوش:

```
null
```

🎯 **كتتعلم:**

- `find()`
- function
- object access

---

# TASK 02 — Find Customer Orders

👨‍💼 **Manager:**

> "Customer `C00158` تاصل بينا وبغينا نشوفو جميع الطلبات ديالو."

### المطلوب:

خرج **جميع orders** اللي عندهم:

```
customer.customer_id === "C00158"
```

🎯 **كتتعلم:**

- `filter()`
- nested objects

---

# TASK 03 — Search by City

👨‍💼 **Manager:**

> "Marketing بغات تعرف جميع الطلبات ديال customers اللي ساكنين فـ Casablanca."

### المطلوب:

رجع جميع orders ديال:

```
customer.address.city
```

اللي هي:

```
Casablanca
```

🎯 **كتتعلم:**

- nested access
- `filter()`

---

# TASK 04 — Search Product

👨‍💼 **Manager:**

> "Product manager بغى يعرف جميع orders اللي فيها المنتج `HOME-002`."

المشكل:

`items` ماشي object، راه **array**.

يعني خاصك تقلب داخل:

```
items[]
```

### المطلوب:

خرج جميع orders اللي فيها:

```
product.sku === "HOME-002"
```

🎯 **كتتعلم:**

- `filter()`
- `some()`
- nested arrays

---

# 🟢 PHASE 2 — Filtering Business Data

# TASK 05 — High Value Orders

👨‍💼 **Manager:**

> "Sales manager بغى جميع الطلبات اللي قيمتها أكثر من 1000 MAD."

### المطلوب:

استعمل:

```
pricing.total
```

وخرج orders:

```
total > 1000
```

وزيد حسب ليا:

> شحال من order لقينا؟

🎯 **كتتعلم:**

- filtering
- `length`

---

# TASK 06 — Paid Orders

👨‍💼 **Manager:**

> "Finance بغات غير الطلبات اللي payment ديالها paid."

### المطلوب:

خرج:

```
payment.status === "paid"
```

ومن بعد عطيني العدد.

---

# TASK 07 — Paid + Delivered

👨‍💼 **Manager:**

> "بغينا نحسبو غير المبيعات اللي تأكدات: payment paid وshipping delivered."

### المطلوب:

Order خاصو يحقق **جوج شروط**:

```
payment.status === "paid"
```

و:

```
shipping.status === "delivered"
```

🎯 هنا غادي تتعلم **conditions داخل filter**.

---

# TASK 08 — Cancelled Orders

👨‍💼 **Manager:**

> "عطيني جميع الطلبات اللي shipping ديالها cancelled."

ومن بعد:

> "حسب ليا cancellation rate."

يعني:

```
cancelled orders / total orders
```

🎯 هنا غادي تدخل لأول مرة فـ **business metric**.

---

# 🟡 PHASE 3 — Mapping Data

# TASK 09 — Customer List

👨‍💼 **Manager:**

> "CRM team ما محتاجاش Order كامل. بغينا غير customer information."

### المطلوب:

من كل order خرج:

```
customer_id
name
email
city
```

يعني بدل:

```
1000 objects كبار
```

تخرج:

```
1000 objects صغار
```

🎯 **Concept:**

`map()`

---

# TASK 10 — Order Summary

👨‍💼 **Manager:**

> "بغيت report صغير على كل Order."

كل نتيجة خاصها تكون بالشكل:

```
{
    order_id,
    customer_name,
    total,
    payment_status,
    shipping_status
}
```

🚫 ما تبقاش ترجع object كامل.

🎯 `map()` + nested objects.

---

# 🟡 PHASE 4 — Statistics

# TASK 11 — Total Revenue

👨‍💼 **Finance Manager:**

> "عطيني total revenue ديال جميع orders."

خاصك تجمع:

```
pricing.total
```

ديال 1000 orders.

🎯 هنا:

`reduce()`

---

# TASK 12 — Average Order Value

👨‍💼 **Manager:**

> "شنو هو Average Order Value ديال الشركة؟"

Formula:

```
total revenue
----------------
number of orders
```

🎯 `reduce()` + `length`.

---

# TASK 13 — Biggest Order

👨‍💼 **Manager:**

> "بغيت نعرف أكبر Order فالشهر."

### المطلوب:

خرج:

```
order_id
customer
total
```

ديال أكبر order.

---

# TASK 14 — Smallest Order

نفس الفكرة، ولكن:

> "عطيني أصغر Order."

---

# TASK 15 — Total Discounts

👨‍💼 **Finance:**

> "شحال عطينا customers كاملين من discounts؟"

جمع:

```
pricing.discount
```

🎯 `reduce()`.

---

# 🟠 PHASE 5 — Working With `items[]`

هنا غادي تبدأ **المتعة الحقيقية** 😄.

# TASK 16 — Total Quantity Sold

👨‍💼 **Sales Manager:**

> "بغيت نعرف شحال من unit تباعت الشركة كاملة."

ولكن:

كل order فيها:

```
items[]
```

وكل item فيه:

```
quantity
```

### المطلوب:

جمع **جميع quantities** الموجودة داخل جميع orders.

⚠️ هنا عندك:

```
orders
   ↓
items[]
   ↓
quantity
```

🎯 غادي تتعلم التعامل مع **array داخل array داخل object**.

---

# TASK 17 — Product Search

👨‍💼 **Product Manager:**

> "عطيني جميع المعلومات على `HOME-002` اللي باعناه."

بغينا نعرف:

```
product name
category
total quantity sold
revenue
```

🎯 هنا غادي تجمع:

`filter()` + `map()` + `reduce()`.

---

# TASK 18 — Best Selling Product

👨‍💼 **Manager:**

> "شنو هو المنتج اللي باع أكبر quantity؟"

خاصك تخرج:

```
product
quantity
```

مثلاً:

```
Tajine céramique
quantity: 247
```

---

# TASK 19 — Highest Revenue Product

فرق مهم:

**Best selling ≠ Highest revenue**

مثلاً:

```
Product A
100 units × 20 = 2000 MAD

Product B
20 units × 200 = 4000 MAD
```

👨‍💼 **Manager:**

> "بغيت المنتج اللي جاب أكبر revenue."

🎯 هنا غادي تتعلم تفكر فـ **business logic** ماشي غير JS.

---

# 🟠 PHASE 6 — Sorting

# TASK 20 — Orders From Highest To Lowest

👨‍💼 **Sales Manager:**

> "رتب ليا جميع orders من الأغلى للأرخص."

حسب:

```
pricing.total
```

🎯 `sort()`.

---

# TASK 21 — Top 10 Orders

👨‍💼:

> "عطيني Top 10 أغلى orders."

المطلوب:

```
sort
↓
take first 10
```

🎯 `sort()` + `slice()`.

---

# TASK 22 — Highest Rated / Valuable Customers

إلى كان عندك customer metrics، بغينا نرتبوهم حسب spending.

> "عطيني Top 10 customers اللي صرفو أكثر."

هنا غادي تحتاج تجمع orders حسب customer.

🔥 وهنا ندخلو للـ**grouping**.

---

# 🔴 PHASE 7 — Grouping

هاد المرحلة مهمة جداً.

# TASK 23 — Orders Per City

👨‍💼 **Marketing:**

> "بغيت report ديال عدد orders لكل مدينة."

النتيجة مثلاً:

```
Casablanca → 143
Rabat      → 97
Safi       → 61
Marrakech  → 84
...
```

🎯 Concept:

**Group By**

وهذا concept غادي تلقاه من بعد فـSQL حتى هو.

---

# TASK 24 — Revenue Per City

نفس الفكرة ولكن:

> "ما بغيناش number ديال orders. بغينا revenue ديال كل مدينة."

مثلاً:

```
Casablanca → 245,000 MAD
Rabat      → 183,000 MAD
Safi       → 91,000 MAD
```

---

# TASK 25 — Orders Per Payment Method

👨‍💼 **Finance:**

> "شحال من order خلصات بـ cash؟ شحال card؟ شحال bank transfer؟"

النتيجة:

```
cash_on_delivery → 420
card             → 390
bank_transfer    → 190
```

---

# TASK 26 — Orders Per Shipping Carrier

👨‍💼 **Logistics:**

> "بغيت performance ديال carriers."

حسب عدد orders لكل:

```
carrier
```

---

# 🔴 PHASE 8 — Data Quality

دابا غادي نبدلو العقلية.

ما بقيناش غير كنقلبو على data.

ولينا كنشوفو:

> **واش data صحيحة؟**

---

# TASK 27 — Duplicate Order IDs

👨‍💼 **Database Manager:**

> "تأكد ليا واش شي `order_id` تكرر."

المطلوب:

> خرج جميع IDs اللي تكررو.

🎯 `Set` + data validation.

---

# TASK 28 — Invalid Totals

👨‍💼 **Finance:**

> "تأكد ليا واش total ديال كل order صحيح."

القاعدة:

```
subtotal + shipping_fee - discount
=
total
```

خرج orders اللي ما كتحترمش هاد القاعدة.

🔥 هذا Task ديال production حقيقي.

---

# TASK 29 — Invalid Quantity

👨‍💼:

> "قلب ليا على أي item عندو quantity غير صحيحة."

مثلاً:

```
quantity <= 0
```

---

# TASK 30 — Missing Data

👨‍💼 **Data Manager:**

> "لقط ليا orders اللي ناقص فيها customer email."

ومن بعد:

> phone ناقص  
> address ناقص  
> postal code ناقص

🎯 هنا غادي تتعلم التعامل مع:

```
null
undefined
empty string
```

---

# 🔴 PHASE 9 — Dates

# TASK 31 — Orders In June

👨‍💼 **Manager:**

> "عطيني جميع orders اللي تدارو فـJune 2026."

استعمل:

```
created_at
```

🎯 Date processing.

---

# TASK 32 — June Revenue

> "دابا بغيت revenue ديال June فقط."

يعني:

```
filter by date
        ↓
reduce revenue
```

---

# TASK 33 — Best Day

👨‍💼:

> "شنو هو النهار اللي بعنا فيه أكثر؟"

خاصك:

```
date → revenue
```

ومن بعد تلقى maximum.

🔥 هذا قريب بزاف لـreal analytics.

---

# 🔥 PHASE 10 — Manager Requests

دابا نبدأو نعطيوك Tasks بحال Jira tickets.

---

# TASK 34 — VIP Customers

👨‍💼 **CRM Manager:**

> "بغيت نعرف customers اللي صرفو أكثر من 10,000 MAD."

المطلوب:

1. جمع spending ديال كل customer.
2. اختار اللي فوق 10,000.
3. رتبهم من الأكثر للأقل.

---

# TASK 35 — Customer Profile

👨‍💼 **Customer Support:**

> "Customer `C00158` عيط لينا. عطيني profile ديالو."

بغينا:

```
name
email
phone
city
number of orders
total spent
average order
last order
```

🔥 هنا غادي تجمع بزاف ديال concepts.

---

# TASK 36 — Customer Lifetime Value

👨‍💼 **Business Manager:**

> "عطيني Customer Lifetime Value لكل customer."

بمعنى:

```
total amount spent
```

ومن بعد:

> Top 20 customers.

---

# 🚨 TASK 37 — Suspicious Orders

👨‍💼 **Fraud Team:**

> "لقط ليا orders اللي ممكن يكونو suspicious."

Rules:

```
total > 5000
```

أو:

```
payment.status === "failed"
```

أو:

```
shipping.status === "cancelled"
&& total > 1000
```

خرج ليا جميع suspicious orders.

---

# 🚀 TASK 38 — Sales Dashboard Data

👨‍💼 **CEO:**

> "عندي meeting مع المستثمرين. بغيت dashboard data."

خاصك تنتج object واحد فيه:

```
{
    totalOrders,
    totalRevenue,
    averageOrderValue,
    cancelledOrders,
    deliveredOrders,
    paidOrders,
    totalDiscounts,
    topProducts,
    topCities
}
```

🔥 هنا كتجمع تقريباً كلشي تعلمتي.

---

# 🧠 المرحلة الأخيرة: Real Company Challenge

من بعد هاد 38 Tasks، غادي نعطيك **مشروع بلا ما نقول ليك شنو functions تستعمل**.

مثلاً:

> **JIRA-2481 — Sales Analytics**
> 
> CEO بغا report ديال June 2026.
> 
> عطينا:
> 
> 1. Total revenue
> 2. Number of orders
> 3. Average order value
> 4. Top 10 products
> 5. Top 5 cities
> 6. Cancellation rate
> 7. Top 10 customers
> 8. Payment method distribution
> 9. Shipping carrier distribution
> 10. اكتشف أي data anomalies

وهنا **ما غاديش نقول ليك `filter()` ولا `reduce()` ولا `map()`**.

نتا خاصك تقرر **كيفاش تحل المشكلة**.

هاد النقطة هي اللي بغيت نوصلوك ليها:  
**ما تبقاش حافظ JavaScript functions؛ تولي قادر تشوف business problem وتحولها لـalgorithm.**

ونمشيو **Task واحد كل مرة**، نتا تكتب الحل، وأنا نراجعو معاك بلا ما نعطيك الحل من الأول.

wa l ai wa golt lik atini tasks o ana ghadi nafadhom machi atini lhal o lcode ola kifach nwsal ldata iwa ana chno nt3alam khalina nkono manti9iyen ay haja ghadi tkon fi terminal machi hta browser ohta les function ana li ghadi n9adhom nta ghir 9olia chno lmatlob mani fi tamarin

عندك الحق 100%. فهمتك دابا مزيان.

**ما غاديش نعطيك:**

- ❌ الكود
- ❌ الـfunctions اللي تستعمل
- ❌ كيفاش توصل للـdata
- ❌ خطوات الحل
- ❌ حتى hint إلا ما طلبتيهش

أنا غير **Manager**، ونتا **Developer**.  
كل Task غادي نعطيك غير **المشكل business** وشنو خاصك تسلّم.

وبما أننا خدامين من **Terminal**، غادي نعتابرو عندك ملف `orders.json` فيه 1000 order.

---

# 🏢 E-commerce Company — Data Processing Tasks

## 🟢 Sprint 1 — Basic Operations

### TASK 01 — Order Lookup

👨‍💼 **Customer Support:**

> واحد customer عطانا رقم الطلب `ORD-000157`.  
> بغينا نعرفو واش هاد الطلب موجود فالنظام، وإذا كان موجود بغينا معلوماتو كاملة.

**المطلوب منك:**

برنامجك ياخذ `order_id` ويعطي معلومات الطلب، وإذا ما كانش موجود يوضح أنه غير موجود.

---

### TASK 02 — Customer Orders

👨‍💼 **Customer Support:**

> Customer `C00158` تاصل بينا وبغينا نعرفو جميع الطلبات اللي دار.

**المطلوب منك:**

إظهار جميع الطلبات المرتبطة بهاد customer، ومعرفة شحال من order عندو.

---

### TASK 03 — City Orders

👨‍💼 **Marketing:**

> بغينا نعرفو جميع الطلبات ديال customers اللي ساكنين فـ `Safi`.

**المطلوب منك:**

إظهار الطلبات وإعطاء العدد الإجمالي ديالها.

---

### TASK 04 — Product Orders

👨‍💼 **Product Manager:**

> بغينا نعرفو جميع الطلبات اللي فيها المنتج `HOME-002`.

**المطلوب منك:**

إظهار الطلبات اللي فيها هاد المنتج ومعرفة شحال من order فيه.

---

# 🟡 Sprint 2 — Sales

### TASK 05 — High Value Orders

👨‍💼 **Sales Manager:**

> بغينا جميع الطلبات اللي قيمتها أكثر من **1000 MAD**.

**المطلوب منك:**

إظهار هاد الطلبات ومعرفة العدد ديالها.

---

### TASK 06 — Paid Orders

👨‍💼 **Finance:**

> بغينا نعرفو شحال من order تخلص فعلاً.

**المطلوب منك:**

إظهار الطلبات اللي payment ديالها `paid` وإعطاء العدد.

---

### TASK 07 — Completed Sales

👨‍💼 **Sales Manager:**

> بالنسبة لينا، البيع يعتبر مكتمل غير إلا كان payment مدفوع والشحنة توصلات.

**المطلوب منك:**

إظهار جميع الطلبات اللي كتحقق هاد الشرط ومعرفة العدد ديالها.

---

### TASK 08 — Cancelled Orders

👨‍💼 **Logistics Manager:**

> بغينا نعرفو جميع الطلبات اللي تلغات فالشحن.

**المطلوب منك:**

إظهار الطلبات الملغاة وحساب نسبة الطلبات الملغاة من جميع الطلبات.

---

# 🟠 Sprint 3 — Reports

### TASK 09 — Customer Report

👨‍💼 **CRM Manager:**

> عندنا orders كبار بزاف، وأنا ما محتاجش نشوف كل التفاصيل.  
> بغيت report صغير لكل order فيه غير:
> 
> اسم customer، email، المدينة، وorder ID.

**المطلوب منك:**

إنتاج report جديد فيه غير هاد المعلومات.

---

### TASK 10 — Sales Report

👨‍💼 **Sales Manager:**

> بغيت report لكل order فيه:
> 
> Order ID  
> Customer name  
> Total  
> Payment status  
> Shipping status

**المطلوب منك:**

إنتاج report جديد بهاد المعلومات فقط.

---

# 🔵 Sprint 4 — Finance

### TASK 11 — Total Revenue

👨‍💼 **Finance Manager:**

> بغيت نعرف شحال دخلات الشركة من جميع الطلبات.

**المطلوب منك:**

حساب مجموع `total` ديال جميع orders.

---

### TASK 12 — Average Order Value

👨‍💼 **Finance Manager:**

> بغيت متوسط قيمة الطلبات ديال الشركة.

**المطلوب منك:**

إعطاء Average Order Value.

---

### TASK 13 — Biggest Order

👨‍💼 **CEO:**

> شنو هو أكبر order فالنظام؟

**المطلوب منك:**

إظهار Order ID، customer، وtotal ديال أكبر order.

---

### TASK 14 — Smallest Order

👨‍💼 **CEO:**

> وشنو هو أصغر order؟

**المطلوب منك:**

إظهار نفس المعلومات ديال أصغر order.

---

### TASK 15 — Discounts

👨‍💼 **Finance:**

> شحال مجموع discounts اللي عطينا للcustomers؟

**المطلوب منك:**

حساب مجموع جميع discounts.

---

# 🟣 Sprint 5 — Products

### TASK 16 — Units Sold

👨‍💼 **Sales Manager:**

> بغيت نعرف شحال من وحدة product تباعت الشركة كاملة.

**المطلوب منك:**

حساب مجموع `quantity` ديال جميع المنتجات فـجميع orders.

---

### TASK 17 — Product Performance

👨‍💼 **Product Manager:**

> بغيت report على المنتج `HOME-002`.

**المطلوب منك:**

التقرير خاصو يبين:

- اسم المنتج
- category
- مجموع الوحدات المباعة
- مجموع revenue اللي جاب

---

### TASK 18 — Best Selling Product

👨‍💼 **Sales Manager:**

> شنو هو المنتج اللي تباع بأكبر عدد من الوحدات؟

**المطلوب منك:**

إظهار اسم المنتج وعدد الوحدات المباعة.

---

### TASK 19 — Highest Revenue Product

👨‍💼 **CEO:**

> شنو هو المنتج اللي جاب أكبر revenue؟

**المطلوب منك:**

إظهار المنتج والـrevenue ديالو.

---

# 🔴 Sprint 6 — Sorting

### TASK 20 — Expensive Orders

👨‍💼 **Sales Manager:**

> بغيت orders مرتبين من الأغلى للأرخص.

**المطلوب منك:**

إظهار القائمة مرتبة حسب total.

---

### TASK 21 — Top 10 Orders

👨‍💼 **CEO:**

> عطيني غير Top 10 أغلى orders.

**المطلوب منك:**

إظهار أول 10 فقط.

---

# ⚫ Sprint 7 — Business Analysis

### TASK 22 — Orders by City

👨‍💼 **Marketing Manager:**

> بغينا نعرفو شحال من order جاي من كل مدينة.

**المطلوب منك:**

Report بالشكل المنطقي:

```
City → Number of orders
```

---

### TASK 23 — Revenue by City

👨‍💼 **Marketing Manager:**

> عدد orders بوحدو ما كافيناش.  
> بغينا نعرفو شحال revenue جابت كل مدينة.

**المطلوب منك:**

Report:

```
City → Revenue
```

---

### TASK 24 — Payment Methods

👨‍💼 **Finance:**

> بغينا نعرفو شحال من order تخلص بكل payment method.

**المطلوب منك:**

Report:

```
Payment method → Number of orders
```

---

### TASK 25 — Shipping Carriers

👨‍💼 **Logistics:**

> بغينا نعرفو شحال من shipment تعاملات معاها كل شركة توصيل.

**المطلوب منك:**

Report:

```
Carrier → Number of shipments
```

---

# 🧹 Sprint 8 — Data Quality

### TASK 26 — Duplicate Orders

👨‍💼 **Database Manager:**

> تأكد ليا واش شي `order_id` مكرر فالنظام.

**المطلوب منك:**

إظهار IDs المكررة.

---

### TASK 27 — Invalid Totals

👨‍💼 **Finance Manager:**

> شي واحد شك أن بعض totals ممكن يكونو غلط.

القاعدة ديالنا:

```
subtotal + shipping_fee - discount = total
```

**المطلوب منك:**

لقط جميع orders اللي الحساب ديالها ما مطابقش.

---

### TASK 28 — Invalid Quantities

👨‍💼 **Inventory Manager:**

> بغينا نتأكدو أن جميع quantities صحيحة.

**المطلوب منك:**

لقط أي product عندو quantity غير صالحة.

---

### TASK 29 — Missing Emails

👨‍💼 **CRM Manager:**

> بغينا نعرفو customers اللي ما عندناش email ديالهم.

**المطلوب منك:**

إظهار orders اللي customer ديالها ناقصو email.

---

### TASK 30 — Missing Contact Data

👨‍💼 **CRM Manager:**

> دير audit للـcustomer contact information.

**المطلوب منك:**

لقط records اللي ناقص فيها:

- email
- phone
- address
- city
- postal code

---

# 📅 Sprint 9 — Dates

### TASK 31 — June Orders

👨‍💼 **Sales Manager:**

> بغينا جميع orders اللي تدارو فـJune 2026.

**المطلوب منك:**

إظهارهم وحساب العدد.

---

### TASK 32 — June Revenue

👨‍💼 **Finance:**

> شحال revenue حققنا فـJune 2026؟

**المطلوب منك:**

إعطاء total revenue ديال June.

---

### TASK 33 — Best Sales Day

👨‍💼 **CEO:**

> فـJune 2026، شنو كان أحسن نهار من ناحية revenue؟

**المطلوب منك:**

إظهار:

```
Date
Revenue
```

ديال النهار الأفضل.

---

# 🔥 Sprint 10 — Customer Intelligence

### TASK 34 — VIP Customers

👨‍💼 **CRM Manager:**

> بغينا نعرفو customers اللي صرفو أكثر من **10,000 MAD**.

**المطلوب منك:**

إظهار customers اللي وصلو لهد المبلغ وترتيبهم من الأكثر إنفاقاً للأقل.

---

### TASK 35 — Customer Profile

👨‍💼 **Customer Support:**

> Customer `C00158` عيط لينا. بغينا profile كامل ديالو.

**المطلوب منك:**

التقرير يبين:

```
Name
Email
Phone
City
Number of orders
Total spent
Average order
Last order
```

---

### TASK 36 — Top Customers

👨‍💼 **CEO:**

> بغيت نعرف Top 20 customers اللي كيصرفو أكثر فلشركة.

**المطلوب منك:**

إظهار:

```
Customer
Number of orders
Total spent
```

مرتبة من الأعلى للأقل.

---

# 🚨 Sprint 11 — Fraud / Anomalies

### TASK 37 — Suspicious Orders

👨‍💼 **Fraud Team:**

> بغينا نراجعو orders اللي ممكن يكونو suspicious.

الـbusiness rules اللي عطاك الفريق:

- Order أكثر من `5000 MAD`
- أو payment فاشل
- أو shipping cancelled وorder أكثر من `1000 MAD`

**المطلوب منك:**

إظهار جميع orders اللي كتدخل فواحد أو أكثر من هاد الحالات.

---

# 🏆 FINAL TASK — CEO Dashboard

### TASK 38 — Executive Report

👨‍💼 **CEO:**

> عندي اجتماع مهم وبغيت summary ديال الشركة من الـ1000 orders.

**المطلوب منك تبني report واحد فيه:**

```
Total orders
Total revenue
Average order value
Total discounts
Paid orders
Delivered orders
Cancelled orders
Top 10 products
Top 5 cities
Top 10 customers
Payment methods
Shipping carriers
Data anomalies
```

⚠️ **هنا ما غاديش نقول ليك شنو تستعمل.**

لا `filter()`  
لا `map()`  
لا `reduce()`  
لا `sort()`  
لا `Set`  
لا أي function.

**نتا اللي خاصك تقرر architecture ديال الحل.**

---

هادشي هو النوع اللي غادي يخليك فعلاً تتعلم: **أنا نعطيك Business Requirement → نتا تفكر → تكتب JS → تشغل من Terminal → تشوف النتيجة → وأنا نراجع معاك.**

ونبدأو **TASK 01 فقط**. ما ندوزوش لـTASK 02 حتى تكمل الأول.

bi nisba lclining dial data

آه، بالنسبة لـ **Cleaning ديال Data**، خاصنا حتى هو نديروه بحال **Tasks ديال شركة**، وما نعطيكش كيفاش تحلو.

غادي نخليو Cleaning بوحدو كـ **Data Quality Sprint**.

## 🧹 Data Cleaning — Tasks

### TASK C01 — Missing Email

👨‍💼 **CRM Manager:**

> عندنا 1000 order. بغيت نعرف شكون من customers ناقص عندو email.

**المطلوب منك:**

- تلقى جميع records اللي email ديال customer ناقص.
- عطيني `order_id` و`customer_id`.
- عطيني العدد الإجمالي.

---

### TASK C02 — Missing Phone

👨‍💼 **CRM Manager:**

> دير نفس الـaudit ولكن هاد المرة على phone.

**المطلوب منك:**

- جميع orders اللي phone ناقص.
- `order_id`
- `customer_id`
- العدد الإجمالي.

---

### TASK C03 — Missing Address

👨‍💼 **Data Manager:**

> بغينا نعرفو customers اللي ناقص عندهم address information.

**المطلوب منك:**

لقط أي customer ناقص عندو واحد من:

- street
- city
- region
- postal_code
- country

---

### TASK C04 — Empty Tags

👨‍💼 **Marketing:**

> بغينا نعرفو orders اللي metadata ديالها ما فيها حتى tag.

**المطلوب منك:**

لقط records اللي `tags` ديالها خاوية، وعطيني العدد.

---

### TASK C05 — Invalid Prices

👨‍💼 **Finance:**

> تأكد لينا أن جميع الأسعار منطقية.

**المطلوب منك:**

لقط أي item عندو:

- `unit_price` أقل من أو يساوي 0
- `quantity` أقل من أو يساوي 0
- `line_total` أقل من 0

---

### TASK C06 — Invalid Order Total

👨‍💼 **Finance Manager:**

> بغينا نتأكدو أن الحسابات ديال orders كلها صحيحة.

القاعدة:

```
subtotal + shipping_fee - discount = total
```

**المطلوب منك:**

لقط جميع orders اللي الحساب ديالها ما مطابقش.

---

### TASK C07 — Invalid Line Total

👨‍💼 **Inventory Manager:**

> بغينا نتأكدو أن كل item محسوب بشكل صحيح.

القاعدة:

```
quantity × unit_price = line_total
```

**المطلوب منك:**

لقط جميع items اللي الحساب ديالها غلط، وبيّن لينا الـorder والـproduct المعني.

---

### TASK C08 — Payment Inconsistency

👨‍💼 **Finance:**

> بغينا نلقاو الحالات اللي payment information فيها تناقض.

مثلاً business rule ديالنا:

- order `paid` → خاص payment status يكون `paid`
- order `failed` → ما خاصهاش تكون `paid`

**المطلوب منك:**

لقط records اللي ما كتحترمش rules ديال payment.

---

### TASK C09 — Shipping Inconsistency

👨‍💼 **Logistics:**

> دير audit للـshipping.

كاينين قواعد منطقية:

- `delivered` خاص يكون عندو `delivered_at`
- `shipped` خاص يكون عندو `shipped_at`
- `cancelled` ما خاصوش يكون عندو `delivered_at`

**المطلوب منك:**

لقط جميع الحالات غير المنطقية.

---

### TASK C10 — Invalid Dates

👨‍💼 **Data Manager:**

> تأكد لينا أن التواريخ صالحة.

**المطلوب منك:**

لقط orders اللي:

- `created_at` ناقص
- `created_at` ماشي تاريخ صالح
- التاريخ خارج الفترة اللي خدامين عليها

---

### TASK C11 — Duplicate Orders

👨‍💼 **Database Manager:**

> تأكد لينا أن كل `order_id` unique.

**المطلوب منك:**

لقط IDs المكررة، وعطيني شحال من مرة تكررت كل وحدة.

---

### TASK C12 — Duplicate Customers

👨‍💼 **CRM Manager:**

> تأكد لينا أن customer records ما فيهمش duplication واضح.

**المطلوب منك:**

قلب على customers اللي عندهم نفس:

- email

أو نفس:

- phone

وبين لينا الحالات المشبوهة.

---

### TASK C13 — Invalid Enum Values

👨‍💼 **Backend Team:**

> شي data ممكن تكون داخلة بقيم غير معروفة.

القيم المسموحة عندنا معروفة بالنسبة لـ:

- `segment`
- `payment.method`
- `payment.status`
- `shipping.status`
- `metadata.channel`

**المطلوب منك:**

لقط أي record فيه value ما داخلاش فالقيم المسموحة.

---

### TASK C14 — Normalize City Names

👨‍💼 **Data Analyst:**

> لقينا أن بعض المدن مكتوبة بطرق مختلفة، بحال:

```
Casablanca
casablanca
CASABLANCA
```

**المطلوب منك:**

حدد جميع الاختلافات اللي كتمثل نفس المدينة، وخرج لينا report ديال القيم اللي خاصها normalization.

⚠️ **ما تبدلش data الأصلية دابا.** غير اكتشف المشاكل.

---

### TASK C15 — Full Data Quality Report

👨‍💼 **Head of Data:**

> بغيت تقرير كامل على جودة الـ1000 orders.

**المطلوب منك تخرج:**

```
Total records
Missing emails
Missing phones
Missing addresses
Invalid prices
Invalid quantities
Invalid totals
Invalid line totals
Payment inconsistencies
Shipping inconsistencies
Invalid dates
Duplicate order IDs
Duplicate customer data
Invalid enum values
Normalization issues
```

وفي الأخير:

> عطيني **Data Quality Score** من 0 إلى 100 بناءً على عدد المشاكل اللي لقيتي.

---

وهنا واحد المبدأ مهم: **Cleaning ماشي غير "نبدل data الخايبة".**

فـالشركة غالباً كتدير:

```
Raw Data
   ↓
Detect Problems
   ↓
Report Problems
   ↓
Define Rules
   ↓
Clean / Normalize
   ↓
Validate Again
   ↓
Clean Data
```

يعني فـTasks **C01 → C15** غادي نتعلمو أولاً **نكتاشفو المشاكل**، ومن بعد ندوزو لـ **Cleaning فعلي**: نصلحو النسخ، نوحدو القيم، ونعيدو validation.