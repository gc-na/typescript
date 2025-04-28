<!--
Meta Description: # التصدير في TypeScript: كيفية استخدام الأمر "export" بفعالية ## ملخص الأمر "export" في TypeScript يُستخدم لتصدير المتغيرات، الدوال، أو الفئات من وحدة...
Meta Keywords: export, typescript, يمكن, تصدير, الأمر
-->

# التصدير في TypeScript: كيفية استخدام الأمر "export" بفعالية

## ملخص
الأمر "export" في TypeScript يُستخدم لتصدير المتغيرات، الدوال، أو الفئات من وحدة معينة (module) بحيث يمكن استيرادها في وحدات أخرى. يساعد هذا الأمر في تنظيم الكود وتعزيز إعادة الاستخدام.

## الوثائق
يُعتبر الأمر "export" جزءًا أساسيًا من نظام الوحدات في TypeScript. يتيح للمطورين تقسيم الكود إلى وحدات صغيرة وقابلة لإعادة الاستخدام. يمكن استخدام "export" لتصدير العناصر التالية:

- **المتغيرات**: يمكن تصدير المتغيرات لتكون متاحة في وحدات أخرى.
- **الدوال**: يمكن تصدير الدوال بحيث يمكن استخدامها في أماكن أخرى من التطبيق.
- **الفئات**: يمكن تصدير الفئات لتسهيل إنشاء كائنات من أنواع بيانات معينة في وحدات مختلفة.

### الاستخدام
يمكن استخدام الأمر "export" بطرق مختلفة:

1. **التصدير المباشر**:
   ```typescript
   export const myVariable = 42;
   
   export function myFunction() {
       console.log("Hello, World!");
   }
   
   export class MyClass {
       constructor() {
           console.log("MyClass instance created!");
       }
   }
   ```

2. **التصدير المتأخر** (تصدير العناصر بعد تعريفها):
   ```typescript
   const myVariable = 42;
   function myFunction() {
       console.log("Hello, World!");
   }
   class MyClass {
       constructor() {
           console.log("MyClass instance created!");
       }
   }

   export { myVariable, myFunction, MyClass };
   ```

### التفاصيل
عند استخدام الأمر "export"، يجب أن تكون العناصر المراد تصديرها متاحة خارج الوحدة. يمكن استخدام "export" في أي مكان داخل ملف TypeScript. يجب ملاحظة أن العناصر غير المصدرة تبقى محلية للوحدة.

## أمثلة
### مثال 1: تصدير متغير
```typescript
// file1.ts
export const myNumber = 100;

// file2.ts
import { myNumber } from './file1';
console.log(myNumber); // 100
```

### مثال 2: تصدير دالة
```typescript
// file1.ts
export function greet(name: string) {
    return `Hello, ${name}!`;
}

// file2.ts
import { greet } from './file1';
console.log(greet("Alice")); // Hello, Alice!
```

### مثال 3: تصدير فئة
```typescript
// file1.ts
export class Person {
    constructor(public name: string) {}
}

// file2.ts
import { Person } from './file1';
const person = new Person("Bob");
console.log(person.name); // Bob
```

## الشرح
- **التحذيرات الشائعة**: تأكد من عدم وجود تعارض في الأسماء عند استيراد العناصر. إذا كان هناك عنصر بنفس الاسم في وحدة أخرى، فقد يؤدي ذلك إلى أخطاء.
- **الاستيراد الافتراضي**: عند استخدام "export default"، يمكنك تصدير عنصر واحد فقط كافتراضي من الوحدة. يمكن استيراده باستخدام اسم مختلف.

## ملخص بعبارة واحدة
الأمر "export" في TypeScript يُستخدم لتصدير المتغيرات، الدوال، والفئات من وحدة معينة لتسهيل إعادة استخدامها في وحدات أخرى.