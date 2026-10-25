# AKX Store — خطوات النشر

## 1) أنشئ مشروع Firebase (مجاني)
1. روح على console.firebase.google.com ← **Add project** (اسمه مثلاً akx-store).
2. **Build ← Authentication ← Get started ← Email/Password ← Enable**.
3. **Build ← Firestore Database ← Create database** (اختار Production mode وأي منطقة).
4. **Project settings (الترس) ← Your apps ← أيقونة </> (Web)** ← سجّل التطبيق وانسخ إعدادات `firebaseConfig`.

## 2) الصق الإعدادات
- افتح `config.js` وحط فيه: ايميلك بـ `ownerEmail` + قيم `firebaseConfig`.
- افتح `firestore.rules` وغيّر `PASTE_YOUR_EMAIL@example.com` لايميلك (بأحرف صغيرة)،
  وبعدين انسخ كل المحتوى والصقه بـ **Firestore ← Rules** واضغط **Publish**.

## 3) ارفع على Netlify
- روح على app.netlify.com/drop واسحب **مجلد الموقع كامل** (فيه index.html و config.js).
- من **Site configuration ← Change site name** غيّر الاسم لـ `akxstore`.
- ضيف رابط موقعك بـ Firebase: **Authentication ← Settings ← Authorized domains ← Add domain** (مثل akxstore.netlify.app).

## 4) أول استخدام
1. افتح الموقع واعمل **حساب جديد** بنفس ايميل المالك.
2. من تبويب "موزع نقاط" سجّل دخول بنفس الحساب (بيطلع "الحساب غير موزع" ويوصلك طلب).
3. ادخل تبويب "عميل" ← **لوحة المالك** ← **موافقة**. بعدها بتبدّل بين العميل والموزع من فوق على اليسار.

## ملاحظات
- المعرف بيتولد مرة وحدة وبيثبت، وبس المالك بيغيّره يدوياً.
- الرصيد بيتخزن عند العميل بنفس قاعدة البيانات، وقواعد الأمان بتمنع العميل من زيادة رصيده، بس الحماية الكاملة للدفع الحقيقي بتحتاج Cloud Functions.
