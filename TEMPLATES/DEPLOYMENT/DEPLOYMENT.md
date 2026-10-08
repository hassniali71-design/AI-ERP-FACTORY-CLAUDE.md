<!-- يُحفظ في: <project-repo>/docs/reports/DEPLOY-YYYY-MM-DD.md
     النشر على Production يحتاج موافقة المالك. لا Secrets في هذا الملف. -->
# DEPLOYMENT — <project-name> · YYYY-MM-DD

| | |
|---|---|
| **TARGET** | Production / Staging |
| **PLATFORM** | <Cloudflare Workers / ...> |
| **COMMIT** | <hash> على <branch> |
| **PREVIOUS DEPLOY** | <hash/تاريخ — نقطة الرجوع> |
| **APPROVED BY** | <المالك · تاريخ> |
| **STATUS** | Planned / Deployed / Rolled Back / Failed |

## Included
- <TASK-ID / BUG-ID> — <عنوان>

## Pre-Deploy Checklist
- [ ] `git status` نظيف، والـcommit موجود على GitHub
- [ ] `bun run build` ✅ · `bun run lint` ✅
- [ ] Database migrations المطلوبة: <لا يوجد / مطبقة / ستُطبق قبل النشر> — انظر DATABASE_CHANGE
- [ ] Environment variables جديدة؟ <الأسماء فقط> — مضبوطة على المنصة
- [ ] Backup حديث إذا يوجد DB change Medium/High
- [ ] خطة Rollback واضحة (أدناه)

## Deploy
```bash
<الأمر المستخدم فعليًا، مثل: bun run deploy>
```

## Post-Deploy Health
- [ ] الموقع يفتح (<URL>)
- [ ] Login يعمل
- [ ] <المسار الأساسي للميزة الجديدة>
- [ ] لا أخطاء جديدة في logs
- النتيجة: Healthy / Degraded / Down

## Rollback Plan
<كيف نرجع للـPREVIOUS DEPLOY — وماذا عن الـmigrations؟>

## Notes / Issues
- <...>

بعد النشر: حدّث `docs/03-STATE.md` (آخر Deployment) + Status في بطاقة الـFactory.
