# NEW_PROJECT — خطوات إنشاء مشروع جديد

> المرجع: CLAUDE.md §21 + [PROJECT_STANDARDS](../../COMPANY_OS/PROJECT_STANDARDS.md). الهيكل مأخوذ من نمط taqseet-erp المجرَّب.

## الخطوات

| # | الخطوة | الناتج | موافقة المالك؟ |
|---|---|---|---|
| 1 | **Understand** — املأ [SPECIFICATION.md](SPECIFICATION.md) §1–§4 من فكرة المالك | Idea مكتوبة | — |
| 2 | **Specification** — أكمل SPECIFICATION.md (MVP، أدوار، قيود) | Spec | ✅ قبل الاستمرار |
| 3 | **Architecture** — Standard Stack ([STANDARD_STACK](../../COMPANY_OS/STANDARD_STACK.md)) + أي انحراف مُبرَّر | `docs/04-ARCHITECTURE.md` | ✅ إذا يوجد انحراف |
| 4 | **Repository** — إنشاء repo على GitHub (`hassniali71-design/<name>`) | repo | ✅ |
| 5 | **Project Context** — انسخ `CLAUDE.md` + `docs/` + `.env.example` + `gitignore.txt` (كـ`.gitignore`) إلى الـrepo واملأها | Context files | — |
| 6 | **Factory Card** — انسخ [PROJECT_CARD.md](PROJECT_CARD.md) إلى `PROJECTS/<name>/PROJECT.md` في الـFactory + سطر في `PROJECTS/README.md` | بطاقة | — |
| 7 | **MVP** — قسّم إلى Tasks ([TASK](../TASK/TASK.md)) — ابدأ بأساس صغير قابل للتشغيل | `docs/tasks/` | ✅ قائمة الـTasks |
| 8 | **Validate** — Report لكل Task ([REPORT](../REPORT/REPORT.md)) | `docs/reports/` | — |

## الملفات

```text
TEMPLATES/NEW_PROJECT/
├── README.md            (هذا الملف)
├── SPECIFICATION.md     Idea → Spec (يُحفظ في الـrepo كـ docs/00-SPEC.md)
├── PROJECT_CARD.md      بطاقة الـFactory (PROJECTS/<name>/PROJECT.md)
├── CLAUDE.md            يُنسخ لجذر الـrepo
├── .env.example         نقطة بداية — أسماء فقط
├── gitignore.txt        يُنسخ كـ .gitignore (الاسم مختلف حتى لا يؤثر على الـFactory)
└── docs/
    ├── 01-BRIEF.md   02-STACK.md   03-STATE.md
    ├── 04-ARCHITECTURE.md   05-DATABASE.md   06-RULES.md
    ├── 07-IMPLEMENTED.md   08-PLAN.md   09-WORKFLOW.md
    └── DECISIONS.md
```

مجلدات تُنشأ عند أول استخدام: `docs/tasks/`, `docs/reports/`, `docs/features/`.

## Checklist أمان قبل أول commit
انظر [SECURITY_RULES](../../COMPANY_OS/SECURITY_RULES.md) — `.env` غير متتبع، `.env.example` بأسماء فقط، RLS من أول migration.
