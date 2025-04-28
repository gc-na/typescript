<!--
Meta Description: # Đối Tượng trong TypeScript: Khám Phá và Sử Dụng ## Tóm Tắt Đối tượng (object) trong TypeScript là kiểu dữ liệu cơ bản cho phép lưu trữ nhiều giá trị...
Meta Keywords: đối, tượng, typescript, dụng, liệu
-->

# Đối Tượng trong TypeScript: Khám Phá và Sử Dụng

## Tóm Tắt
Đối tượng (object) trong TypeScript là kiểu dữ liệu cơ bản cho phép lưu trữ nhiều giá trị dưới dạng cặp khóa-giá trị, rất hữu ích trong việc tổ chức và quản lý dữ liệu.

## Tài Liệu
Trong TypeScript, đối tượng là một kiểu dữ liệu phức tạp, cho phép bạn nhóm nhiều thuộc tính và phương thức lại với nhau. Đối tượng có thể được định nghĩa dưới dạng một literal, hoặc thông qua một lớp (class). Kiểu dữ liệu này rất hữu ích khi bạn cần quản lý các thông tin liên quan đến nhau một cách có cấu trúc.

### Mục đích
- Tổ chức dữ liệu: Giúp gom nhóm các thuộc tính và phương thức liên quan.
- Tăng tính mở rộng: Dễ dàng thêm thuộc tính mới mà không làm thay đổi cấu trúc chính.
- Hỗ trợ lập trình hướng đối tượng: Cung cấp cách tiếp cận để xây dựng các ứng dụng phức tạp.

### Cách Sử Dụng
Để định nghĩa một đối tượng, bạn có thể sử dụng cú pháp literal như sau:

```typescript
let person: { name: string; age: number } = {
    name: "Nguyễn Văn A",
    age: 30
};
```

Bên cạnh đó, bạn có thể sử dụng lớp để tạo ra các đối tượng:

```typescript
class Person {
    constructor(public name: string, public age: number) {}
}

let person = new Person("Nguyễn Văn B", 25);
```

## Ví Dụ
### Ví dụ 1: Định Nghĩa Đối Tượng
```typescript
let car: { brand: string; year: number } = {
    brand: "Toyota",
    year: 2021
};
```

### Ví dụ 2: Sử Dụng Lớp
```typescript
class Animal {
    constructor(public species: string, public sound: string) {}

    makeSound() {
        console.log(this.sound);
    }
}

let dog = new Animal("Dog", "Bark");
dog.makeSound(); // In ra "Bark"
```

## Giải Thích
Khi làm việc với đối tượng trong TypeScript, có một số điểm cần lưu ý:
- **Tính bất biến**: Nếu bạn không muốn sửa đổi một đối tượng, bạn có thể sử dụng từ khóa `readonly` cho các thuộc tính.
- **Kiểu dữ liệu**: Đảm bảo rằng các thuộc tính trong đối tượng được định nghĩa đúng kiểu dữ liệu, để tránh lỗi khi biên dịch.
- **Phạm vi truy cập**: Khi sử dụng lớp, hãy chú ý đến phạm vi (public, private, protected) của các thuộc tính và phương thức.

## Tóm Tắt Một Dòng
Đối tượng trong TypeScript là kiểu dữ liệu cho phép tổ chức và quản lý thông tin dưới dạng cặp khóa-giá trị, hỗ trợ lập trình hướng đối tượng và giúp xây dựng các ứng dụng phức tạp.