# 🚀 دليل نشر موقع نادي المحادثة الإنجليزية

## 📋 المتطلبات

1. حساب GitHub
2. حساب Vercel أو Railway
3. قاعدة بيانات PostgreSQL (Neon أو Supabase)

---

## 🔧 الخطوة 1: إعداد قاعدة البيانات (Neon - مجاني)

1. اذهب إلى [neon.tech](https://neon.tech)
2. سجل حساب جديد (مجاني)
3. أنشئ مشروع جديد
4. انسخ `DATABASE_URL`

---

## 🔧 الخطوة 2: تحويل Prisma لـ PostgreSQL

### تغيير ملف `prisma/schema.prisma`:

```prisma
datasource db {
  provider = "postgresql"
  url      = env("DATABASE_URL")
}
```

### متغيرات البيئة المطلوبة:

```env
# قاعدة البيانات
DATABASE_URL="postgresql://user:password@host:5432/dbname?sslmode=require"

# خدمة البريد الإلكتروني
RESEND_API_KEY="re_Cvn2Cx5e_4vuDS2EN7U2GU2KMzjXFYFrc"

# WhatsApp (اختياري - Twilio)
TWILIO_ACCOUNT_SID=""
TWILIO_AUTH_TOKEN=""
TWILIO_WHATSAPP_NUMBER=""
```

---

## 🔧 الخطوة 3: النشر على Vercel

### الطريقة 1: من GitHub

1. ارفع الكود إلى GitHub
2. اذهب إلى [vercel.com/new](https://vercel.com/new)
3. اختر المشروع
4. أضف متغيرات البيئة
5. اضغط Deploy

### الطريقة 2: من Vercel CLI

```bash
# تثبيت Vercel CLI
npm i -g vercel

# تسجيل الدخول
vercel login

# نشر المشروع
vercel --prod
```

---

## 🔧 الخطوة 4: النشر على Railway

1. اذهب إلى [railway.app](https://railway.app)
2. سجل بـ GitHub
3. اضغط "New Project"
4. اختر "Deploy from GitHub repo"
5. اختر المشروع
6. أضف PostgreSQL:
   - اضغط "+" 
   - اختر "PostgreSQL"
7. أضف متغيرات البيئة
8. Railway سينشئ `DATABASE_URL` تلقائياً

---

## ⚠️ ملاحظات مهمة

### للإنتاج:

1. **غيّر كلمات المرور الافتراضية:**
   ```
   Setup Key: ecc-tripoli-owner-2024 ← غيّره!
   Admin Code: ECC-ADMIN-2024 ← غيّره!
   Moderator Code: ECC-MOD-2024 ← غيّره!
   ```

2. **أضف متغيرات جديدة:**
   ```env
   NEXTAUTH_SECRET="your-random-secret-here"
   NEXTAUTH_URL="https://your-domain.vercel.app"
   ```

3. **أضف دومين مخصص (اختياري):**
   - Vercel: Project Settings → Domains
   - Railway: Settings → Domains

---

## 📞 للدعم

- **Vercel Docs:** vercel.com/docs
- **Railway Docs:** docs.railway.app
- **Neon Docs:** neon.tech/docs

---

## 🔑 معلومات المالك

- **البريد:** hussien199919@gmail.com
- **مفتاح المالك:** ECC-8BCC1756D6F5BC6A
- **كود المشرف:** ECC-ADMIN-2024
- **كود المراقب:** ECC-MOD-2024
