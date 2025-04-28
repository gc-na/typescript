<!--
Meta Description: # Từ Khóa "static" trong TypeScript: Hướng Dẫn Chi Tiết và Ứng Dụng ## Tóm Tắt Từ khóa `static` trong TypeScript cho phép định nghĩa các thuộc tính và...
Meta Keywords: static, thể, các, một, lớp
-->

# Từ Khóa "static" trong TypeScript: Hướng Dẫn Chi Tiết và Ứng Dụng

## Tóm Tắt
Từ khóa `static` trong TypeScript cho phép định nghĩa các thuộc tính và phương thức mà không cần tạo một thể hiện của lớp. Điều này giúp tối ưu hóa bộ nhớ và tăng cường khả năng quản lý mã nguồn.

## Tài Liệu
Trong TypeScript, từ khóa `static` được sử dụng để khai báo các thành viên tĩnh trong một lớp. Các thành viên này có thể là thuộc tính hoặc phương thức, và chúng có thể được truy cập trực tiếp thông qua tên lớp mà không cần khởi tạo một thể hiện của lớp đó.

### Mục Đích
- Để cung cấp các phương thức và thuộc tính có thể được sử dụng mà không cần tạo một thể hiện của lớp.
- Để chia sẻ dữ liệu hoặc hành vi chung cho tất cả các thể hiện của lớp.

### Cách Sử Dụng
Để sử dụng từ khóa `static`, bạn chỉ cần thêm nó trước thuộc tính hoặc phương thức trong định nghĩa lớp. Dưới đây là cú pháp cơ bản:

```typescript
class ClassName {
    static propertyName: Type;

    static methodName(parameters): ReturnType {
        // Thực hiện một số thao tác
    }
}
```

## Ví Dụ
Dưới đây là một số ví dụ cơ bản về cách sử dụng từ khóa `static` trong TypeScript:

### Ví dụ 1: Thuộc tính tĩnh
```typescript
class MathUtil {
    static PI: number = 3.14;

    static getArea(radius: number): number {
        return this.PI * radius * radius;
    }
}

console.log(MathUtil.PI); // Output: 3.14
console.log(MathUtil.getArea(5)); // Output: 78.5
```

### Ví dụ 2: Phương thức tĩnh
```typescript
class Counter {
    static count: number = 0;

    static increment() {
        this.count++;
    }

    static getCount(): number {
        return this.count;
    }
}

Counter.increment();
Counter.increment();
console.log(Counter.getCount()); // Output: 2
```

## Giải Thích
Khi sử dụng từ khóa `static`, bạn cần lưu ý một số điều sau:

1. **Không thể truy cập từ instance**: Các thành viên tĩnh không thể được truy cập thông qua một thể hiện của lớp. Ví dụ:
   ```typescript
   const counter = new Counter();
   // counter.increment(); // Lỗi: increment là phương thức tĩnh
   ```

2. **Những hạn chế về kế thừa**: Các thành viên tĩnh có thể được kế thừa, nhưng chúng không thể được ghi đè trong các lớp con.

3. **Quản lý bộ nhớ**: Sử dụng các thành viên tĩnh giúp tiết kiệm bộ nhớ vì chỉ có một bản sao của thuộc tính hoặc phương thức tĩnh tồn tại.

## Tóm Tắt Một Dòng
Từ khóa `static` trong TypeScript cho phép định nghĩa các thuộc tính và phương thức mà không cần tạo thể hiện của lớp, giúp tối ưu hóa quản lý mã nguồn.