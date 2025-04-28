<!--
Meta Description: # undefined trong TypeScript: Khám Phá và Ứng Dụng ## Tóm tắt Trong TypeScript, `undefined` là một kiểu dữ liệu cơ bản, đại diện cho giá trị không xác...
Meta Keywords: undefined, giá, trị, biến, một
-->

# undefined trong TypeScript: Khám Phá và Ứng Dụng

## Tóm tắt
Trong TypeScript, `undefined` là một kiểu dữ liệu cơ bản, đại diện cho giá trị không xác định. Nó thường được sử dụng để chỉ ra rằng một biến đã được khai báo nhưng chưa được gán giá trị.

## Tài liệu
`undefined` là một trong hai giá trị đặc biệt trong JavaScript và TypeScript (giá trị còn lại là `null`). Khi một biến được khai báo mà không được gán giá trị, nó sẽ tự động có giá trị là `undefined`. Điều này giúp lập trình viên xác định xem một biến đã được khởi tạo hay chưa.

### Mục đích
- Để biểu thị rằng một biến chưa có giá trị.
- Để kiểm tra các điều kiện trong mã, giúp xử lý lỗi và gỡ lỗi hiệu quả hơn.

### Cách sử dụng
Trong TypeScript, bạn có thể khai báo một biến có kiểu `undefined` như sau:

```typescript
let myVar: undefined;
myVar = undefined; // Đúng
```

Bạn cũng có thể khai báo một biến có thể nhận giá trị `undefined` cùng với các kiểu dữ liệu khác bằng cách sử dụng toán tử `|`:

```typescript
let myVar: string | undefined;
myVar = "Hello"; // Đúng
myVar = undefined; // Đúng
```

## Ví dụ
### 1. Biến chưa được gán giá trị
```typescript
let x: number;
console.log(x); // Kết quả: undefined
```

### 2. Biến có thể là undefined
```typescript
function greet(name: string | undefined) {
    if (name === undefined) {
        console.log("Xin chào, khách!");
    } else {
        console.log(`Xin chào, ${name}!`);
    }
}

greet(undefined); // Kết quả: Xin chào, khách!
greet("Minh");    // Kết quả: Xin chào, Minh!
```

### 3. Sử dụng trong Object
```typescript
interface User {
    name: string;
    age?: number; // age có thể là undefined
}

const user1: User = { name: "An" };
console.log(user1.age); // Kết quả: undefined
```

## Giải thích
- **Cái bẫy phổ biến**: Một số lập trình viên có thể nhầm lẫn giữa `undefined` và `null`. Trong khi `undefined` biểu thị rằng biến chưa được gán giá trị, `null` biểu thị rằng biến đã được gán nhưng không có giá trị.
- **Kiểm tra giá trị**: Khi kiểm tra giá trị của biến, bạn nên xác minh rằng nó không phải là `undefined` trước khi sử dụng để tránh lỗi runtime.

## Tóm tắt một dòng
`undefined` trong TypeScript là một kiểu dữ liệu dùng để biểu thị rằng một biến chưa được gán giá trị, giúp lập trình viên nhận biết trạng thái của biến trong mã nguồn.