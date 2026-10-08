# Project Card — taqseet-erp

> **Factory Status:** Pilot Project (DEC-0001) · **Current Phase:** Waiting for Phase 3 — Pilot Baseline (read-only)
> **Card updated:** 2026-10-08
> هذه بطاقة فقط. **مصدر الحقيقة = repo المشروع** (DEC-0002). لا تنسخ محتوى من الـrepo إلى هنا.

## Identity

| البند | القيمة |
|---|---|
| الاسم | taqseet-erp (العلامة: حسبة HESBA — حسب `docs/04-BRAND.md`) |
| الوصف | ERP SaaS متعدد المستأجرين لمحلات الأجهزة الكهربائية والمنزلية والبيع بالتقسيط (مصر)، عربي RTL |
| نوع النظام | Multi-tenant SaaS ERP |
| السوق | مصر |
| Repository | https://github.com/hassniali71-design/taqseet-erp |
| Local path | `D:\taqseet-erp` |
| Default branch | `main` |
| Production URL | **Needs Owner Input** (DEC-0012) |
| Domain | **Needs Owner Input** (DEC-0012) |
| Supabase Project ID | **Needs Owner Input** (DEC-0012) — لا يوجد `supabase/config.toml` في الـrepo |

## Stack

يطابق [STANDARD_STACK](../../COMPANY_OS/STANDARD_STACK.md) بالكامل. المرجع: `docs/02-STACK.md`.
Deployment: Cloudflare Workers (`bun run deploy` → `nitro deploy --prebuilt`).

## Operational Info (أسماء فقط — بدون قيم)

- **Env vars** (من `.env.example`): `SUPABASE_URL`, `SUPABASE_ANON_KEY`, `SUPABASE_SERVICE_ROLE_KEY`, `VITE_SUPABASE_URL`, `VITE_SUPABASE_ANON_KEY`, `TWILIO_ACCOUNT_SID`, `TWILIO_AUTH_TOKEN`, `TWILIO_SMS_FROM`, `TWILIO_WHATSAPP_FROM`
- **Integrations:** Supabase, Twilio (SMS / WhatsApp)
- **CI:** GitHub Action `supabase-keep-alive.yml` — ping يومي لمنع إيقاف Supabase free tier (مؤشر أن المشروع على **Free plan**؛ يُحذف عند الانتقال لـPro).
- **Migrations:** 24 ملف (`supabase/migrations/0001…0024`)
- **Secrets hygiene:** `.env` غير متتبع ✅، `.env.example` موجود ✅

## Where the truth lives (داخل الـrepo)

| الحاجة | الملف |
|---|---|
| ابدأ هنا كل جلسة | `CLAUDE.md` |
| الحالة الحالية + آخر بند | `docs/03-STATE.md` |
| الفيتشرز المنفذة | `docs/05-IMPLEMENTED.md` |
| المؤجَّل | `docs/06-PLAN.md` |
| Business Rules | `docs/07-RULES.md`, `docs/08-FINANCE.md` |
| قواعد العمل + Routing gotcha | `docs/09-WORKFLOW.md` |
| Spec كامل | `docs/ERP_SaaS_Requirements.md` (كبير — يُقرأ عند الحاجة فقط) |

## Status Snapshot (2026-10-08)

- آخر بند عمل: **64** (حسب `docs/03-STATE.md`)
- آخر commit: 2026-09-27
- Working tree: clean
- Build/Lint: **Not Tested** في هذه الجلسة

## Gaps vs Factory Template

(مقارنة بـ [PROJECT_STANDARDS](../../COMPANY_OS/PROJECT_STANDARDS.md) — لا تُنفَّذ بدون Task وموافقة)

- لا يوجد `ARCHITECTURE` / `DATABASE` منفصلان.
- لا يوجد `DECISIONS` log.
- لا يوجد Tasks / Reports workflow رسمي (البنود مسجلة في `03-STATE.md`).
- لا يوجد testing framework.

## Factory Notes

- لا تغيير على هذا المشروع في Phase 1.
