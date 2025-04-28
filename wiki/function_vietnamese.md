<!--
Meta Description: # Hàm trong TypeScript: Hướng dẫn chi tiết và ví dụ minh họa ## Tóm tắt Hàm trong TypeScript là một khái niệm cơ bản cho phép các lập trình viên định ...
Meta Keywords: hàm, typescript, kiểu, tham, một
-->

# Hàm trong TypeScript: Hướng dẫn chi tiết và ví dụ minh họa

## Tóm tắt
Hàm trong TypeScript là một khái niệm cơ bản cho phép các lập trình viên định nghĩa các đoạn mã có thể tái sử dụng, giúp tổ chức và tối ưu hóa mã nguồn hiệu quả hơn.

## Tài liệu
### Mục đích
Hàm trong TypeScript được sử dụng để nhóm các đoạn mã lại với nhau, cho phép thực hiện một nhiệm vụ cụ thể. Điều này giúp giảm thiểu mã lặp lại và cải thiện khả năng bảo trì của ứng dụng.

### Cách sử dụng
Để định nghĩa một hàm trong TypeScript, bạn sử dụng từ khóa `function`, theo sau là tên hàm, danh sách tham số và kiểu trả về (nếu có). Cú pháp cơ bản như sau:

```typescript
function tenHam(thamSo1: Kieu1, thamSo2: Kieu2): KieuTraVe {
    // Thân hàm
}
```

### Chi tiết
- **Tên hàm**: Phải tuân theo quy tắc đặt tên của JavaScript, không được bắt đầu bằng số và không chứa ký tự đặc biệt.
- **Tham số**: Có thể có hoặc không, mỗi tham số có thể có kiểu dữ liệu riêng, giúp TypeScript kiểm tra kiểu dữ liệu tại thời điểm biên dịch.
- **Kiểu trả về**: Nếu hàm trả về giá trị, bạn nên chỉ định kiểu dữ liệu cho giá trị đó. Nếu không, bạn có thể để trống hoặc sử dụng kiểu `void`.

## Ví dụ
### Ví dụ 1: Hàm không có tham số và không có kiểu trả về
```typescript
function sayHello(): void {
    console.log("Xin chào!");
}
sayHello();
```

### Ví dụ 2: Hàm có tham số và kiểu trả về
```typescript
function add(a: number, b: number): number {
    return a + b;
}
const result = add(5, 10);
console.log(result); // Kết quả: 15
```

### Ví dụ 3: Hàm với tham số tùy chọn
```typescript
function greet(name: string, greeting?: string): string {
    return `${greeting || "Xin chào"}, ${name}!`;
}
console.log(greet("Mai")); // Kết quả: Xin chào, Mai!
```

## Giải thích
- **Cạm bẫy phổ biến**: Một số lập trình viên mới có thể quên chỉ định kiểu cho tham số hoặc kiểu trả về, gây ra lỗi không mong muốn. Hãy chắc chắn rằng bạn luôn kiểm tra kiểu dữ liệu của tham số.
- **Lưu ý**: Trong TypeScript, hàm có thể được gán cho biến hoặc truyền như một tham số cho hàm khác. Điều này hỗ trợ lập trình hàm (functional programming) một cách tối ưu.

## Tóm tắt một câu
Hàm trong TypeScript là một công cụ mạnh mẽ cho phép tổ chức và tái sử dụng mã nguồn, tối ưu hóa quy trình phát triển ứng dụng.