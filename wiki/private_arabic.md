<!--
Meta Description: # استخدام الكلمة المحجوزة "private" في TypeScript ## ملخص تُستخدم الكلمة المحجوزة "private" في TypeScript لتحديد الخصائص والأساليب التي ينبغي أن تكون ...
Meta Keywords: private, الوصول, الخصائص, الفئة, string
-->

# استخدام الكلمة المحجوزة "private" في TypeScript

## ملخص
تُستخدم الكلمة المحجوزة "private" في TypeScript لتحديد الخصائص والأساليب التي ينبغي أن تكون خاصة بفئة معينة، مما يمنع الوصول إليها من خارج تلك الفئة. يساعد هذا في تحسين مستوى التجريد والأمان في الشيفرة البرمجية.

## الوثائق
تعمل الكلمة المحجوزة "private" على تقييد الوصول إلى عناصر الفئة، مما يعني أنه يمكن الوصول إليها فقط من داخل تلك الفئة. يتم تعريف الخصائص والأساليب الخاصة باستخدام الكلمة "private" قبل اسم الخاصية أو الطريقة.

### الغرض
- حماية البيانات: تضمن الخصائص الخاصة عدم إمكانية الوصول إليها من خارج الفئة، مما يحمي البيانات الحساسة.
- تحسين التجريد: يسمح للمطورين بالتركيز على واجهة الفئة بدلاً من التفاصيل الداخلية.

### الاستخدام
يمكن استخدام الكلمة "private" في تعريف الخصائص والأساليب داخل الفئة كما يلي:

```typescript
class MyClass {
    private myPrivateProperty: string;

    constructor(value: string) {
        this.myPrivateProperty = value;
    }

    private myPrivateMethod(): string {
        return `Value: ${this.myPrivateProperty}`;
    }

    public getValue(): string {
        return this.myPrivateMethod();
    }
}
```

في هذا المثال، `myPrivateProperty` و`myPrivateMethod` هما خاصتان، ولا يمكن الوصول إليهما إلا من داخل `MyClass`.

## الأمثلة
### مثال أساسي
```typescript
class User {
    private password: string;

    constructor(password: string) {
        this.password = password;
    }

    public checkPassword(input: string): boolean {
        return this.password === input;
    }
}

const user = new User("secret");
console.log(user.checkPassword("secret")); // true
// console.log(user.password); // خطأ: Property 'password' is private and only accessible within class 'User'.
```

### مثال آخر
```typescript
class BankAccount {
    private balance: number;

    constructor(initialBalance: number) {
        this.balance = initialBalance;
    }

    public deposit(amount: number): void {
        this.balance += amount;
    }

    public getBalance(): number {
        return this.balance;
    }
}

const account = new BankAccount(100);
account.deposit(50);
console.log(account.getBalance()); // 150
// console.log(account.balance); // خطأ: Property 'balance' is private and only accessible within class 'BankAccount'.
```

## الشرح
### الأخطاء الشائعة
- **عدم فهم الوصول**: قد يخطئ المطورون في محاولة الوصول إلى الخصائص أو الأساليب الخاصة من خارج الفئة، مما يؤدي إلى أخطاء في الشيفرة.
- **تداخل الأسماء**: استخدام نفس أسماء الخصائص العامة والخاصة يمكن أن يؤدي إلى ارتباك في الشيفرة، لذا من الأفضل استخدام أسماء واضحة.

### ملاحظات إضافية
- الخصائص والأساليب الخاصة لا يمكن الوصول إليها عبر الوراثة (inheritance)، مما يعني أن الفئات الفرعية لا تستطيع الوصول إليها.
- يمكن استخدام الكلمات المحجوزة الأخرى مثل "protected" لتوفير مستوى مختلف من الوصول.

## ملخص جملة واحدة
تُستخدم الكلمة المحجوزة "private" في TypeScript لحماية الخصائص والأساليب من الوصول الخارجي، مما يعزز الأمان والتجريد في البرمجة.