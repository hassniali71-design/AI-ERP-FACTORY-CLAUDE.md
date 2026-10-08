# اقرأ هذا فقط أول كل جلسة (≤ 30 سطر)

**<project-name>**: <وصف في سطر>. عربي RTL.
Stack: Standard Stack — انظر `docs/02-STACK.md`. <أي انحراف>

**قوانين القراءة (توفير Context):**
- لا تقرأ أي ملف من `docs/` إلا عند الحاجة أو عند ذكره صراحة.
- استثناء دائم: اقرأ `docs/03-STATE.md` مع أي طلب تعديل كود.
- لا تقرأ `node_modules/` أو `.output/` أو `dist/` أبدًا.

**خريطة الملفات:**
`docs/00-SPEC.md` المواصفات · `docs/01-BRIEF.md` الفكرة · `docs/02-STACK.md` أوامر التشغيل · `docs/03-STATE.md` الحالة الآن · `docs/04-ARCHITECTURE.md` المعمارية · `docs/05-DATABASE.md` الجداول وRLS · `docs/06-RULES.md` قواعد لا تُكسر · `docs/07-IMPLEMENTED.md` المنفذ فعليًا · `docs/08-PLAN.md` المؤجل · `docs/09-WORKFLOW.md` قواعد العمل · `docs/DECISIONS.md` القرارات · `docs/tasks/` · `docs/reports/`

**خريطة الكود:** `src/routes/` الصفحات · `<data layer path>` طبقة البيانات · `supabase/migrations/` الـSchema.

**قواعد:**
- كل عمل = Task (`docs/tasks/`) وينتهي بـReport (`docs/reports/`).
- بعد كل تعديل: سطر في `docs/03-STATE.md`.
- `bun run build` و`bun run lint` يجب أن يبقيا نظيفين.
- لا Secrets في Git. لا Commit/Push بدون طلب المالك.
- Factory: https://github.com/hassniali71-design/AI-ERP-FACTORY-CLAUDE.md
