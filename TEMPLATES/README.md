# Factory Templates

> v0.1 — بسيطة وعملية. تُحسَّن بعد الاستخدام الفعلي في Pilot (taqseet-erp).

## دورة العمل

```text
Idea → Specification → Task → Implementation → Test → Report → Context Update
```

| المرحلة | القالب | أين يُحفظ الناتج؟ (DEC-0013) |
|---|---|---|
| Idea → Specification (مشروع جديد) | [NEW_PROJECT/](NEW_PROJECT/) | repo جديد + بطاقة في `PROJECTS/<name>/` بالـFactory |
| Idea → Specification (Feature) | [FEATURE/](FEATURE/) | `docs/features/FEAT-NNNN-<slug>.md` في repo المشروع |
| Bug intake | [BUG/](BUG/) | `docs/tasks/BUG-NNNN-<slug>.md` في repo المشروع |
| Task | [TASK/](TASK/) | `docs/tasks/TASK-NNNN-<slug>.md` في repo المشروع |
| Database change | [DATABASE_CHANGE/](DATABASE_CHANGE/) | ملحق بالـTask + migration في `supabase/migrations/` |
| Test → Report | [REPORT/](REPORT/) | `docs/reports/REPORT-<TASK-ID>.md` في repo المشروع |
| Decision | [DECISION/](DECISION/) | `docs/DECISIONS.md` في repo المشروع (أو `COMPANY_OS/DECISIONS.md` لقرارات المصنع) |
| Deployment | [DEPLOYMENT/](DEPLOYMENT/) | `docs/reports/DEPLOY-YYYY-MM-DD.md` في repo المشروع |
| Context Update | — | `docs/03-STATE.md` في repo المشروع (سطر واحد) + تحديث Status في بطاقة الـFactory عند تغيّر المرحلة |

## قواعد الاستخدام

1. انسخ القالب، احذف التعليمات بين `<!-- -->`، املأ الحقول.
2. حقل غير معروف → `Needs Owner Input` — **لا تخمّن.**
3. لا تملأ نتيجة اختبار لم يُشغَّل → `Not Tested`.
4. لا قيم Secrets في أي قالب — أسماء المتغيرات فقط.
5. مشروع قائم له نمط ترقيم خاص (مثل `بند NN` في taqseet-erp) → يُحترم؛ القالب يتكيف معه لا العكس.

## الترقيم

`TASK-0001`, `BUG-0001`, `FEAT-0001`, `DEC-0001` — عدّاد مستقل لكل مشروع داخل repo المشروع.
