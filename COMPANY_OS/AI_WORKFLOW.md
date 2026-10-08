# AI Workflow

> الحالة: Active — مبني على DEC-0006 (2026-10-08).

## الأدوار

| الأداة | الدور | الحالة |
|---|---|---|
| **Claude Chat** | التفكير، التحليل، التخطيط، تحويل الفكرة إلى Specification | Core |
| **Claude Code** | التنفيذ داخل الـRepository | Core |
| **Claude Agent / Sessions** | مهام متكررة ومراقبة | لاحقًا — بعد استقرار الـWorkflow |
| Lovable / Cursor | أدوات مساعدة عند الحاجة | ليست Core |

## قواعد الأدوات الخارجية (Lovable / Cursor)

1. أي تغيير مهم يمر عبر **Git** و Workflow المصنع (Task → تنفيذ → Report).
2. يُفضَّل Branch منفصل للتغييرات الخارجية المؤثرة.
3. **ممنوع** أن تعدل أداتان نفس الجزء الحساس في نفس الوقت (مثلًا Lovable وClaude Code على نفس الـmigrations).
4. بعد أي تغيير خارجي مؤثر: افحصه، ثم حدّث `CURRENT_STATE` في repo المشروع.

## دورة الجلسة (مختصر CLAUDE.md §23)

```text
Identify Project → Read CLAUDE.md → Read Project Card (PROJECTS/<name>/PROJECT.md)
→ Read project repo's own CLAUDE.md + state file → Inspect Git → Confirm scope
→ Plan → Execute → Validate → Report → Update state
```

## الالتزام

- لا Commit / Push من Claude إلا بطلب صريح من صاحب المشروع.
- كل Task مهمة تنتهي بـ Report (القالب في CLAUDE.md §12).
- لا يُكتب `Completed` لشيء لم يُختبر — استخدم `Not Tested`.
