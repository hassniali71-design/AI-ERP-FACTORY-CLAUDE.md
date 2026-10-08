# Security Rules

> الحالة: Active — v0.1. مستخلص من CLAUDE.md §16, §18, §25, §26.

## Secrets

- **ممنوع** في Git: passwords, API keys, service-role keys, DB credentials, JWT secrets, tokens.
- كل مشروع يحتوي `.env.example` بأسماء المتغيرات فقط، و`.gitignore` يستثني `.env` و`.env.*`.
- عند إضافة Secret جديد: وثّق **الاسم والغرض** فقط، لا القيمة.
- لا يُطبع أو يُنسخ محتوى `.env` في أي جلسة أو تقرير.
- **Rotation** أي credential تحتاج إبلاغ صاحب المشروع قبل التنفيذ.

### Checklist عند Onboarding أي مشروع

- [ ] `.env` غير متتبع (`git ls-files .env` فارغ).
- [ ] `.gitignore` يحتوي `.env` و `.env.*` و `!.env.example`.
- [ ] `.env.example` موجود بأسماء فقط.
- [ ] لا يوجد service-role key في كود الـFrontend أو متغيرات `VITE_*`.
- [ ] RLS مفعّل على كل الجداول ذات بيانات tenants.

## Multi-Tenant

- عزل الـtenants يُفرض في **Database (RLS) / Backend**، وليس في الـUI.
- إخفاء البيانات في الـFrontend ليس حماية.

## بيانات العملاء

- الـFactory يراقب التشغيل (health, errors, versions, storage) وليس محتوى أعمال العملاء.
- أقل صلاحيات ممكنة دائمًا.

## Database

- أي migration مؤثرة = عملية حساسة: افهم الـschema، تحقق من RLS والـimpact، migration قابلة للتتبع.
- عند احتمال فقد بيانات: **توقف واطلب مراجعة.**

## سجل الحوادث المعروفة

| التاريخ | المشروع | المشكلة | الحالة |
|---|---|---|---|
| 2026-10-08 | superflow-eg | `.env` كان متتبعًا في Git ومرفوعًا على GitHub (مفاتيح publishable/anon فقط) | أُزيل من التتبع محليًا (staged في superflow-eg، بدون commit). يبقى في history — لا rotation ولا rewrite (DEC-0009). **مفتوح** حتى مراجعة RLS. |
