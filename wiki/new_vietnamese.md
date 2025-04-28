<!--
Meta Description: # Từ Khóa "new" Trong TypeScript: Cách Khởi Tạo Đối Tượng ## Tóm Tắt Từ khóa `new` trong TypeScript được sử dụng để tạo ra các đối tượng mới từ các lớ...
Meta Keywords: tạo, new, khởi, đối, tượng
-->

# Từ Khóa "new" Trong TypeScript: Cách Khởi Tạo Đối Tượng

## Tóm Tắt
Từ khóa `new` trong TypeScript được sử dụng để tạo ra các đối tượng mới từ các lớp (class). Nó cho phép lập trình viên khởi tạo các đối tượng với các thuộc tính và phương thức được định nghĩa trong lớp.

## Tài Liệu
Từ khóa `new` là một phần quan trọng trong lập trình hướng đối tượng trong TypeScript. Khi bạn định nghĩa một lớp, bạn có thể tạo một đối tượng từ lớp đó bằng cách sử dụng từ khóa `new`.

### Mục Đích
Mục đích chính của từ khóa `new` là khởi tạo một đối tượng mới từ một lớp đã được định nghĩa. Nó cũng tự động gọi hàm khởi tạo (constructor) của lớp đó.

### Cách Sử Dụng
Để sử dụng từ khóa `new`, bạn cần có một lớp đã được định nghĩa. Dưới đây là cú pháp cơ bản:
```typescript
let objectName = new ClassName(parameters);
```

### Chi Tiết
- Khi sử dụng `new`, TypeScript sẽ tạo ra một đối tượng mới và trả về nó.
- Nếu lớp có một hàm khởi tạo, hàm này sẽ được gọi với các tham số được truyền vào.
- Nếu không có hàm khởi tạo, một đối tượng rỗng sẽ được tạo ra.

## Ví Dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng từ khóa `new` trong TypeScript:

### Ví dụ 1: Khởi Tạo Đối Tượng Từ Lớp
```typescript
class Person {
  name: string;
  age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }
}

const person1 = new Person("John", 30);
console.log(person1.name); // John
console.log(person1.age);  // 30
```

### Ví dụ 2: Khởi Tạo Đối Tượng Không Có Tham Số
```typescript
class Animal {
  species: string;

  constructor() {
    this.species = "Unknown";
  }
}

const animal1 = new Animal();
console.log(animal1.species); // Unknown
```

## Giải Thích
Khi sử dụng từ khóa `new`, có một số lưu ý cần nhớ:
- **Gọi Hàm Khởi Tạo**: Nếu lớp có một hàm khởi tạo mà không có tham số, bạn vẫn có thể tạo đối tượng mà không cần truyền tham số.
- **Không Thể Sử Dụng `new` Với Hàm Thông Thường**: Chỉ có thể sử dụng `new` với lớp hoặc hàm khởi tạo; không thể sử dụng với các hàm thông thường.
- **Lỗi Khi Không Có Hàm Khởi Tạo**: Nếu lớp không có hàm khởi tạo và không có thuộc tính nào được định nghĩa, đối tượng sẽ được tạo ra nhưng sẽ không có thuộc tính nào.

## Tóm Tắt Một Dòng
Từ khóa `new` trong TypeScript được sử dụng để khởi tạo các đối tượng mới từ các lớp, cho phép lập trình viên dễ dàng tạo ra và quản lý các thực thể trong ứng dụng.