<!--
Meta Description: # Namespace trong TypeScript: Tổ Chức Mã Nguồn Hiệu Quả ## Tóm Tắt Namespace trong TypeScript là một cách để tổ chức mã nguồn, giúp nhóm các thành phầ...
Meta Keywords: namespace, dụng, các, trong, typescript
-->

# Namespace trong TypeScript: Tổ Chức Mã Nguồn Hiệu Quả

## Tóm Tắt
Namespace trong TypeScript là một cách để tổ chức mã nguồn, giúp nhóm các thành phần liên quan lại với nhau và tránh xung đột giữa các biến hoặc hàm có tên giống nhau trong các phần khác nhau của ứng dụng.

## Tài Liệu
Namespace là một tính năng quan trọng trong TypeScript, cho phép lập trình viên tổ chức mã nguồn của họ thành các khối logic riêng biệt. Điều này đặc biệt hữu ích trong các ứng dụng lớn, nơi mà việc quản lý tên biến và hàm có thể trở nên khó khăn. 

### Mục Đích
- **Tổ chức mã nguồn**: Giúp mã nguồn trở nên rõ ràng và dễ quản lý hơn.
- **Tránh xung đột tên**: Cho phép sử dụng các tên giống nhau trong các không gian khác nhau mà không gây ra xung đột.

### Cách Sử Dụng
Namespace được định nghĩa bằng từ khóa `namespace`, theo sau là tên của namespace. Bạn có thể định nghĩa các biến, hàm, và lớp bên trong namespace này.

```typescript
namespace MyNamespace {
    export function myFunction() {
        console.log("Hello from MyNamespace!");
    }
}
```

### Xuất khẩu
Các thành phần bên trong namespace cần được đánh dấu là `export` nếu bạn muốn sử dụng chúng từ bên ngoài namespace.

### Gọi hàm từ Namespace
Bạn có thể gọi hàm từ namespace bằng cách sử dụng cú pháp `NamespaceName.FunctionName`.

```typescript
MyNamespace.myFunction(); // Kết quả: Hello from MyNamespace!
```

## Ví Dụ
### Ví dụ cơ bản về Namespace
```typescript
namespace MathUtilities {
    export function add(a: number, b: number): number {
        return a + b;
    }

    export function subtract(a: number, b: number): number {
        return a - b;
    }
}

console.log(MathUtilities.add(5, 3)); // Kết quả: 8
console.log(MathUtilities.subtract(5, 3)); // Kết quả: 2
```

### Kết hợp với Class
```typescript
namespace Shapes {
    export class Circle {
        constructor(public radius: number) {}
        
        area(): number {
            return Math.PI * this.radius * this.radius;
        }
    }
}

const myCircle = new Shapes.Circle(5);
console.log(myCircle.area()); // Kết quả: 78.53981633974483
```

## Giải Thích
### Những Cạm Bẫy Thường Gặp
- **Xung đột tên**: Nếu không sử dụng `export`, các thành phần trong namespace sẽ không thể truy cập từ bên ngoài, dẫn đến lỗi không tìm thấy.
- **Sử dụng không đúng cách**: Namespace không nên được sử dụng như một cách để thay thế module. Đối với các ứng dụng lớn và phức tạp, hãy xem xét sử dụng module ES6.

### Lưu Ý Thêm
- Namespace thường được sử dụng trong các dự án nhỏ hoặc khi không cần đến hệ thống module phức tạp.
- Với sự phát triển của ES6, việc sử dụng module thay cho namespace ngày càng trở nên phổ biến hơn.

## Tóm Tắt Một Dòng
Namespace trong TypeScript cung cấp một phương pháp hiệu quả để tổ chức mã nguồn và tránh xung đột tên trong các ứng dụng lớn.