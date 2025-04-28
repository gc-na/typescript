<!--
Meta Description: # استخدام await في TypeScript: دليل شامل للمبرمجين ## ملخص الأمر `await` في TypeScript يُستخدم لتأجيل تنفيذ الشيفرة حتى يتم الانتهاء من Promise. ويسمح...
Meta Keywords: await, promise, async, استخدام, typescript
-->

# استخدام await في TypeScript: دليل شامل للمبرمجين

## ملخص
الأمر `await` في TypeScript يُستخدم لتأجيل تنفيذ الشيفرة حتى يتم الانتهاء من Promise. ويسمح لك بكتابة شيفرة غير متزامنة بطريقة سلسة وسهلة الفهم.

## الوثائق
يُعتبر `await` جزءًا من بنية `async/await` في JavaScript وTypeScript، حيث يُستخدم مع الدوال المعرفة بـ `async`. يُستخدم `await` لتجعل الشيفرة تنتظر حتى تُحل الـ Promise. إذا كان الـ Promise ناجحًا، يتم استئناف التنفيذ بالقيمة المعادة. أما إذا فشل، يتم رمي الخطأ.

### الاستخدام
لإستخدام `await`، يجب أن تكون في دالة معرفة بـ `async`:

```typescript
async function fetchData() {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    return data;
}
```

### التفاصيل
- يتم استخدام `await` فقط مع القيم التي تعيد Promise.
- عند استخدام `await`، يجب أن تكون الدالة محاطة بكلمة `async`.
- يمكن استخدام `await` عدة مرات في نفس الدالة.

## الأمثلة
### مثال أساسي
```typescript
async function example() {
    const result = await Promise.resolve(5);
    console.log(result); // 5
}
example();
```

### مثال مع Fetch API
```typescript
async function getUserData(userId: number) {
    try {
        const response = await fetch(`https://api.example.com/users/${userId}`);
        const userData = await response.json();
        console.log(userData);
    } catch (error) {
        console.error('Error fetching user data:', error);
    }
}
getUserData(1);
```

## الشرح
### العقبات الشائعة
- **عدم استخدام `async`**: إذا حاولت استخدام `await` في دالة غير معرفة بـ `async`، ستحصل على خطأ.
- **الانتظار على القيم غير الـ Promise**: إذا استخدمت `await` على قيمة ليست Promise، سيتم تحويلها تلقائيًا إلى Promise، مما قد يؤدي إلى سلوك غير متوقع.
- **نقص في معالجة الأخطاء**: من الأفضل دائماً استخدام `try/catch` حول الكود الذي يستخدم `await` للتأكد من معالجة الأخطاء بشكل صحيح.

## ملخص جملة واحدة
`await` في TypeScript يتيح لك كتابة شيفرة غير متزامنة بطريقة سلسة من خلال تأجيل التنفيذ حتى يتم حل الـ Promise.