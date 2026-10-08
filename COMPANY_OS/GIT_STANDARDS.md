# Git Standards

> الحالة: Active — v0.1. التفاصيل الكاملة في CLAUDE.md §6 و §24.

## المبادئ

- **GitHub = Source of Truth للكود.** كل مشروع له Repository مستقل تحت `hassniali71-design`.
- الـFactory repo يحتفظ بالمعرفة والعملية فقط — **لا ينسخ كود المشاريع** (DEC-0002).

## قواعد العمل

1. افحص `git status` و branch الحالي قبل أي تغيير كبير.
2. لا تكتب فوق تغييرات محلية غير متعلقة بالمهمة، ولا تحذفها.
3. Commits صغيرة ومتكررة بوصف واضح — لا commit ضخم يجمع عدة Phases.
4. لا `reset --hard` / `rebase` destructive / `force push` إلا بطلب صريح.
5. **لا Commit أو Push من Claude بدون طلب صريح.**
6. تغييرات أدوات خارجية مؤثرة (Lovable/Cursor) → Branch منفصل.

## Branch naming (مقترح — يُعتمد بعد التجربة في Pilot)

```text
main                 الإنتاج/المرجع
feature/<task-id>-<short-name>
fix/<task-id>-<short-name>
claude/<short-name>  جلسات Claude Code (مستخدم فعليًا في superflow-eg)
```

## Commit message

```text
<TASK-ID>: <وصف قصير واضح>
```

نمط taqseet-erp الحالي (`بند NN: ...`) مقبول داخل ذلك المشروع — لا نغيره.

## البيئة المحلية

- `git` = Git for Windows 2.56 (`C:\Program Files\Git`) عبر System PATH — انظر DEC-0008.
