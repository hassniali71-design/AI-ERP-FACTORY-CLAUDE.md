<!-- يُحفظ في: <project-repo>/docs/tasks/TASK-NNNN-<slug>.md · المرجع: CLAUDE.md §10 -->
# TASK-NNNN — <عنوان واضح>

| | |
|---|---|
| **PROJECT** | <project-name> |
| **TYPE** | Feature / Bug / Refactor / Database / Deployment / Documentation |
| **STATUS** | Draft / Approved / In Progress / Done / Blocked |
| **SOURCE** | <FEAT-NNNN / BUG-NNNN / طلب المالك بتاريخ> |
| **CREATED** | YYYY-MM-DD |

## GOAL
<ما الهدف في جملة أو اثنتين؟>

## BUSINESS CONTEXT
<لماذا نحتاج هذا؟ من المستفيد؟>

## SCOPE
- In: <ما سيتم تعديله>
- Out: <ما هو خارج النطاق صراحة>

## TARGET
<الملفات / modules المتوقع تأثرها — بعد Search، وليس تخمينًا>

## CONSTRAINTS
- <ما يجب عدم تغييره: Business Rules، Stack، صلاحيات، schema…>
- يشمل تغيير Database؟ نعم → أرفق [DATABASE_CHANGE](../DATABASE_CHANGE/DATABASE_CHANGE.md)

## EXPECTED RESULT
<ما النتيجة المطلوبة من منظور المستخدم>

## VALIDATION
- [ ] `bun run build` نظيف
- [ ] `bun run lint` نظيف
- [ ] <سيناريو الاختبار الأساسي>
- [ ] <حالة خطأ مهمة / حدود صلاحيات / عزل tenant إن وُجد>

## DONE WHEN
- [ ] Validation كلها ✅ أو موثق سبب عدم تشغيلها (`Not Tested`)
- [ ] Report مكتوب ([REPORT](../REPORT/REPORT.md))
- [ ] `docs/03-STATE.md` محدث بسطر
- [ ] لا تغييرات جانبية غير مقصودة (`git diff` مراجَع)

## OPEN QUESTIONS
- <ما هو غير معروف ويحتاج قرار المالك قبل/أثناء التنفيذ>
