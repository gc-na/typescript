<!--
Meta Description: # استيراد في TypeScript: كيفية استخدام الأمر "import" بفعالية ## ملخص يعتبر الأمر "import" في TypeScript أداة أساسية لاستيراد الوحدات والمكتبات، مما ي...
Meta Keywords: import, typescript, استخدام, module, استيراد
-->

# استيراد في TypeScript: كيفية استخدام الأمر "import" بفعالية

## ملخص
يعتبر الأمر "import" في TypeScript أداة أساسية لاستيراد الوحدات والمكتبات، مما يسهل تنظيم الشيفرة وتقسيمها إلى أجزاء قابلة لإعادة الاستخدام.

## الوثائق
يستخدم الأمر "import" لاستيراد العناصر مثل المتغيرات، الدوال، أو الكائنات من وحدات (Modules) أخرى في TypeScript. يتيح لك هذا الأمر العمل بكفاءة أكبر وتحسين هيكلة الشيفرة الخاصة بك.

### الغرض
الهدف من استخدام "import" هو استيراد الكود من ملف آخر للاستفادة منه دون الحاجة إلى إعادة كتابته، مما يساعد في تقليل التكرار وزيادة قابلية الصيانة.

### الاستخدام
يتم استخدام الأمر "import" بالصيغة التالية:

```typescript
import { Element } from './module';
```

أو لاستيراد الافتراضيات:

```typescript
import Element from './module';
```

يمكن أيضًا استخدام الأمر لاستيراد جميع العناصر من وحدة معينة:

```typescript
import * as ModuleName from './module';
```

### التفاصيل
- يدعم TypeScript استيراد الوحدات من ملفات JavaScript وTypeScript.
- يمكن استخدام "import" مع أنواع البيانات، الكائنات، والدوال.
- يجب أن تكون الوحدات المستوردة متاحة في المسار المحدد.
- يمكن استخدام "import" داخل ملفات `.ts` و`.tsx`.

## الأمثلة
### استيراد دالة
```typescript
// module.ts
export function greet(name: string) {
    return `Hello, ${name}!`;
}

// main.ts
import { greet } from './module';

console.log(greet('Ali')); // Hello, Ali!
```

### استيراد الافتراضيات
```typescript
// module.ts
const PI = 3.14;
export default PI;

// main.ts
import PI from './module';

console.log(PI); // 3.14
```

### استيراد جميع العناصر
```typescript
// module.ts
export const a = 1;
export const b = 2;

// main.ts
import * as MathConstants from './module';

console.log(MathConstants.a); // 1
console.log(MathConstants.b); // 2
```

## الشرح
### الأخطاء الشائعة
- عدم تطابق المسار: تأكد من صحة المسار عند استيراد الملفات.
- عدم تصدير العناصر المطلوبة: تحقق من أن العنصر المطلوب تم تصديره بشكل صحيح من الوحدة.
- استخدام الأسماء غير الصحيحة: تأكد من استخدام الأسماء الصحيحة للعناصر المستوردة.

### ملاحظات إضافية
- يمكن استخدام "import" بشكل متداخل داخل الشيفرة، لكن يُفضل ترتيب الاستيرادات في بداية الملف.
- عند استيراد مكتبات خارجية، تأكد من تثبيتها عبر npm أو yarn.

## ملخص جملة واحدة
الأمر "import" في TypeScript يُستخدم لاستيراد الوحدات والعناصر، مما يسهل تنظيم الشيفرة ويعزز إعادة الاستخدام.