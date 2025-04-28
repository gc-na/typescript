<!--
Meta Description: # Từ Khóa "default" trong TypeScript: Hướng Dẫn Chi Tiết ## Tóm tắt Từ khóa "default" trong TypeScript được sử dụng để chỉ định các giá trị mặc định c...
Meta Keywords: định, mặc, typescript, giá, trị
-->

# Từ Khóa "default" trong TypeScript: Hướng Dẫn Chi Tiết

## Tóm tắt
Từ khóa "default" trong TypeScript được sử dụng để chỉ định các giá trị mặc định cho tham số trong hàm và cho phép xuất khẩu một thành phần từ module mà không cần tên.

## Tài liệu
### Mục đích
Từ khóa "default" giúp lập trình viên dễ dàng quản lý và tối ưu hóa mã nguồn trong TypeScript thông qua việc thiết lập các giá trị mặc định cho tham số của hàm, hoặc khi xuất khẩu thành phần từ module.

### Cách sử dụng
1. **Giá trị mặc định cho tham số hàm**: Khi định nghĩa một hàm, bạn có thể chỉ định giá trị mặc định cho các tham số. Nếu tham số không được cung cấp khi gọi hàm, giá trị mặc định sẽ được sử dụng.

   Ví dụ:
   ```typescript
   function greet(name: string = "Người dùng") {
       console.log(`Xin chào, ${name}!`);
   }

   greet(); // Kết quả: Xin chào, Người dùng!
   greet("An"); // Kết quả: Xin chào, An!
   ```

2. **Xuất khẩu mặc định**: Trong TypeScript, bạn có thể xuất khẩu một thành phần như hàm, lớp hoặc biến mà không cần chỉ định tên, bằng cách sử dụng từ khóa "default".

   Ví dụ:
   ```typescript
   // file: myModule.ts
   export default function add(x: number, y: number): number {
       return x + y;
   }

   // file: main.ts
   import add from './myModule';
   console.log(add(5, 10)); // Kết quả: 15
   ```

## Ví dụ
### Ví dụ về giá trị mặc định
```typescript
function multiply(a: number, b: number = 1): number {
    return a * b;
}

console.log(multiply(5)); // Kết quả: 5
console.log(multiply(5, 2)); // Kết quả: 10
```

### Ví dụ về xuất khẩu mặc định
```typescript
// file: calculator.ts
export default class Calculator {
    static add(a: number, b: number): number {
        return a + b;
    }
}

// file: app.ts
import Calculator from './calculator';
console.log(Calculator.add(2, 3)); // Kết quả: 5
```

## Giải thích
- **Cạm bẫy phổ biến**: Khi sử dụng giá trị mặc định, nếu không cẩn thận, bạn có thể gặp phải trường hợp không mong muốn khi tham số được truyền vào là `undefined`. Trong trường hợp này, giá trị mặc định sẽ không được sử dụng.
  
- **Lưu ý khi xuất khẩu**: Chỉ có một thành phần có thể được xuất khẩu mặc định từ mỗi file. Nếu bạn cố gắng xuất khẩu nhiều thành phần mặc định, TypeScript sẽ báo lỗi.

## Tóm tắt một dòng
Từ khóa "default" trong TypeScript cho phép chỉ định giá trị mặc định cho tham số hàm và xuất khẩu thành phần mà không cần tên.