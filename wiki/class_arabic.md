<!--
Meta Description: # فئة (Class) في TypeScript: مفهومها واستخداماتها ## ملخص تعتبر الفئة (Class) في TypeScript واحدة من اللبنات الأساسية للبرمجة الكائنية، حيث توفر وسيلة...
Meta Keywords: name, typescript, الفئة, الخصائص, class
-->

# فئة (Class) في TypeScript: مفهومها واستخداماتها

## ملخص
تعتبر الفئة (Class) في TypeScript واحدة من اللبنات الأساسية للبرمجة الكائنية، حيث توفر وسيلة لإنشاء كائنات تتشارك في الخصائص والطرق، مما يسهل تنظيم الشيفرة البرمجية وإعادة استخدامها.

## الوثائق
تُستخدم الفئة في TypeScript لتعريف نوع من الكائنات يتضمن خصائص وطرق. تُعتبر الفئات بمثابة قوالب يمكن من خلالها إنشاء كائنات جديدة. يمكن أن تحتوي الفئة على مُنشئ (Constructor) يُستخدم لتهيئة الكائنات عند إنشائها.

### الغرض
- تنظيم الشيفرة البرمجية من خلال تجميع البيانات والوظائف في كائنات.
- توفير إمكانية التوريث، مما يسمح بإنشاء فئات جديدة تستند إلى فئات موجودة.

### الاستخدام
لإنشاء فئة جديدة، يتم استخدام الكلمة المفتاحية `class` متبوعة باسم الفئة. يمكن تعريف الخصائص والطرق داخل الفئة، بالإضافة إلى المُنشئ.

### تفاصيل
```typescript
class ClassName {
    // الخصائص
    propertyName: type;

    // المُنشئ
    constructor(parameter: type) {
        this.propertyName = parameter;
    }

    // الطرق
    methodName(): returnType {
        // تنفيذ الشيفرة
    }
}
```

## الأمثلة
### مثال بسيط على فئة
```typescript
class Person {
    name: string;
    age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }

    greet(): string {
        return `Hello, my name is ${this.name} and I am ${this.age} years old.`;
    }
}

const person1 = new Person("Ali", 30);
console.log(person1.greet()); // Hello, my name is Ali and I am 30 years old.
```

### مثال على التوريث
```typescript
class Animal {
    name: string;

    constructor(name: string) {
        this.name = name;
    }

    speak(): string {
        return `${this.name} makes a noise.`;
    }
}

class Dog extends Animal {
    speak(): string {
        return `${this.name} barks.`;
    }
}

const dog = new Dog("Rex");
console.log(dog.speak()); // Rex barks.
```

## الشرح
### الأخطاء الشائعة
- **عدم تعريف الخصائص**: تأكد من تعريف جميع الخصائص قبل استخدامها.
- **عدم استخدام المُنشئ**: عند إنشاء كائن من الفئة، يجب استخدام المُنشئ لتهيئة الخصائص.
- **عدم استخدام `this`**: عند الإشارة إلى الخصائص داخل الفئة، يجب استخدام `this` لضمان الوصول الصحيح.

### ملاحظات إضافية
- TypeScript يدعم الفئات المستندة إلى ECMAScript 2015 (ES6) ويضيف ميزات إضافية مثل الأنواع الثابتة.
- يمكن استخدام الفئات لإنشاء واجهات برمجية واضحة، مما يسهل الصيانة والتوسع.

## ملخص بجملة واحدة
تمكن الفئة في TypeScript من إنشاء كائنات منظمة وقابلة لإعادة الاستخدام من خلال تجميع الخصائص والطرق في قالب موحد.