<!-- يُحفظ في: <project-repo>/docs/reports/REPORT-<TASK-ID>.md · المرجع: CLAUDE.md §11–§12
     ممنوع تقرير مضلل: ما لم يُشغَّل = Not Tested. -->
# REPORT — <TASK-ID>

```text
TASK:              <TASK-ID> — <العنوان>
STATUS:            Completed / Partially Completed / Blocked / Needs Review
DATE:              YYYY-MM-DD
BRANCH / COMMIT:   <branch> · <hash أو "not committed">

SUMMARY:
<2–4 أسطر: ماذا تم ولماذا>

FILES CHANGED:
- <path> — <سبب>

FILES CREATED:
- <path>

FILES DELETED:
- <path> — <سبب + كيف تحققت أنه غير مستخدم>

DATABASE CHANGES:
<لا يوجد / migration: <file> — مطبقة على: local / staging / production / غير مطبقة>

API CHANGES:
<لا يوجد / ...>

TESTS:
- <الاختبار> → Passed / Failed / Not Tested

BUILD:
bun run build → Passed / Failed / Not Tested
bun run lint  → Passed / Failed (<N> errors, <N> warnings) / Not Tested

DEPLOYMENT:
<لا يوجد / DEPLOY-YYYY-MM-DD>

KNOWN ISSUES:
- <مشكلة موجودة/جديدة — لا تُخفى>

NEXT ACTION:
<الخطوة التالية المقترحة>

NOTES:
<قرارات صغيرة اتُّخذت أثناء التنفيذ + سببها>
```

## Definition of Done Check
- [ ] المطلوب الأساسي يعمل
- [ ] Business Rules محفوظة
- [ ] الصلاحيات / عزل tenants صحيح
- [ ] حالات الخطأ المهمة معالجة
- [ ] لا تغييرات جانبية غير مقصودة
- [ ] Build/Lint ✅
- [ ] Documentation + `docs/03-STATE.md` محدثة
