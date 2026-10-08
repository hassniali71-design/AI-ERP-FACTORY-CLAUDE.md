# Standard Stack

> الحالة: **Active** — موثق كما اكتُشف فعليًا في Phase 0 (2026-10-08)، **بدون أي تغيير**.
> المصدر: `package.json` في المشاريع الثلاثة + `taqseet-erp/docs/02-STACK.md`.
> أي تغيير على هذا الملف = Decision جديد (انظر [DECISIONS.md](DECISIONS.md)).

## الـStack

| الطبقة | التقنية | ملاحظات |
|---|---|---|
| Framework | **TanStack Start** + TanStack Router (file-based) | الصفحات في `src/routes/` |
| UI Library | **React 19** | |
| Language | **TypeScript** (~5.8) | |
| Build | **Vite** (عبر `@lovable.dev/vite-tanstack-config`) | |
| Styling | **Tailwind CSS v4** (`@theme inline`) | |
| Components | **shadcn/ui** (style: new-york) + lucide-react | `components.json` |
| Data fetching | TanStack Query | |
| Validation | **zod** | |
| Backend / DB | **Supabase** — Postgres + Auth + RLS + Storage | Schema عبر `supabase/migrations/*.sql` |
| Package manager / runtime | **Bun** | `bun.lock` في كل المشاريع |
| Deployment | **Cloudflare Workers** عبر `nitro deploy --prebuilt` | مؤكد في taqseet-erp فقط |
| Language/Direction | عربي **RTL** (`dir="rtl"`, `lang="ar"`) | |
| Scaffolding | Lovable (أداة مساعدة، ليست Core) | انظر DEC-0006 |

## أوامر قياسية

```bash
bun i
bun run dev
bun run build
bun run lint
```

**Build و Lint يجب أن يبقيا نظيفين بعد أي تعديل.**

## الانتشار الفعلي

| المشروع | يطابق الـStack؟ | ملاحظات |
|---|---|---|
| taqseet-erp | ✅ | مرجع النشر (Cloudflare + postbuild `fix-cloudflare-chunks.ts`) |
| The-Educational-Center | ✅ | طريقة النشر غير موثقة في الفحص (لا يوجد `deploy` script) |
| superflow-eg | ✅ | طريقة النشر غير موثقة في الفحص |

## غير محسوم بعد (لا تفترضه)

- طريقة النشر الموحدة لكل المشاريع (Cloudflare مؤكد لمشروع واحد فقط).
- Testing framework: لا يوجد vitest/playwright في أي مشروع حاليًا.
- استراتيجية Supabase Projects (مشترك/مستقل لكل مشروع) — انظر CLAUDE.md §17.
