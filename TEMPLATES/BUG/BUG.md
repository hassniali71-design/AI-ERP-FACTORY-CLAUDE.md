<!-- يُحفظ في: <project-repo>/docs/tasks/BUG-NNNN-<slug>.md
     المبدأ: أعد إنتاج المشكلة وحدد السبب الجذري قبل الإصلاح. -->
# BUG-NNNN — <وصف قصير للعَرَض>

| | |
|---|---|
| **PROJECT** | <project-name> |
| **SEVERITY** | Critical (بيانات/أمان/توقف) / High / Medium / Low |
| **STATUS** | Reported / Reproduced / Root Cause Found / Fixed / Verified / Won't Fix |
| **REPORTED** | YYYY-MM-DD · <بواسطة> |
| **ENVIRONMENT** | Production / Local · <URL أو route> · <tenant: نعم/لا — بدون بيانات العميل> |

## Symptom
<ماذا يرى المستخدم؟>

## Expected
<ماذا كان يجب أن يحدث؟>

## Steps to Reproduce
1. <...>
- **Reproduced?** نعم / لا / جزئيًا

## Evidence
<رسالة الخطأ، console، logs — **بدون** Secrets أو بيانات عملاء>

## Root Cause
<السبب الحقيقي — الملف/الـcommit/الـmigration. "غير معروف بعد" مقبول>

## Fix Plan
- <أقل تعديل ضروري>
- يمس Database؟ → [DATABASE_CHANGE](../DATABASE_CHANGE/DATABASE_CHANGE.md)
- خطر الـregression: <ما الذي قد ينكسر؟>

## Verification
- [ ] خطوات إعادة الإنتاج لم تعد تُظهر المشكلة
- [ ] `bun run build` / `bun run lint` نظيفان
- [ ] <سيناريو مجاور للتأكد من عدم الكسر>

## Knowledge
- متكرر/قابل لإعادة الاستخدام؟ نعم → أضفه لـ `KNOWLEDGE_BASE/COMMON_BUGS.md` في الـFactory
