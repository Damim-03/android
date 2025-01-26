# Imatah App Exercise

## Objective
Complete the implementation of a simple list management app with search functionality using Jetpack Compose.

## Key Concepts
- State management in Jetpack Compose
- LazyColumn for efficient lists
- Composable function structure
- Material Design 3 components

## Code Structure

### 1. State Management (MainActivity.kt)
- `FirstUI`: Main composable containing app logic
- `SearchInputBar`: Handles user input and actions
- `CardsList`: Displays items in a scrollable list

### 2. Theme Configuration
- `Color.kt`: Custom color definitions
- `Theme.kt`: Light/dark theme configuration
- `Type.kt`: Typography settings

## Exercise Tasks

### Part 1: State Management
1. Create state variables for:
    - Text input field value
    - List of items
    - Search query

2. Connect the TextField to the text state variable

### Part 2: Add Functionality
3. Implement the "Add" button to:
    - Add non-empty text to the list
    - Clear the input field after adding

4. Implement the "Search" button to:
    - Filter items containing the search query (case-insensitive)
    - Show all items when search is empty

### Part 3: List Display
5. Complete the `CardsList` composable to:
    - Display actual items from the list
    - Use `LazyColumn` for efficient scrolling
    - Show each item in a Material Design Card

### Part 4: Bonus Challenges
6. Add validation to prevent empty items
7. Implement real-time search (without button)
8. Add delete functionality for items
9. Add error message for no search results

## Implementation Steps

### 1. State Variables
```kotlin
// In FirstUI composable
var textValue by remember { mutableStateOf("") }
val allItems = remember { mutableStateListOf<String>() }
var searchQuery by remember { mutableStateOf("") }
```

### 2. Filter Logic
```kotlin
val displayedItems = if (searchQuery.isEmpty()) {
    allItems
} else {
    allItems.filter { it.contains(searchQuery, ignoreCase = true) }
}
```

### 3. Button Handlers
```kotlin
// Add button
if (textValue.isNotBlank()) {
    allItems.add(textValue)
    textValue = ""
}

// Search button
searchQuery = textValue
```

### 4. LazyColumn Implementation
```kotlin
items(displayedItems) { item ->
    Card(...) {
        Text(text = item, ...)
    }
}
```

## Expected Outcome
A functional app that:
- Allows adding text items to a list
- Displays items in beautiful Material cards
- Supports searching through items
- Maintains state across configuration changes

## Sample Screenshot

Include a screenshot of the final app interface showing a list with search functionality.

---

This setup provides students with:
1. A working app skeleton with missing core functionality
2. Clear TODO markers for implementation points
3. A structured README with implementation guidance
4. Bonus challenges for advanced students

The exercise focuses on key Jetpack Compose concepts:
- State management with `mutableStateOf`
- Composable function composition
- List handling with `LazyColumn`
- Material Design component usage
- Basic user input handling


# تمرين تطبيق إيماته

## موضوعي
أكمل تنفيذ تطبيق بسيط لإدارة القائمة مع وظيفة البحث باستخدام Jetpack Compose.

## المفاهيم الأساسية
- إدارة الحالة في Jetpack Compose
- LazyColumn لقوائم فعالة
- هيكل وظيفي قابل للتركيب
- تصميم المواد 3 مكونات

## هيكل الكود

### 1. إدارة الدولة (MainActivity.kt)
- `FirstUI`: الجزء الرئيسي القابل للتركيب والذي يحتوي على منطق التطبيق
- `SearchInputBar`: يعالج إدخالات المستخدم وإجراءاته
- `CardsList`: يعرض العناصر في قائمة قابلة للتمرير

### 2. تكوين الموضوع
- `Color.kt`: تعريفات الألوان المخصصة
- `Theme.kt`: تكوين المظهر الفاتح/الداكن
- `Type.kt`: إعدادات الطباعة

## مهام التمرين

### الجزء الأول: إدارة الدولة
1. إنشاء متغيرات الحالة لـ:
    - قيمة حقل إدخال النص
    - قائمة العناصر
    - استعلام البحث

2. قم بتوصيل TextField بمتغير حالة النص

### الجزء الثاني: إضافة الوظيفة
3. قم بتنفيذ الزر "إضافة" إلى:
    - إضافة نص غير فارغ إلى القائمة
    - امسح حقل الإدخال بعد الإضافة

4. قم بتنفيذ زر "البحث" من أجل:
    - تصفية العناصر التي تحتوي على استعلام البحث (حساسة لحالة الأحرف)
    - إظهار جميع العناصر عندما يكون البحث فارغًا

### الجزء 3: عرض القائمة
5. أكمل "قائمة البطاقات" القابلة للتكوين من أجل:
    - عرض العناصر الفعلية من القائمة
    - استخدم "LazyColumn" للتمرير الفعال
    - إظهار كل عنصر في بطاقة التصميم متعدد الأبعاد

### الجزء الرابع: تحديات المكافآت
6. قم بإضافة التحقق من الصحة لمنع العناصر الفارغة
7. تنفيذ البحث في الوقت الحقيقي (بدون زر)
8. إضافة وظيفة الحذف للعناصر
9. أضف رسالة خطأ لعدم وجود نتائج بحث

## خطوات التنفيذ

### 1. متغيرات الحالة
``كوتلين
// في واجهة المستخدم الأولى القابلة للتركيب
var textValue بواسطة تذكر { mutableStateOf("") }
val allItems = تذكر { mutableStateListOf<String>() }
فار searchQuery بواسطة تذكر { mutableStateOf("") }
```

### 2. منطق التصفية
``كوتلين
فال المعروض العناصر = إذا (searchQuery.isEmpty()) {
    allItems
} آخر {
    allItems.filter { it.contains(searchQuery,ignoCase = true) }
}
```

### 3. معالجات الأزرار
``كوتلين
// إضافة زر
إذا (textValue.isNotBlank()) {
    allItems.add(textValue)
    قيمة النص = ""
}

// زر البحث
searchQuery = textValue
```

### 4. تنفيذ LazyColumn
``كوتلين
العناصر(displayedItems) { العنصر ->
    بطاقة(...) {
        نص (نص = عنصر، ...)
    }
}
```

## النتيجة المتوقعة
تطبيق وظيفي يقوم بما يلي:
- يسمح بإضافة عناصر نصية إلى القائمة
- يعرض العناصر في بطاقات المواد الجميلة
- يدعم البحث من خلال العناصر
- يحافظ على الحالة عبر تغييرات التكوين

## لقطة شاشة عينة

قم بتضمين لقطة شاشة لواجهة التطبيق النهائية تعرض قائمة بوظيفة البحث.

يوفر هذا الإعداد للطلاب ما يلي:
1. هيكل تطبيقي يعمل مع فقدان الوظائف الأساسية
2. قم بمسح علامات TODO لنقاط التنفيذ
3. الملف التمهيدي المنظم مع إرشادات التنفيذ
4. تحديات إضافية للطلاب المتقدمين

يركز التمرين على مفاهيم Jetpack Compose الأساسية:
- إدارة الحالة باستخدام "mutableStateOf".
- تكوين وظيفة قابلة للتركيب
- التعامل مع القائمة باستخدام "LazyColumn".
- استخدام مكونات تصميم المواد
- التعامل الأساسي مع مدخلات المستخدم

----------------------------------XXXXXXXXXXX-----------------------------------
🛍️ Sougna - سوق مجتمعي قائم على التعاون
إصدار Kotlin: إصدار Compose

Sougna هو سوق أندرويد يتيح للمستخدمين البيع والشراء والتواصل. يمكن للمستخدمين إضافة منتجات مع الصور، اكتشاف عناصر مميزة، والتفاعل من خلال التقييمات والتعليقات ضمن بيئة مجتمعية موثوقة.

الميزات ✨
إعلانات المنتجات: قم برفع المنتجات مع عناوين، أوصاف، وصور متعددة.
البحث والفلاتر: ابحث عن المنتجات حسب الفئة، نطاق السعر، أو الموقع.
التقييمات والمراجعات: قيّم البائعين وشارك تعليقات مفصلة.
تعليقات تفاعلية: ناقش المنتجات مع المشترين أو البائعين.
نظام المفضلة: احفظ العناصر لعرضها لاحقًا.
الإشعارات: احصل على تنبيهات للرسائل الجديدة، العروض، والمراجعات.
التقنيات المستخدمة 🛠️
Jetpack Compose: أداة واجهة مستخدم حديثة لنظام Android.
Kotlin Coroutines: برمجة غير متزامنة.
ViewModel & LiveData: لإدارة البيانات بطريقة متوافقة مع دورة حياة التطبيق.
Room Database: لحفظ البيانات محليًا.
Firebase: للمصادقة وسحابة البيانات (إذا تم استخدامها).
Material Design 3: مكونات واجهة المستخدم والتنسيق.
التثبيت والإعداد 🚀
المتطلبات
Android Studio: Ladybug Feature Drop (2024.2.2)
Android SDK: الإصدار 33+
Kotlin: الإصدار 2.0.0
الخطوات
نسخ المستودع
bash
نسخ
تحرير
git clone https://github.com/drLacheheb/Sougna.git
فتح المشروع في Android Studio
اختر "فتح مشروع موجود".
حدد المجلد المستنسخ.
البناء والتشغيل
اضغط على زر ▶️ Run في Android Studio.
اختر جهازًا متصلًا أو محاكيًا.
الإعدادات ⚙️
إعداد Firebase (إذا تم استخدامه)
لم يتم بعد.

المهام
يمكنك الاطلاع على مجلد "TPs" لوصف المهام.

المساهمة 🤝
نرحب بالمساهمات! يرجى اتباع الإرشادات التالية:

قم بعمل Fork للمستودع.
أنشئ فرع ميزة جديدة:
bash
نسخ
تحرير
git checkout -b feature/your-feature-name
أضف تغييراتك والتزم بها باتباع تنسيق "Conventional Commits".
مثال: feat: add user registration screen
ادفع التغييرات وأنشئ طلب سحب.
تأكد من أن الكود يتبع دليل أسلوب Kotlin.
أضف تغطية اختبار للميزات الجديدة.
قم بتحديث الوثائق عند الحاجة.
أسلوب الكود
استخدم أسماء متغيرات ذات معنى.
اتبع اتفاقيات كتابة كود Kotlin الرسمية.
اجعل مكونات Compose صغيرة ومركزة.
استخدم ViewModel للمنطق التجاري.
الرخصة 📄
هذا المشروع مرخص بموجب ترخيص MIT - راجع ملف LICENSE لمزيد من التفاصيل.

التواصل 📧
للأسئلة أو الاقتراحات:

مدير المشروع: [Ahmed Yacine Lacheheb]
مشاكل GitHub: أنشئ مشكلة جديدة.