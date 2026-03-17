# 🚀 دليل نشر موقع نادي المحادثة الإنجليزية

## 📋 الخطوة 1: إنشاء حساب GitHub

1. اذهب إلى [github.com](https://github.com)
2. اضغط **Sign Up**
3. أنشئ حساب جديد
4. تحقق من البريد الإلكتروني

---

## 📋 الخطوة 2: إنشاء Repository جديد

1. بعد تسجيل الدخول، اضغط **+** في الأعلى
2. اختر **New repository**
3. اسم المستودع: `ecc-website`
4. اجعله **Private** أو **Public**
5. اضغط **Create repository**

---

## 📋 الخطوة 3: رفع الكود إلى GitHub

### تحميل الكود:
- الكود متوفر في الملف: `ecc-website-source.zip`

### طريقة الرفع:

**الخيار A: من المتصفح**
1. افتح repository الذي أنشأته
2. اضغط **uploading an existing file**
3. اسحب الملفات وأفلتها
4. اضغط **Commit changes**

**الخيار B: من Terminal**
```bash
# فك ضغط الملف
unzip ecc-website-source.zip

# الذهاب للمجلد
cd ecc-website

# تهيئة Git
git init
git add .
git commit -m "Initial commit"

# ربط بـ GitHub
git remote add origin https://github.com/YOUR_USERNAME/ecc-website.git
git branch -M main
git push -u origin main
```

---

## 📋 الخطوة 4: إنشاء قاعدة بيانات مجانية (Neon)

1. اذهب إلى [neon.tech](https://neon.tech)
2. اضغط **Sign Up** (سجل بـ GitHub أسهل)
3. بعد الدخول، اضغط **Create a project**
4. سمِّه: `ecc-database`
5. اختر Region قريب منك
6. اضغط **Create project**
7. **انسخ Connection String** (DATABASE_URL)
   ```
   postgresql://username:password@ep-xxx.region.aws.neon.tech/neondb?sslmode=require
   ```

---

## 📋 الخطوة 5: نشر الموقع على Vercel

### 5.1 إنشاء حساب Vercel
1. اذهب إلى [vercel.com](https://vercel.com)
2. اضغط **Sign Up**
3. اختر **Continue with GitHub**
4. امنح الصلاحيات المطلوبة

### 5.2 استيراد المشروع
1. في لوحة التحكم، اضغط **Add New...**
2. اختر **Project**
3. اختر repository: `ecc-website`
4. اضغط **Import**

### 5.3 إعداد المشروع
- **Framework Preset:** Next.js (سيكتشف تلقائياً)
- **Root Directory:** `./`
- **Build Command:** `prisma generate && next build`
- **Output Directory:** `.next`

### 5.4 إضافة متغيرات البيئة

اضغط **Environment Variables** وأضف:

```
DATABASE_URL
```
القيمة: `postgresql://...` (من Neon)

```
RESEND_API_KEY
```
القيمة: `re_Cvn2Cx5e_4vuDS2EN7U2GU2KMzjXFYFrc`

```
NEXTAUTH_SECRET
```
القيمة: (أنشئ كلمة عشوائية مثل: `ecc-tripoli-2024-secret-key-xyz123`)

```
NEXTAUTH_URL
```
القيمة: `https://your-project-name.vercel.app`

### 5.5 النشر
1. اضغط **Deploy**
2. انتظر 2-3 دقائق
3. 🎉 **تم النشر بنجاح!**

---

## 📋 الخطوة 6: إنشاء المالك الأول

### عبر Terminal في Vercel:
1. اذهب إلى مشروعك على Vercel
2. اضغط **Storage** → **Neon** → **Query**
3. شغّل هذا SQL:

```sql
INSERT INTO "User" (id, email, name, role, "createdAt", "updatedAt")
VALUES (
  'owner_001',
  'hussien199919@gmail.com',
  'Hussien',
  'owner',
  NOW(),
  NOW()
);

INSERT INTO "SiteSetting" (id, key, value, "updatedAt")
VALUES (
  'owner_key_001',
  'owner_key',
  'ECC-8BCC1756D6F5BC6A',
  NOW()
);
```

---

## ✅ تم! الآن:

| الرابط | الاستخدام |
|--------|----------|
| `https://your-site.vercel.app` | الموقع للجمهور |
| `https://your-site.vercel.app/api` | API endpoints |

---

## 🔐 معلومات الدخول:

| الدور | البريد | كلمة المرور/المفتاح |
|-------|--------|-------------------|
| **Owner** | hussien199919@gmail.com | `ECC-8BCC1756D6F5BC6A` |
| **Admin** | (أي بريد) | كلمة المرور + `ECC-ADMIN-2024` |
| **Moderator** | (أي بريد) | كلمة المرور + `ECC-MOD-2024` |

---

## 🆘 حل المشاكل:

### الموقع لا يعمل:
1. تحقق من DATABASE_URL
2. تحقق من Logs في Vercel

### قاعدة البيانات لا تتصل:
1. تأكد من صحة DATABASE_URL
2. تأكد من أن IP غير محظور في Neon

### البريد لا يُرسل:
1. تحقق من RESEND_API_KEY
2. تأكد من أن البريد المستهدف مسجل في Resend (للتجربة)

---

## 📞 روابط مفيدة:

- **Vercel Dashboard:** vercel.com/dashboard
- **Neon Dashboard:** console.neon.tech
- **Resend Dashboard:** resend.com/dashboard
- **GitHub Repo:** github.com/YOUR_USERNAME/ecc-website
