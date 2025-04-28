<!--
Meta Description: # استخدام الكلمة المحجوزة "protected" في TypeScript ## ملخص تُستخدم الكلمة المحجوزة "protected" في TypeScript لتحديد مستوى الوصول إلى الخصائص والطرق د...
Meta Keywords: الوصول, protected, إلى, typescript, الخصائص
-->

# استخدام الكلمة المحجوزة "protected" في TypeScript

## ملخص
تُستخدم الكلمة المحجوزة "protected" في TypeScript لتحديد مستوى الوصول إلى الخصائص والطرق داخل فئات معينة، مما يتيح التحكم في كيفية الوصول إلى هذه العناصر من الفئات المشتقة.

## الوثائق
تعتبر الكلمة المحجوزة "protected" من مميزات TypeScript التي تساعد على تعزيز مفهوم التوجيه للكائنات. عندما تُستخدم هذه الكلمة، يمكن الوصول إلى الخصائص والطرق المحمية فقط داخل الفئة التي تم تعريفها فيها أو في أي فئة مشتقة منها. هذا يوفر مستوى من الحماية، مما يمنع الوصول المباشر من خارج الفئة.

### الاستخدام
لتعريف خاصية أو طريقة على أنها محمية، يمكن استخدام الكلمة المحجوزة "protected" في تعريف الفئة، كما يلي:

```typescript
class Animal {
    protected name: string;

    constructor(name: string) {
        this.name = name;
    }

    protected speak(): void {
        console.log(`${this.name} makes a noise.`);
    }
}
```

### التفاصيل
- **الملخص**: تُستخدم "protected" لتحديد الخصائص والطرق التي يمكن الوصول إليها فقط من داخل الفئة أو الفئات المشتقة.
- **الوصول**: يمكن للفئات التي ترث من الفئة الأصلية الوصول إلى الخصائص والطرق المحمية.
- **عدم الوصول الخارجي**: لا يمكن للفئات أو الكائنات التي لا ترث من الفئة الأصلية استخدام الخصائص والطرق المحمية.

## الأمثلة
إليك بعض الأمثلة على كيفية استخدام "protected" في TypeScript:

### مثال 1: تعريف خاصية محمية
```typescript
class Person {
    protected age: number;

    constructor(age: number) {
        this.age = age;
    }
}

class Employee extends Person {
    public getAge(): number {
        return this.age; // الوصول إلى الخاصية المحمية
    }
}

const emp = new Employee(30);
console.log(emp.getAge()); // 30
```

### مثال 2: تعريف طريقة محمية
```typescript
class Vehicle {
    protected startEngine(): void {
        console.log('Engine started.');
    }
}

class Car extends Vehicle {
    public drive(): void {
        this.startEngine(); // الوصول إلى الطريقة المحمية
        console.log('Car is driving.');
    }
}

const myCar = new Car();
myCar.drive(); // Engine started. Car is driving.
```

## الشرح
من الأخطاء الشائعة عندما يتم استخدام "protected" هي محاولة الوصول إلى الخصائص أو الطرق المحمية من خارج الفئة الأصلية والفئات المشتقة. على سبيل المثال:

```typescript
const person = new Person(25);
console.log(person.age); // خطأ: الخاصية محمية ولا يمكن الوصول إليها
```

يجب أن تكون حذرًا عند استخدام "protected"، لأن الفئات المشتقة هي الوحيدة التي يمكنها الوصول إلى هذه الخصائص والطرق. هذا يعني أنه إذا كنت تحتاج إلى استخدام هذه العناصر في سياقات أخرى، قد تحتاج إلى إعادة التفكير في تصميم الفئة.

## ملخص بجملة واحدة
تُستخدم الكلمة المحجوزة "protected" في TypeScript لتحديد الوصول إلى الخصائص والطرق بحيث يمكن الوصول إليها فقط من الفئات المشتقة.