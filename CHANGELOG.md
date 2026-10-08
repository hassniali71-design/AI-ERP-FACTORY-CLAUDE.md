# Factory Changelog

> تغييرات مؤثرة على مستوى Feature / Architecture / Process. لا يُسجل كل سطر.

---

## 2026-10-09 — Phase 2: Templates

**Project:** AI ERP Factory · **Task:** PHASE-2

**Changed:**
- أُنشئ `TEMPLATES/` + `README.md` (دورة العمل وأين يُحفظ كل ناتج).
- قوالب: `NEW_PROJECT/` (Spec، Project Card، CLAUDE.md، `.env.example`، `gitignore.txt`، `docs/01…09` + DECISIONS)، `TASK/`، `FEATURE/`، `BUG/`، `REPORT/`، `DECISION/`، `DATABASE_CHANGE/`، `DEPLOYMENT/`.
- `COMPANY_OS/PROJECT_STANDARDS.md` → Active، يشير للقوالب.

**Reason:** قرار المالك (2026-10-09) ببدء Phase 2.
**Result:** قوالب v0.1 جاهزة. **غير مستخدمة بعد على مشروع حقيقي** — تُختبر في Phase 3. غير committed.

---

## 2026-10-08 — Phase 1: Foundation

**Project:** AI ERP Factory
**Task:** PHASE-1

**Changed:**
- `CLAUDE (1).md` → `CLAUDE.md` (حتى يُحمَّل تلقائيًا في جلسات Claude Code).
- أُضيف `.gitignore`.
- أُنشئ `COMPANY_OS/`: `STANDARD_STACK`, `AI_WORKFLOW`, `GIT_STANDARDS`, `SECURITY_RULES`, `PROJECT_STANDARDS` (تصميم Template), `DECISIONS` (DEC-0001…0007).
- أُنشئ `PROJECTS/` + فهرس + بطاقة Pilot لـ taqseet-erp.
- `FACTORY_DISCOVERY.md`: أُضيفت نتائج ما بعد الـDiscovery (D3/D4).

**Outside Factory:**
- superflow-eg: `.env` أُضيف لـ`.gitignore` وأُزيل من التتبع (staged، بدون commit)، أُنشئ `.env.example`.
- البيئة: تثبيت Bun 1.2.21 (user-level عبر npm).

**Reason:** قرارات المالك D1–D7 + بدء Phase 1.
**Result:** Foundation جاهزة. قرارات المالك N1–N7 سُجلت كـDEC-0008…0013 (2026-10-09). Commit محلي واحد، بدون Push.

---

## 2026-10-08 — Phase 0: Discovery

- أُنشئ `FACTORY_DISCOVERY.md`.
