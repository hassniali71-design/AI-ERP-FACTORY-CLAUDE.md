<!-- ملحق إلزامي لأي Task تمس الـDatabase. يُحفظ داخل ملف الـTask أو بجواره: docs/tasks/TASK-NNNN-db.md
     المرجع: CLAUDE.md §25. احتمال فقد بيانات = توقف واطلب مراجعة المالك. -->
# DATABASE CHANGE — <TASK-ID>

| | |
|---|---|
| **PROJECT** | <project-name> |
| **MIGRATION FILE** | `supabase/migrations/<NNNN_name>.sql` (اتبع نمط الترقيم الموجود في المشروع) |
| **RISK** | Low (إضافة فقط) / Medium (تعديل) / **High (حذف/تحويل بيانات)** |
| **OWNER APPROVAL** | مطلوب إذا Medium/High · <نعم بتاريخ / بانتظار> |

## 1. Current Schema (قبل)
<الجداول/الأعمدة المتأثرة كما هي الآن — من الـmigrations، وليس من الذاكرة>

## 2. Change
| العملية | الجدول | التفاصيل |
|---|---|---|
| ADD / ALTER / DROP / RLS / FUNCTION / INDEX | | |

## 3. Multi-Tenant & Security
- [ ] كل جدول جديد فيه عمود الـtenant (مثل `tenant_id`) بنفس نمط المشروع
- [ ] RLS **enabled** على كل جدول جديد
- [ ] Policies تعزل الـtenants (SELECT / INSERT / UPDATE / DELETE)
- [ ] لا يُعتمد على الـUI لإخفاء البيانات
- [ ] لا service-role في الـFrontend

## 4. Data Safety
- هل يوجد احتمال فقد/تغيير بيانات قائمة؟ **لا / نعم → توقف**
- Idempotent؟ (`IF NOT EXISTS` / `IF EXISTS`) نعم / لا
- Rollback: <SQL أو خطوات التراجع — أو "غير قابل للتراجع" + سبب + موافقة>
- Backup قبل التطبيق على Production: مطلوب إذا Medium/High

## 5. Code Impact
<queries / types / server functions / UI تتأثر>

## 6. Validation
- [ ] الـmigration تُطبَّق بلا أخطاء على بيئة غير Production أولًا
- [ ] مستخدم tenant A لا يرى بيانات tenant B
- [ ] الصلاحيات حسب الأدوار
- [ ] Data integrity: <فحص محدد — بدون قراءة بيانات عملاء حقيقية>
- [ ] `bun run build` نظيف

## 7. Rollout
| البيئة | تاريخ التطبيق | بواسطة | النتيجة |
|---|---|---|---|
| Local/Staging | | | |
| Production | | | |

بعد التطبيق: حدّث `docs/05-DATABASE.md` (أو ما يقابله في المشروع).
