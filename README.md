# تحويل HESABATI ERP لتطبيق أندرويد (APK)

## المتطلبات (مرة واحدة على الكمبيوتر)
1. ثبّت Node.js من: https://nodejs.org (اختر LTS)
2. ثبّت Android Studio من: https://developer.android.com/studio

## خطوات البناء
افتح الطرفية (Terminal / CMD) داخل هذا الفولدر ونفّذ بالترتيب:

```bash
npm install
npx cap add android
npx cap sync android
npx cap open android
```

داخل Android Studio:
- للتجربة على تليفونك: Build > Build APK(s) > خد ملف APK وانقله للتليفون وثبّته
- لرفعه على Google Play: Build > Generate Signed Bundle / APK واختر AAB

## كل مرة تعدّل فيها index.html بعد كده
```bash
npx cap copy android
npx cap open android
```

## أيقونات التطبيق (مهم)
- ضع أيقونة مربعة 192x192 باسم `icon-192.png` و 512x512 باسم `icon-512.png` داخل فولدر `www/`
- مولّد جاهز: https://www.pwabuilder.com/imageGenerator

## ملاحظات
- البيانات تُحفظ محلياً على الجهاز (localStorage) كما في المتصفح تماماً
- Chart.js و XLSX والخطوط تُحمّل من الإنترنت — التطبيق يحتاج اتصال للرسوم البيانية وتصدير Excel (وللبناء الأول مرة أيضاً)
- لو عايز أوفلاين 100%: نزّل الملفات الثلاثة (chart.js, xlsx, خط Cairo) وحطها في فولدر www وعدّل الروابط في index.html
