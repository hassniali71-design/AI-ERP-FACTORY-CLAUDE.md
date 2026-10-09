# Factory Decisions Log

> قرارات على مستوى المصنع. قرارات كل مشروع تعيش في repo المشروع.
> لا يُعاد فتح قرار بدون سبب؛ التغيير = قرار جديد يشير للقديم.

---

### DEC-0001 — taqseet-erp هو أول Pilot Project
- **DATE:** 2026-10-08 · **STATUS:** Active
- **CONTEXT:** ثلاثة مشاريع حقيقية موجودة؛ نحتاج مشروعًا واحدًا لتجربة الـWorkflow.
- **DECISION:** taqseet-erp هو الـPilot. باقي المشاريع تبقى كما هي بدون تغيير.
- **WHY:** الأنضج توثيقًا (`docs/` مرقمة) ونشرًا (Cloudflare deploy script).
- **CONSEQUENCES:** بطاقة مشروع واحدة فقط في Phase 1؛ باقي المشاريع مسجلة في الفهرس فقط.

### DEC-0002 — Context المشروع يعيش في repo المشروع
- **DATE:** 2026-10-08 · **STATUS:** Active
- **DECISION:** التفاصيل الحقيقية داخل repo المشروع. الـFactory يحتفظ ببطاقة + metadata + روابط + حالة + معلومات تشغيلية فقط.
- **WHY:** منع مصدرين متضاربين للحقيقة.
- **CONSEQUENCES:** لا نسخ لملفات المشاريع إلى الـFactory. البطاقة تشير لملفات الـrepo.

### DEC-0003 — لا حذف للنسخ المكررة من الـFactory قبل الموافقة
- **DATE:** 2026-10-08 · **STATUS:** Active
- **DECISION:** فحص وتحديد النسخة الرسمية فقط؛ الحذف بموافقة صريحة.

### DEC-0004 — `D:\New folder (2)` لا يُعدَّل
- **DATE:** 2026-10-08 · **STATUS:** Active
- **DECISION:** فحص فقط. النتيجة: نسخة مطابقة (hash) لـ `superflow-eg/supabase/` — انظر تقرير Phase 1.

### DEC-0005 — إصلاح `.env` في superflow-eg بشكل آمن
- **DATE:** 2026-10-08 · **STATUS:** Active
- **DECISION:** إضافة `.env` لـ`.gitignore`، إزالته من التتبع مع إبقاء الملف المحلي، إنشاء `.env.example`. لا rotation بدون إبلاغ المالك.

### DEC-0006 — Claude هو الـCore؛ Lovable/Cursor أدوات مساعدة
- **DATE:** 2026-10-08 · **STATUS:** Active
- **DECISION:** Claude Chat للتخطيط، Claude Code للتنفيذ، Agents/Sessions لاحقًا. Lovable/Cursor عند الحاجة، والتغييرات المهمة تمر عبر Git وWorkflow المصنع.
- **CONSEQUENCES:** انظر [AI_WORKFLOW.md](AI_WORKFLOW.md).

### DEC-0007 — تجهيز Git و Bun بدون تعديلات حساسة
- **DATE:** 2026-10-08 · **STATUS:** Active
- **DECISION:** لا تعديل لإعدادات Windows الحساسة، لا حذف/استبدال أدوات، أي Admin أو تعديل PATH يُعرض على المالك أولًا.

---

### DEC-0008 — Git CLI
- **DATE:** 2026-10-09 · **STATUS:** Active
- **DECISION (المالك):** إضافة git الخاص بـGitHub Desktop إلى User PATH فقط، بدون Admin.
- **ما حدث فعليًا:** عند التنفيذ تبيّن أن **Git for Windows 2.56** مثبت بالفعل في `C:\Program Files\Git` وموجود في System PATH (ثُبّت 2026-10-08 14:11، بعد Discovery). الإدخال المضاف لـUser PATH كان زائدًا ومرتبطًا برقم إصدار GitHub Desktop (`app-3.6.6`)، فأُعيد User PATH لحالته الأصلية (مطابق للنسخة الاحتياطية).
- **CONSEQUENCES:** `git` = `C:\Program Files\Git\cmd\git.exe` (2.56.0). لم يُعدَّل System PATH ولم يُلمس GitHub Desktop.

### DEC-0009 — مفاتيح superflow-eg: لا rotation ولا rewrite للتاريخ
- **DATE:** 2026-10-09 · **STATUS:** Active
- **DECISION:** لا rotation، لا حذف history، لا force push. `.env` يبقى محليًا ومستثنى في `.gitignore`، و`.env.example` بدون قيم.
- **CONSEQUENCES:** الموضوع **مفتوح** حتى مراجعة RLS على مستوى الجداول.

### DEC-0010 — النسخة المكررة من الـFactory تبقى
- **DATE:** 2026-10-09 · **STATUS:** Active
- **DECISION:** `D:\AI ERP FACTORY — CLAUDE.md` نسخة قديمة/مكررة غير مرتبطة بـGitHub — **لا تُحذف**. النسخة الرسمية: `D:\AI-ERP-FACTORY-CLAUDE.md`.

### DEC-0011 — `D:\New folder (2)` يبقى كنسخة احتياطية
- **DATE:** 2026-10-09 · **STATUS:** Active
- **DECISION:** نسخة احتياطية مؤكدة لـ`superflow-eg/supabase`. لا حذف ولا نقل. التنظيف لاحقًا بعد التأكد من حفظ الأصول.

### DEC-0012 — بيانات taqseet-erp الناقصة = Needs Owner Input
- **DATE:** 2026-10-09 · **STATUS:** Active
- **DECISION:** Production URL، Domain، Supabase Project ID تُسجَّل `Needs Owner Input` ولا تُخمَّن. تُملأ عند Baseline.

### DEC-0013 — Tasks/Reports داخل repo المشروع
- **DATE:** 2026-10-09 · **STATUS:** Active · يكمّل DEC-0002
- **DECISION:** التفاصيل الفنية والمهام والتقارير الخاصة بكل مشروع داخل repo المشروع. الـFactory يحتفظ فقط بـ: Project card، Status، Repository reference، Current phase، Important decisions، Operational metadata.

### DEC-0014 — taqseet-erp: دفتر واحد (`main`)
- **DATE:** 2026-10-09 · **STATUS:** Active
- **DECISION (المالك):** "خلي دفتر واحد" — `main` هو الـbranch الوحيد للعمل والنشر في taqseet-erp.
- **ما حدث:** `main` اتعمله fast-forward ليحتوي كل شغل `claude/quirky-shannon-3fv54p` (بنود 65–68 + التقارير) بدون أي conflict، والـbranch الجانبي اتمسح محليًا (كان مطابقًا لـ`main` بنفس الـcommit `2984022`).
- **CONSEQUENCES:** على GitHub ما زال `origin/main` متأخرًا 5 commits، و`origin/claude/quirky-shannon-3fv54p` موجود — يتحلّوا عند أول Push بموافقة المالك. أي نشر قادم يكون من `main` فقط.
