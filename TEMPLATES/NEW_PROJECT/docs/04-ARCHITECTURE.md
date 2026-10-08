# Architecture

| المكون | التفاصيل |
|---|---|
| Frontend | TanStack Start + React + Tailwind + shadcn/ui |
| Backend / API | <server functions / Supabase RPC / edge functions> |
| Database | Supabase Postgres — انظر `05-DATABASE.md` |
| Authentication | Supabase Auth — <طريقة الدخول> |
| Authorization | <الأدوار — وأين تُفرض: RLS / server> |
| Integrations | <...> |
| Deployment | <Cloudflare Workers / ...> |

## العلاقات بين المكونات
<مسار الطلب: UI → data layer → Supabase (RLS) → ...>

## قرارات معمارية
- انظر `DECISIONS.md`
