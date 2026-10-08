# قواعد عمل خاصة بالمشروع + Gotchas

- لا تغيير للـStack بدون Decision وموافقة.
- لا اختراع Business Rules — عند الشك: Needs Owner Input.
- حافظ على RTL (`dir="rtl"`, `lang="ar"`).
- Commits صغيرة بوصف واضح: `<TASK-ID>: <وصف>`.
- اتبع نمط طبقة البيانات الموجود — لا أنماط موازية.

## Gotchas
- **TanStack Router:** لصفحة تفاصيل `/foo/$id` مع وجود `foo.tsx` سمِّ الملف `foo_.$id.tsx`، وإلا يعتبر `foo.tsx` layout ويظل المحتوى صفحة القائمة. — مصدر: taqseet-erp
