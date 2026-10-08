<!-- Idea → Specification. يُحفظ في <project-repo>/docs/00-SPEC.md. يُعتمد من المالك قبل إنشاء الـrepo/الكود.
     لا تخترع Business Logic جوهرية: ما ليس معروفًا → Needs Owner Input. -->
# Project Specification — <project-name>

| | |
|---|---|
| **STATUS** | Idea / Draft / Approved |
| **OWNER** | <...> |
| **DATE** | YYYY-MM-DD |

## 1. Idea
<الفكرة بكلمات المالك>

## 2. Problem
<المشكلة الحالية وكيف تُحل الآن بدون النظام>

## 3. Users & Client
- **العميل/السوق:** <...>
- **المستخدمون:** <أدوار>

## 4. Core Operations
1. <أهم العمليات اليومية التي يجب أن يدعمها النظام>

## 5. MVP (النسخة الأولى فقط)
### Included
- <Module> — <ماذا يفعل>
### Explicitly NOT in MVP
- <...>

## 6. Roles & Permissions
| الدور | يستطيع | لا يستطيع |
|---|---|---|
| Platform Owner | | |
| Tenant Owner | | |
| <...> | | |

## 7. Multi-Tenant
- وحدة الـtenant: <شركة / محل / مركز / ...>
- العزل: RLS على مستوى Database (CLAUDE.md §16)
- Supabase: مشترك / مستقل — <Needs Owner Input إن لم يُحسم>

## 8. Business Rules الأساسية
- <قاعدة غير قابلة للكسر>

## 9. Integrations
- <WhatsApp / SMS / Payment / ...> — أو لا يوجد

## 10. Constraints
- اللغة/الاتجاه: عربي RTL
- <ميزانية، وقت، قانوني، ...>

## 11. Open Questions (Needs Owner Input)
- <...>
