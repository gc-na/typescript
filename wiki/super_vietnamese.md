<!--
Meta Description: # Từ Khóa "super" Trong TypeScript: Cách Sử Dụng và Tính Năng ## Tóm Tắt Từ khóa "super" trong TypeScript được sử dụng để gọi các phương thức và thuộc...
Meta Keywords: lớp, super, dụng, gọi, cha
-->

# Từ Khóa "super" Trong TypeScript: Cách Sử Dụng và Tính Năng

## Tóm Tắt
Từ khóa "super" trong TypeScript được sử dụng để gọi các phương thức và thuộc tính từ lớp cha (superclass) trong lớp con (subclass). Nó giúp khôi phục các thành phần của lớp cha trong quá trình kế thừa, hỗ trợ cho việc xây dựng các ứng dụng phức tạp hơn.

## Tài Liệu
### Mục Đích
"super" cho phép các lớp con truy cập và sử dụng các thành phần của lớp cha. Điều này rất quan trọng trong lập trình hướng đối tượng, nơi mà việc tái sử dụng mã và mở rộng chức năng là cần thiết.

### Cách Sử Dụng
Khi một lớp con kế thừa từ một lớp cha, bạn có thể sử dụng từ khóa "super" để:
- Gọi hàm khởi tạo của lớp cha.
- Gọi các phương thức và thuộc tính của lớp cha.

### Chi Tiết
1. **Gọi Hàm Khởi Tạo**: Trong lớp con, để gọi hàm khởi tạo của lớp cha, bạn cần sử dụng "super()" trong hàm khởi tạo của lớp con.
2. **Gọi Phương Thức**: Bạn có thể sử dụng "super.methodName()" để gọi một phương thức từ lớp cha.
3. **Truy Cập Thuộc Tính**: "super.propertyName" có thể được sử dụng để truy cập thuộc tính của lớp cha.

## Ví Dụ
Dưới đây là một số ví dụ minh họa về cách sử dụng "super" trong TypeScript:

### Ví Dụ 1: Gọi Hàm Khởi Tạo
```typescript
class Animal {
    constructor(public name: string) {
        console.log(`${this.name} is an animal.`);
    }
}

class Dog extends Animal {
    constructor(name: string) {
        super(name); // Gọi hàm khởi tạo của lớp cha
        console.log(`${this.name} is a dog.`);
    }
}

const myDog = new Dog("Buddy");
```

### Ví Dụ 2: Gọi Phương Thức
```typescript
class Animal {
    makeSound() {
        console.log("Animal makes sound");
    }
}

class Dog extends Animal {
    makeSound() {
        super.makeSound(); // Gọi phương thức của lớp cha
        console.log("Dog barks");
    }
}

const myDog = new Dog();
myDog.makeSound();
```

## Giải Thích
### Các Vấn Đề Thường Gặp
- **Bỏ Quên Gọi super()**: Nếu bạn không gọi "super()" trong hàm khởi tạo của lớp con, TypeScript sẽ báo lỗi.
- **Xung Đột Tên**: Nếu lớp con định nghĩa phương thức hoặc thuộc tính với tên giống với lớp cha, bạn cần sử dụng "super" để truy cập thành phần của lớp cha.
- **Không Thể Sử Dụng super Ngoài Lớp**: Từ khóa "super" chỉ có thể sử dụng trong ngữ cảnh của một lớp con và không thể sử dụng trong các hàm hoặc biến toàn cục.

## Tóm Tắt Một Dòng
Từ khóa "super" trong TypeScript cho phép lớp con gọi các phương thức và thuộc tính của lớp cha, hỗ trợ cho việc kế thừa trong lập trình hướng đối tượng.