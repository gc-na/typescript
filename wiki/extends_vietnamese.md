<!--
Meta Description: # Sử Dụng Từ Khóa "extends" Trong TypeScript: Hướng Dẫn Chi Tiết ## Tóm Tắt Từ khóa "extends" trong TypeScript được sử dụng để kế thừa các lớp hoặc gi...
Meta Keywords: lớp, giao, diện, thừa, các
-->

# Sử Dụng Từ Khóa "extends" Trong TypeScript: Hướng Dẫn Chi Tiết

## Tóm Tắt
Từ khóa "extends" trong TypeScript được sử dụng để kế thừa các lớp hoặc giao diện, cho phép một lớp hoặc giao diện mở rộng các thuộc tính và phương thức của lớp hoặc giao diện khác, giúp tăng tính tái sử dụng mã và tổ chức cấu trúc chương trình.

## Tài Liệu
### Mục Đích
Từ khóa "extends" cho phép bạn tạo ra các lớp hoặc giao diện con từ các lớp hoặc giao diện cha, cho phép mở rộng và kế thừa các thuộc tính và phương thức. Điều này giúp giảm thiểu sự trùng lặp mã và cải thiện khả năng bảo trì.

### Cách Sử Dụng
1. **Kế thừa Lớp**: Khi bạn tạo một lớp mới, bạn có thể sử dụng từ khóa "extends" để kế thừa từ một lớp khác.
2. **Kế thừa Giao Diện**: Tương tự, bạn có thể sử dụng "extends" trong giao diện để kế thừa từ một giao diện khác.

### Chi Tiết
Khi một lớp con kế thừa từ lớp cha, nó có thể truy cập tất cả các thuộc tính và phương thức công khai và bảo vệ của lớp cha. Trong trường hợp giao diện, giao diện con sẽ bao gồm tất cả các thuộc tính của giao diện cha, và bạn có thể thêm các thuộc tính mới.

## Ví Dụ
### Kế Thừa Lớp
```typescript
class Animal {
    speak() {
        console.log("Animal speaks");
    }
}

class Dog extends Animal {
    bark() {
        console.log("Dog barks");
    }
}

const dog = new Dog();
dog.speak(); // Animal speaks
dog.bark();  // Dog barks
```

### Kế Thừa Giao Diện
```typescript
interface Person {
    name: string;
}

interface Employee extends Person {
    salary: number;
}

const employee: Employee = {
    name: "John",
    salary: 50000
};
```

## Giải Thích
### Những Cạm Bẫy Thường Gặp
- **Không Kế Thừa Đúng Cách**: Đảm bảo rằng lớp hoặc giao diện cha có các thuộc tính được sử dụng trong lớp hoặc giao diện con.
- **Lỗi Khi Gọi Phương Thức**: Nếu bạn gọi phương thức của lớp cha mà không có sự kế thừa đúng, TypeScript sẽ báo lỗi.
- **Lỗi Tại Thời Điểm Biên Dịch**: Kiểm tra kỹ các thuộc tính và phương thức để tránh lỗi không mong muốn khi biên dịch.

## Tóm Tắt Một Câu
Từ khóa "extends" trong TypeScript cho phép bạn kế thừa các thuộc tính và phương thức từ lớp hoặc giao diện khác, giúp cải thiện tính tái sử dụng mã và cấu trúc chương trình.