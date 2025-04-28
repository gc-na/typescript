<!--
Meta Description: # Lớp (Class) trong TypeScript: Hướng Dẫn Chi Tiết ## Tóm tắt Lớp (Class) trong TypeScript là một cấu trúc cho phép định nghĩa các đối tượng với thuộc...
Meta Keywords: lớp, typescript, một, tượng, trong
-->

# Lớp (Class) trong TypeScript: Hướng Dẫn Chi Tiết

## Tóm tắt
Lớp (Class) trong TypeScript là một cấu trúc cho phép định nghĩa các đối tượng với thuộc tính và phương thức, giúp tổ chức mã nguồn theo cách hướng đối tượng.

## Tài liệu
Trong TypeScript, lớp (class) là một khái niệm cơ bản trong lập trình hướng đối tượng. Nó cho phép bạn định nghĩa một kiểu dữ liệu mới mà có thể chứa cả thuộc tính (properties) và phương thức (methods). Lớp có thể được kế thừa từ lớp khác, cho phép tái sử dụng mã nguồn và tạo ra các cấu trúc phức tạp hơn.

### Cú pháp
Cú pháp cơ bản để định nghĩa một lớp trong TypeScript như sau:

```typescript
class ClassName {
    // Thuộc tính
    propertyName: propertyType;

    // Constructor
    constructor(parameter: parameterType) {
        this.propertyName = parameter;
    }

    // Phương thức
    methodName(): returnType {
        // Thực hiện một số hành động
    }
}
```

### Đặc điểm
- **Kế thừa**: TypeScript hỗ trợ kế thừa giữa các lớp, cho phép lớp con (subclass) kế thừa thuộc tính và phương thức từ lớp cha (superclass).
- **Modifier truy cập**: Các thuộc tính và phương thức có thể được đánh dấu là `public`, `private`, hoặc `protected` để kiểm soát quyền truy cập.
- **Tính trừu tượng**: Có thể tạo các lớp trừu tượng (abstract classes) không thể được khởi tạo trực tiếp.

## Ví dụ
### Định nghĩa và khởi tạo lớp
```typescript
class Person {
    private name: string;
    private age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }

    public introduce(): string {
        return `Xin chào, tôi là ${this.name} và tôi ${this.age} tuổi.`;
    }
}

const person = new Person("Nguyễn Văn A", 30);
console.log(person.introduce());
```

### Kế thừa
```typescript
class Employee extends Person {
    private position: string;

    constructor(name: string, age: number, position: string) {
        super(name, age);
        this.position = position;
    }

    public introduce(): string {
        return `${super.introduce()} Tôi là ${this.position}.`;
    }
}

const employee = new Employee("Trần Thị B", 25, "Kỹ sư");
console.log(employee.introduce());
```

## Giải thích
Khi làm việc với lớp trong TypeScript, có một số điểm cần lưu ý:
- **Quyền truy cập**: Các thuộc tính `private` không thể được truy cập từ bên ngoài lớp, điều này có thể dẫn đến nhầm lẫn nếu không hiểu rõ cấu trúc.
- **Kế thừa phức tạp**: Khi tạo lớp con từ nhiều lớp cha, có thể xảy ra hiện tượng "diamond inheritance" (kế thừa hình thoi), dẫn đến sự không nhất quán trong mã nguồn.
- **Tính trừu tượng**: Sử dụng lớp trừu tượng để định nghĩa các phương thức mà lớp con phải thực hiện, giúp tạo ra một cấu trúc rõ ràng và dễ quản lý.

## Tóm tắt một câu
Lớp trong TypeScript là một công cụ mạnh mẽ cho phép lập trình viên xây dựng các ứng dụng theo cách hướng đối tượng với khả năng tái sử dụng và tổ chức mã nguồn hiệu quả.