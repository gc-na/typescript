<!--
Meta Description: # استخدام الأمر "implements" في TypeScript ## ملخص يُستخدم الأمر "implements" في TypeScript لتعريف أن فئة معينة تتبنى واجهة محددة، مما يضمن أن الفئة ت...
Meta Keywords: implements, الفئة, name, typescript, واجهة
-->

# استخدام الأمر "implements" في TypeScript

## ملخص
يُستخدم الأمر "implements" في TypeScript لتعريف أن فئة معينة تتبنى واجهة محددة، مما يضمن أن الفئة تحتوي على جميع الخصائص والطرق المعرفة في تلك الواجهة.

## الوثائق
يعتبر "implements" جزءًا أساسيًا من نظام الأنواع في TypeScript، حيث يتيح للمطورين التأكد من أن الفئات تتوافق مع واجهات معينة. يمكن استخدامه لتعزيز قابلية إعادة الاستخدام وتحقيق التصميم الجيد للتطبيقات.

### الغرض
الغرض من استخدام "implements" هو ضمان أن الفئة المعينة تتضمن جميع الخصائص والطرق التي تم تعريفها في الواجهة. هذا يساعد على تقليل الأخطاء وضمان أن الفئات تتبع هيكلًا موحدًا.

### الاستخدام
للاستخدام، يتم تعريف واجهة باستخدام الكلمة الرئيسية `interface`، ثم يتم استخدام الكلمة الرئيسية `implements` في تعريف الفئة. إليك الخطوات الأساسية:

1. تعريف الواجهة باستخدام الكلمة الأساسية `interface`.
2. تعريف الفئة باستخدام الكلمة الأساسية `class`.
3. استخدام الكلمة الأساسية `implements` للإشارة إلى أن الفئة تلتزم بالواجهة.

## الأمثلة
### مثال 1: واجهة بسيطة وفئة
```typescript
interface Person {
    name: string;
    age: number;
    greet(): void;
}

class Student implements Person {
    name: string;
    age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }

    greet() {
        console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
}

const student = new Student("Ali", 20);
student.greet();
```

### مثال 2: واجهة متعددة
```typescript
interface Animal {
    sound(): void;
}

interface Pet extends Animal {
    play(): void;
}

class Dog implements Pet {
    sound() {
        console.log("Woof!");
    }

    play() {
        console.log("The dog is playing.");
    }
}

const dog = new Dog();
dog.sound();
dog.play();
```

## الشرح
### الأخطاء الشائعة
- **عدم مطابقة الواجهة**: عند استخدام "implements"، يجب التأكد من أن الفئة تحتوي على جميع الخصائص والطرق المعرفة في الواجهة. إذا كانت هناك أي خصائص مفقودة، سيظهر خطأ في وقت الترجمة.
- **تعارض الأنواع**: يجب أن تتطابق أنواع الخصائص في الفئة مع الأنواع المحددة في الواجهة. أي تعارض في الأنواع سيؤدي إلى حدوث أخطاء.

### ملاحظات إضافية
- يمكن لفئة واحدة أن تنفذ واجهات متعددة باستخدام الفاصلة.
- لا يمكن لفئة أن تنفذ واجهة بدون تضمين جميع أجزائها.

## ملخص جملة واحدة
الأمر "implements" في TypeScript يُستخدم لضمان أن الفئة تتبنى واجهة محددة، مما يعزز تنظيم الشيفرة وقابلية الصيانة.