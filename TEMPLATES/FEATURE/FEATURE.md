<!-- Idea → Specification لميزة داخل مشروع قائم. يُحفظ في: <project-repo>/docs/features/FEAT-NNNN-<slug>.md
     الناتج النهائي: قائمة Tasks صغيرة (كل واحدة بقالب TASK). لا تنفيذ قبل اعتماد المالك. -->
# FEAT-NNNN — <اسم الميزة>

| | |
|---|---|
| **PROJECT** | <project-name> |
| **STATUS** | Idea / Spec Draft / Approved / In Progress / Done |
| **REQUESTED BY** | <المالك / العميل> · YYYY-MM-DD |

## 1. Idea
<الطلب كما ورد، بكلمات صاحبه>

## 2. Problem
<ما المشكلة التي تحلها؟ ماذا يحدث الآن بدونها؟>

## 3. Users & Roles
| الدور | ماذا يفعل بالميزة؟ | صلاحيات |
|---|---|---|
| | | |

## 4. Specification
### المسار الأساسي
1. <خطوة>
### حالات خاصة / أخطاء
- <...>
### Business Rules
- <قاعدة — مع مرجع لـ docs/RULES إن وُجدت>

## 5. Impact
- **Database:** لا / نعم → <جداول، RLS> (يستلزم DATABASE_CHANGE)
- **API / Server functions:** <...>
- **UI:** <صفحات/مكونات>
- **Multi-tenant:** <كيف يُضمن العزل على مستوى DB؟>
- **Integrations:** <...>

## 6. Out of Scope
- <...>

## 7. Known / Unknown
- معروف: <...>
- غير معروف (Needs Owner Input): <...>

## 8. Task Breakdown
| Task | العنوان | النوع | يعتمد على |
|---|---|---|---|
| TASK-NNNN | | | — |

## 9. Acceptance
- [ ] <كيف يتأكد المالك أن الميزة تعمل>
