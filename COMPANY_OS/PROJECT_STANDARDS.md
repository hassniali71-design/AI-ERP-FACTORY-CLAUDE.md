# Project Standards — Project Context Template (Design)

> الحالة: **Draft v0.1** — التصميم فقط. ملفات القالب الفعلية تُبنى في Phase 2 داخل `TEMPLATES/NEW_PROJECT/`.
> المرجع: هيكل `taqseet-erp/docs/` (مجرَّب فعليًا عبر 64 بند عمل). لم يُنسخ أي محتوى منه.

## 1. مبدأ التوزيع (DEC-0002)

| المكان | يحتوي |
|---|---|
| **Repo المشروع** | الـContext التفصيلي الحقيقي (`CLAUDE.md` + `docs/`) — المصدر الوحيد للحقيقة |
| **Factory → `PROJECTS/<name>/PROJECT.md`** | بطاقة فقط: metadata، روابط، حالة، معلومات تشغيلية، مؤشرات لملفات الـrepo |

## 2. ما تعلمناه من taqseet-erp (ما ينجح)

1. **`CLAUDE.md` قصير جدًا (~20 سطر)** في جذر المشروع = خريطة + قوانين قراءة، وليس موسوعة.
2. **قانون قراءة صريح:** لا يُقرأ أي ملف من `docs/` إلا عند الحاجة — مع استثناء دائم لملف الحالة.
3. **ملفات مرقمة صغيرة** بمسؤولية واحدة لكل ملف.
4. **ملف حالة واحد** ("وصلنا لفين") يُحدَّث بسطر بعد كل تعديل.
5. **فصل "المنفذ فعليًا" عن "المؤجَّل بقرار واعٍ"** — يمنع إعادة فتح قرارات.
6. Spec كبير منفصل (`ERP_SaaS_Requirements.md`) لا يُقرأ إلا عند الحاجة.

## 3. القالب المقترح (داخل repo كل مشروع)

```text
<project-repo>/
├── CLAUDE.md                 ≤ 30 سطر: وصف، Stack، قوانين القراءة، خريطة الملفات، أوامر التحقق
└── docs/
    ├── 01-BRIEF.md           الفكرة، المشكلة، العميل/السوق، نوع النظام          ← PROJECT.md (CLAUDE.md §8)
    ├── 02-STACK.md           الـStack وأوامر التشغيل + الانحرافات عن STANDARD_STACK
    ├── 03-STATE.md           الحالة الحقيقية الآن + آخر بند + Known Issues     ← CURRENT_STATE.md
    ├── 04-ARCHITECTURE.md    Frontend/API/Auth/Authorization/Integrations/Deploy ← ARCHITECTURE.md
    ├── 05-DATABASE.md        الجداول، العلاقات، RLS، migrations المهمة، العزل    ← DATABASE.md
    ├── 06-RULES.md           Business Rules غير القابلة للكسر                    ← BUSINESS_RULES.md
    ├── 07-IMPLEMENTED.md     جرد الـFeatures المنفذة فعليًا
    ├── 08-PLAN.md            الباقي / المؤجَّل بقرار واعٍ
    ├── 09-WORKFLOW.md        قواعد عمل خاصة بالمشروع + gotchas
    ├── DECISIONS.md          قرارات المشروع (قالب CLAUDE.md §14)
    └── (اختياري) BRAND.md, SPEC.md, ملفات domain خاصة (مثل FINANCE.md)
```

### ربط القالب بمتطلبات CLAUDE.md §8

الملفات الخمسة الإلزامية (PROJECT / ARCHITECTURE / DATABASE / BUSINESS_RULES / CURRENT_STATE) موجودة كلها ضمن الترقيم أعلاه (الأسهم ←)، بدل إنشاء ملفات مكررة بأسماء مختلفة.

### الفرق عن taqseet-erp الحالي

| taqseet-erp | القالب | السبب |
|---|---|---|
| لا يوجد ARCHITECTURE / DATABASE منفصلين | 04 / 05 | مطلوبان في CLAUDE.md §8 |
| `04-BRAND`, `08-FINANCE` | اختياريان | خاصان بالمشروع |
| لا يوجد DECISIONS | `DECISIONS.md` | CLAUDE.md §14 |

> **لا يُعاد ترتيب ملفات taqseet-erp الحالية.** القالب للمشاريع الجديدة، والمشاريع القائمة تُكمَّل بالملفات الناقصة فقط عند الحاجة وبموافقة.

## 4. أسئلة مفتوحة قبل Phase 2

- هل Tasks / Reports لكل مشروع تعيش داخل repo المشروع (`docs/tasks/`) أم في الـFactory؟ (توصية: داخل repo المشروع، تماشيًا مع DEC-0002.)
