<!--
Meta Description: # Kiểu Dữ Liệu "unknown" trong TypeScript: Tìm Hiểu và Ứng Dụng ## Tóm Tắt Kiểu dữ liệu `unknown` trong TypeScript là một kiểu dữ liệu an toàn hơn so ...
Meta Keywords: kiểu, dụng, unknown, typescript, giá
-->

# Kiểu Dữ Liệu "unknown" trong TypeScript: Tìm Hiểu và Ứng Dụng

## Tóm Tắt
Kiểu dữ liệu `unknown` trong TypeScript là một kiểu dữ liệu an toàn hơn so với kiểu `any`, cho phép bạn xác định rằng một biến có thể chứa bất kỳ giá trị nào, nhưng không thể truy cập vào các thuộc tính hoặc phương thức của nó cho đến khi xác định rõ ràng kiểu của nó.

## Tài Liệu
### Mục Đích
Kiểu `unknown` được giới thiệu trong TypeScript 3.0, nhằm cung cấp một cách an toàn để xử lý các giá trị không xác định. Khi sử dụng `unknown`, bạn có thể đảm bảo rằng các giá trị không được sử dụng một cách tùy tiện, giúp giảm thiểu các lỗi xảy ra trong quá trình biên dịch và chạy ứng dụng.

### Cách Sử Dụng
Khi bạn định nghĩa một biến với kiểu `unknown`, bạn cần phải thực hiện kiểm tra kiểu trước khi sử dụng nó. Điều này giúp bạn đảm bảo rằng bạn chỉ làm việc với loại dữ liệu mà bạn mong đợi, tránh được các lỗi không mong muốn.

Cú pháp chung để khai báo biến với kiểu `unknown` như sau:
```typescript
let variableName: unknown;
```

## Ví Dụ
### Ví dụ 1: Khai báo và sử dụng với kiểu unknown
```typescript
let value: unknown;

value = 42; // có thể gán giá trị số
console.log(value); // in ra 42

value = "Hello, TypeScript"; // có thể gán giá trị chuỗi
console.log(value); // in ra "Hello, TypeScript"

// Để sử dụng giá trị, cần phải kiểm tra kiểu
if (typeof value === "string") {
    console.log(value.toUpperCase()); // in ra giá trị chữ hoa
}
```

### Ví dụ 2: Kiểm tra kiểu trước khi sử dụng
```typescript
let data: unknown;

data = { name: "Alice", age: 30 }; // gán đối tượng

// Kiểm tra kiểu dữ liệu trước khi truy cập thuộc tính
if (typeof data === "object" && data !== null) {
    console.log((data as { name: string }).name); // in ra "Alice"
}
```

## Giải Thích
### Cạm Bẫy Thường Gặp
- **Sử dụng trực tiếp**: Một trong những sai lầm phổ biến là cố gắng sử dụng giá trị của biến `unknown` mà không kiểm tra kiểu, điều này sẽ dẫn đến lỗi biên dịch.
- **Sử dụng as**: Việc ép kiểu (`as`) không phải lúc nào cũng an toàn. Bạn nên thực hiện kiểm tra kiểu trước khi sử dụng.
- **Không thể gán cho một kiểu cụ thể**: Giá trị kiểu `unknown` không thể được gán trực tiếp cho các kiểu khác mà không có ép kiểu, điều này có thể gây nhầm lẫn cho những người mới làm quen với TypeScript.

## Tóm Tắt Một Câu
Kiểu `unknown` trong TypeScript cung cấp một cách an toàn để làm việc với các giá trị không xác định, yêu cầu kiểm tra kiểu trước khi sử dụng để tránh lỗi trong quá trình biên dịch và chạy ứng dụng.