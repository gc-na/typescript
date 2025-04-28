<!--
Meta Description: # Constructor trong TypeScript: Khởi Tạo Đối Tượng Một Cách Hiệu Quả ## Tóm Tắt Constructor trong TypeScript là một phương thức đặc biệt được sử dụng ...
Meta Keywords: constructor, tạo, một, trong, khởi
-->

# Constructor trong TypeScript: Khởi Tạo Đối Tượng Một Cách Hiệu Quả

## Tóm Tắt
Constructor trong TypeScript là một phương thức đặc biệt được sử dụng để khởi tạo các đối tượng của một lớp. Nó cho phép bạn thiết lập các thuộc tính của đối tượng ngay khi đối tượng được tạo ra.

## Tài Liệu
Constructor trong TypeScript được định nghĩa bên trong lớp và có tên giống với tên lớp. Khi một đối tượng mới được khởi tạo từ lớp đó, constructor sẽ tự động được gọi. Đây là nơi lý tưởng để khởi tạo các thuộc tính bắt buộc hoặc thực hiện các hành động khởi tạo khác.

### Cú Pháp
```typescript
class ClassName {
    constructor(param1: type1, param2: type2) {
        // Khởi tạo các thuộc tính ở đây
    }
}
```

### Mục Đích
- Tạo và khởi tạo các thuộc tính của đối tượng.
- Thực hiện các hoạt động cần thiết để thiết lập trạng thái ban đầu của đối tượng.
- Cung cấp một cách dễ dàng để truyền tham số cho đối tượng khi nó được tạo.

## Ví Dụ
### Ví dụ Cơ Bản
Dưới đây là một ví dụ đơn giản về cách sử dụng constructor trong TypeScript:

```typescript
class Person {
    name: string;
    age: number;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }

    introduce() {
        console.log(`Xin chào, tôi là ${this.name} và tôi ${this.age} tuổi.`);
    }
}

const person1 = new Person("Nguyễn Văn A", 30);
person1.introduce(); // Xin chào, tôi là Nguyễn Văn A và tôi 30 tuổi.
```

### Ví dụ với Tham Số Mặc Định
Chúng ta có thể chỉ định tham số mặc định trong constructor:

```typescript
class Car {
    model: string;
    year: number;

    constructor(model: string, year: number = 2020) {
        this.model = model;
        this.year = year;
    }
}

const car1 = new Car("Toyota");
console.log(car1.year); // 2020
```

## Giải Thích
Khi sử dụng constructor, có một số điểm cần lưu ý:

1. **Tham số Bắt Buộc**: Nếu bạn không cung cấp giá trị cho tham số trong constructor, TypeScript sẽ báo lỗi nếu tham số đó không có giá trị mặc định.
2. **Chỉ Được Định Nghĩa Một Lần**: Mỗi lớp chỉ có thể có một constructor. Nếu bạn cần nhiều cách khởi tạo, hãy sử dụng tham số mặc định hoặc phương thức tĩnh.
3. **Tính Kế Thừa**: Khi kế thừa từ một lớp cha, bạn cần gọi `super()` trong constructor của lớp con để khởi tạo các thuộc tính của lớp cha.

## Tóm Tắt Một Dòng
Constructor trong TypeScript là phương thức khởi tạo đối tượng trong lớp, giúp thiết lập thuộc tính và trạng thái ban đầu của đối tượng một cách hiệu quả.