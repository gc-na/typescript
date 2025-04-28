<!--
Meta Description: # Từ Khóa "private" trong TypeScript: Cách Sử Dụng và Ý Nghĩa ## Tóm Tắt Từ khóa `private` trong TypeScript được sử dụng để kiểm soát quyền truy cập v...
Meta Keywords: private, tính, lớp, thuộc, phương
-->

# Từ Khóa "private" trong TypeScript: Cách Sử Dụng và Ý Nghĩa

## Tóm Tắt
Từ khóa `private` trong TypeScript được sử dụng để kiểm soát quyền truy cập vào các thuộc tính và phương thức của một lớp, giúp bảo vệ dữ liệu và ngăn chặn việc truy cập trái phép từ bên ngoài.

## Tài Liệu
Trong TypeScript, từ khóa `private` được áp dụng cho các thuộc tính và phương thức của một lớp. Khi một thuộc tính hoặc phương thức được đánh dấu là `private`, nó chỉ có thể được truy cập từ bên trong lớp đó. Điều này giúp lập trình viên quản lý tốt hơn việc sử dụng dữ liệu và bảo vệ tính toàn vẹn của nó.

### Cách Sử Dụng
- **Khai báo Thuộc Tính Private**: Bạn có thể khai báo thuộc tính là `private` trong lớp bằng cách sử dụng từ khóa này trước tên thuộc tính.
- **Khai báo Phương Thức Private**: Tương tự, bạn có thể khai báo các phương thức là `private`, ngăn chặn việc gọi từ ngoài lớp.

### Ví dụ
```typescript
class User {
    private password: string;

    constructor(password: string) {
        this.password = password;
    }

    private validatePassword(input: string): boolean {
        return this.password === input;
    }

    public login(input: string): string {
        if (this.validatePassword(input)) {
            return "Login successful";
        } else {
            return "Invalid password";
        }
    }
}

const user = new User("secret");
console.log(user.login("secret")); // Login successful
// console.log(user.password); // Lỗi: thuộc tính 'password' là private
// console.log(user.validatePassword("secret")); // Lỗi: phương thức 'validatePassword' là private
```

## Giải Thích
- **Khó Khăn Thường Gặp**: Một số lập trình viên mới có thể nhầm lẫn giữa `private` và `public`. Dễ mắc phải lỗi khi cố gắng truy cập các thuộc tính hoặc phương thức `private` từ bên ngoài lớp.
- **Lưu Ý Quan Trọng**: Từ khóa `private` chỉ bảo vệ các thuộc tính và phương thức trong ngữ cảnh của lớp. Nếu lớp con kế thừa từ lớp cha, các thuộc tính và phương thức `private` không thể được truy cập từ lớp con.

## Tóm Tắt Một Dòng
Từ khóa `private` trong TypeScript giúp bảo vệ và kiểm soát quyền truy cập vào thuộc tính và phương thức của lớp, chỉ cho phép truy cập từ bên trong lớp đó.