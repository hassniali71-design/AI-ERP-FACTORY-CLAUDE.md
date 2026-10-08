# FACTORY DISCOVERY — Phase 0

> التاريخ: 2026-10-08
> المنفذ: Claude Code
> الحالة: **Needs Review** — بانتظار قرارات صاحب المشروع
> النطاق: فحص المستودع + البيئة المحلية + المشاريع المرتبطة (metadata فقط، بدون قراءة بيانات أعمال أو قيم Secrets)

---

## 1. Current State

- المستودع `AI-ERP-FACTORY-CLAUDE.md` في مرحلته الأولى: commitان فقط (`Initial commit` + `Add files via upload`).
- Remote: `https://github.com/hassniali71-design/AI-ERP-FACTORY-CLAUDE.md.git` — branch `main`، الحالة clean.
- المحتوى الحالي: `README.md` (سطر وصف) + ملف التعليمات باسم **`CLAUDE (1).md`** (وليس `CLAUDE.md`).
- لا توجد بعد أي من مجلدات الهيكل المستهدف (`COMPANY_OS/`, `PROJECTS/`, `TEMPLATES/` …).

### البيئة المحلية (Windows 11)

| الأداة | الحالة |
|---|---|
| Node | v22.18.0 ✅ |
| npm | 10.9.3 ✅ |
| VS Code | موجود ✅ |
| git | **غير موجود في PATH** — متاح فقط داخل GitHub Desktop (bundled) |
| gh (GitHub CLI) | غير موجود |
| bun | **غير موجود** — رغم أن كل المشاريع تستخدم `bun.lock` وسكربتات `bun run` |
| supabase CLI | غير موجود |
| wrangler / Cloudflare CLI | غير موجود |
| Python | غير موجود (alias المتجر فقط) |

---

## 2. Existing Structure

### المستودع الحالي
```text
AI-ERP-FACTORY-CLAUDE.md/
├── CLAUDE (1).md
└── README.md
```

### مشاريع حقيقية مرتبطة على نفس الجهاز (`D:\`)

| المشروع | Repository | Migrations | آخر Commit | ملفات Context موجودة |
|---|---|---|---|---|
| **taqseet-erp** | `hassniali71-design/taqseet-erp` | 24 | 2026-09-27 | `CLAUDE.md` + `docs/01-BRIEF … 09-WORKFLOW` + `ERP_SaaS_Requirements.md` + GitHub workflow (`supabase-keep-alive.yml`) |
| **The-Educational-Center** | `hassniali71-design/The-Educational-Center` | 36 | 2026-10-03 | `CLAUDE.md`, `AGENTS.md`, `AI_AGENT_HANDOFF_LATEST.md`, عدة `*_SPEC.md`, `report.md` |
| **superflow-eg** | `hassniali71-design/superflow-eg` | 10 | 2026-10-07 | `AGENTS.md`, `CLAUDE_1.md` — يوجد ملف واحد معدل غير محفوظ (uncommitted) |

### الـStack الفعلي (موحد فعليًا في الثلاثة)

- **Frontend/Fullstack:** React + TanStack Start / TanStack Router + Vite + TypeScript
- **UI:** Tailwind CSS v4 + shadcn/ui (`components.json`) + lucide-react
- **Validation:** zod
- **Backend/DB/Auth:** Supabase (supabase-js + migrations)
- **Package manager:** bun
- **Generator الأصلي:** Lovable (`@lovable.dev/vite-tanstack-config`, مجلد `.lovable`)
- **Deployment (taqseet-erp):** Cloudflare عبر `nitro deploy --prebuilt` + سكربت `fix-cloudflare-chunks.ts`

> الخلاصة: يوجد **Standard Stack فعلي غير موثق** — يكفي توثيقه، لا حاجة لاختيار Stack جديد.

### Standards موجودة بالفعل

- `taqseet-erp/docs/` يحتوي على هيكل Context مرقم ناضج (BRIEF / STACK / STATE / BRAND / IMPLEMENTED / PLAN / RULES / FINANCE / WORKFLOW). هذا أقرب شيء لـ Standard فعلي ويصلح كأساس لـ `TEMPLATES/NEW_PROJECT`.
- `The-Educational-Center` يستخدم نمط Handoff + Spec files منفصلة.
- **النمطان مختلفان** — لا يوجد Template موحد بين المشاريع.

### ملفات/مجلدات أخرى ذات صلة

- `D:\AI ERP FACTORY — CLAUDE.md\` — نسخة محلية ثانية بنفس الاسم تقريبًا، تحتوي `.gitattributes` فقط، بـ commit مختلف (`67d0a47`) وبدون remote.
- `D:\New folder (2)\` — يحتوي `migrations/` (10 ملفات) + `runbooks/seed_demo_tenant_history.sql` + `config.toml` + نسخ zip. غير معروف لأي مشروع تنتمي (عدد الـmigrations = 10 يطابق superflow-eg، لكن غير مؤكد).

---

## 3. Missing Components

1. **`CLAUDE.md` بالاسم الصحيح** — الملف الحالي `CLAUDE (1).md` لن يُحمَّل تلقائيًا بواسطة Claude Code في الجلسات القادمة.
2. `COMPANY_OS/` كاملًا — خاصة `STANDARD_STACK.md` (الـStack موجود فعليًا لكنه غير موثق) و`GIT_STANDARDS.md` و`SECURITY_RULES.md`.
3. `PROJECTS/` — لا يوجد تسجيل للمشاريع الثلاثة داخل المصنع.
4. `TEMPLATES/` — لا يوجد Template موحد للمشروع الجديد / Task / Report / Decision.
5. `CHANGELOG.md` على مستوى المصنع.
6. `.gitignore` في مستودع المصنع.
7. أدوات CLI أساسية في البيئة: `git` في PATH، `bun`، و(اختياريًا) `gh` و`supabase` CLI. بدونها لا أستطيع تشغيل build/test أو عمل commit من الجلسة.

---

## 4. Risks

| # | الخطر | الشدة | التفاصيل |
|---|---|---|---|
| R1 | **`.env` مُتتبَّع في Git في superflow-eg** | متوسطة | `.gitignore` لا يستثني `.env`، والملف داخل الـrepo. المتغيرات الموجودة (أسماء فقط): `SUPABASE_URL`, `SUPABASE_PROJECT_ID`, `SUPABASE_PUBLISHABLE_KEY` ونسخ `VITE_*`. هذه مفاتيح **publishable/anon** (عامة بطبيعتها) وليست service-role، لذلك الخطر المباشر منخفض **بشرط أن RLS مفعّل وصحيح**. لكنه يخالف القاعدة #26 ويجب إصلاحه قبل إضافة أي Secret حقيقي. |
| R2 | تعارض نسخ المصنع | منخفضة | مجلدان محليان بنفس الفكرة وتاريخ Git مختلف — خطر العمل في النسخة الخطأ. |
| R3 | Migrations يتيمة في `New folder (2)` | متوسطة | ملفات SQL خارج أي repo + seed لـ demo tenant. خطر التطبيق على المشروع/الـDB الخطأ أو فقدانها. |
| R4 | لا يمكن التحقق (Build/Test) محليًا | متوسطة | غياب `bun` و`git` من PATH يعني أن أي Task تنفيذية ستنتهي بـ `Not Tested`. |
| R5 | تعدد أدوات AI على نفس المشاريع | متوسطة | وجود `.lovable` + `AGENTS.md` + `CLAUDE.md` في نفس المشاريع → خطر تعديل Lovable وClaude لنفس الحالة في نفس الوقت (القاعدة #19). |
| R6 | Context غير موحد | منخفضة | كل مشروع يوثق بطريقة مختلفة → صعوبة التنقل بين المشاريع. |
| R7 | تغيير غير محفوظ في superflow-eg | منخفضة | ملف واحد معدل وغير committed — لن ألمسه. |

---

## 5. Recommended Next Steps

**Phase 1 — Foundation** (صغيرة، آمنة، داخل مستودع المصنع فقط):

1. إعادة تسمية `CLAUDE (1).md` → `CLAUDE.md`.
2. إضافة `.gitignore` + `CHANGELOG.md`.
3. إنشاء `COMPANY_OS/STANDARD_STACK.md` يوثق الـStack الفعلي أعلاه (بدون اختراع).
4. إنشاء `COMPANY_OS/GIT_STANDARDS.md` و`SECURITY_RULES.md` مختصرين، مستخلصين من CLAUDE.md (بدون تكرار مطول).
5. إنشاء `PROJECTS/` بثلاث بطاقات مختصرة (`PROJECT.md` + `CURRENT_STATE.md`) تشير إلى الـrepos الأصلية، مع **الإشارة** إلى docs الموجودة بدل نسخها (لتجنب ازدواجية الحقيقة).

**Phase 2 — Templates:**

6. بناء `TEMPLATES/NEW_PROJECT` اعتمادًا على هيكل `taqseet-erp/docs/` المجرب فعليًا، + Templates لـ Task / Report / Decision.

**إصلاحات خارج مستودع المصنع (تحتاج موافقة):**

7. superflow-eg: إضافة `.env` إلى `.gitignore` وإزالته من التتبع (`git rm --cached .env`) مع إنشاء `.env.example`، والتأكد من أن RLS مفعل على كل الجداول.
8. البيئة: تثبيت `bun` وإضافة `git` إلى PATH (أو تثبيت Git for Windows) — مطلوب لتشغيل Build/Test وcommits من Claude Code.

---

## 6. Decisions Required From Owner

1. **D1 — مكان PROJECTS:** هل نسجل المشاريع الثلاثة (taqseet-erp, The-Educational-Center, superflow-eg) داخل المصنع كبطاقات Context تشير للـrepos؟ وأي مشروع هو **"First Real Project"** للـPhase 3؟ (توصيتي: **taqseet-erp** لأنه الأنضج توثيقًا ونشرًا.)
2. **D2 — مصدر الحقيقة للـContext:** هل يبقى Context التفصيلي داخل repo كل مشروع (`docs/`) والمصنع يحتفظ ببطاقة مختصرة + رابط؟ أم ننقل الـContext بالكامل للمصنع؟ (توصيتي: **يبقى في repo المشروع** — المصنع يحتفظ بالفهرس والحالة فقط، لتجنب نسختين متضاربتين.)
3. **D3 — النسخة المكررة:** ماذا نفعل بـ `D:\AI ERP FACTORY — CLAUDE.md\`؟ (توصيتي: تجاهلها/أرشفتها يدويًا بعد التأكد أنها فارغة — لن أحذفها.)
4. **D4 — `New folder (2)`:** لأي مشروع تنتمي هذه الـmigrations والـrunbook؟
5. **D5 — superflow-eg `.env`:** هل أوافق على إصلاح R1 في repo superflow-eg؟
6. **D6 — Lovable:** هل Lovable ما زال يُستخدم فعليًا على هذه المشاريع؟ إذا نعم، نحتاج قاعدة واضحة: من يعدل ماذا ومتى (Branch منفصل؟).
7. **D7 — البيئة:** هل أثبت/أجهز `bun` و`git` CLI، أم ستقوم بذلك بنفسك؟

---

## 7. Post-Discovery Findings (2026-10-08, بعد قرارات المالك)

### D3 — نسخ الـFactory

| المسار | Remote | Commits | المحتوى | الحكم |
|---|---|---|---|---|
| `D:\AI-ERP-FACTORY-CLAUDE.md` | `origin` → `hassniali71-design/AI-ERP-FACTORY-CLAUDE.md` | 2 (`fbb6ae2`, `9903848`) | CLAUDE.md + README + ملفات Phase 0/1 | **الرسمية** |
| `D:\AI ERP FACTORY — CLAUDE.md` | **لا يوجد** | 1 (`67d0a47` Initial commit، 2026-10-08 01:32) | `.gitattributes` (66 bytes) فقط | مسودة محلية فارغة سابقة |

**لماذا الأولى هي الرسمية:** مرتبطة بـGitHub (Source of Truth حسب §6)، تحتوي ملف التعليمات الفعلي، وأحدث (أُنشئت بعد الثانية بـ~45 دقيقة). الثانية بلا remote وبلا محتوى.
لم يُعثر على نسخ أخرى في `C:` (المسار الوحيد المطابق هو مجلد إعدادات Claude الداخلي) أو `D:`. **لم يُحذف شيء.**
**قرار المالك (DEC-0010):** تبقى النسخة المكررة كما هي؛ مسجلة كقديمة/غير مرتبطة بـGitHub.

### D4 — `D:\New folder (2)`

- 10 migrations + `config.toml` + `runbooks/seed_demo_tenant_history.sql` + 3 ملفات zip.
- **الارتباط مؤكد:** كل الملفات غير المضغوطة **مطابقة بالـSHA256** للملفات المقابلة في `D:\superflow-eg\supabase\` (نفس الأسماء، نفس `project_id`).
- → نسخة احتياطية مطابقة لـ superflow-eg؛ لا تحتوي شيئًا غير موجود في الـrepo. (ملفات الـzip لم تُفك.) **لم يُعدَّل شيء.**
**قرار المالك (DEC-0011):** يبقى كنسخة احتياطية؛ التنظيف لاحقًا.

---

## REPORT

```text
TASK:            Phase 0 — Discovery
STATUS:          Completed (Discovery) / Needs Review (Decisions)
SUMMARY:         فحص المستودع والبيئة و3 مشاريع مرتبطة؛ تحديد Stack فعلي موحد، مخاطر، وخطة Phase 1.
FILES CHANGED:   —
FILES CREATED:   FACTORY_DISCOVERY.md
FILES DELETED:   —
DATABASE CHANGES: —
API CHANGES:     —
TESTS:           Not Applicable
BUILD:           Not Applicable
DEPLOYMENT:      —
KNOWN ISSUES:    R1–R7 أعلاه
NEXT ACTION:     مراجعة القرارات D1–D7 ثم بدء Phase 1 — Foundation
NOTES:           لم تُقرأ قيم أي Secrets ولا بيانات أعمال؛ أسماء متغيرات البيئة فقط. لم يُعدَّل أي مشروع خارج هذا المستودع. لم يتم commit.
```
