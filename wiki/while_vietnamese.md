<!--
Meta Description: # Vòng Lặp "while" Trong TypeScript: Cách Sử Dụng và Ví Dụ ## Tóm Tắt Vòng lặp "while" trong TypeScript cho phép thực hiện một đoạn mã nhiều lần miễn ...
Meta Keywords: lặp, vòng, điều, kiện, while
-->

# Vòng Lặp "while" Trong TypeScript: Cách Sử Dụng và Ví Dụ

## Tóm Tắt
Vòng lặp "while" trong TypeScript cho phép thực hiện một đoạn mã nhiều lần miễn là điều kiện cho trước vẫn đúng. Đây là một công cụ mạnh mẽ để lặp qua các cấu trúc dữ liệu hoặc thực hiện các tác vụ lặp lại.

## Tài Liệu
Vòng lặp "while" được sử dụng để lặp lại một khối mã cho đến khi điều kiện được chỉ định trở thành sai. Cấu trúc cơ bản của vòng lặp "while" như sau:

```typescript
while (điều kiện) {
    // Khối mã cần thực thi
}
```

### Mục Đích
Vòng lặp "while" thường được sử dụng khi số lần lặp không được xác định trước. Điều này thường xảy ra khi bạn cần lặp cho đến khi một điều kiện cụ thể được đáp ứng, như trong các trường hợp xử lý dữ liệu hoặc nhập liệu từ người dùng.

### Cách Sử Dụng
- Đặt điều kiện lặp trong ngoặc đơn.
- Đảm bảo rằng điều kiện sẽ trở thành sai tại một thời điểm nào đó để tránh vòng lặp vô hạn.
- Khối mã bên trong sẽ được thực thi mỗi khi điều kiện là đúng.

## Ví Dụ
### Ví Dụ 1: Vòng Lặp Đếm Ngược
```typescript
let count: number = 5;

while (count > 0) {
    console.log(count);
    count--; // Giảm giá trị của count
}
```
Kết quả sẽ là:
```
5
4
3
2
1
```

### Ví Dụ 2: Nhập Liệu từ Người Dùng
```typescript
let input: string;
let validInput: boolean = false;

while (!validInput) {
    input = prompt("Nhập một số dương:") || "";
    if (parseInt(input) > 0) {
        validInput = true;
    }
}
console.log("Bạn đã nhập: " + input);
```

## Giải Thích
### Những Lỗi Thường Gặp
- **Vòng Lặp Vô Hạn**: Nếu điều kiện trong vòng lặp không bao giờ trở thành sai, chương trình sẽ mắc kẹt trong vòng lặp. Đảm bảo rằng có điều kiện để thoát khỏi vòng lặp.
- **Hiệu Năng**: Sử dụng vòng lặp "while" không phải lúc nào cũng là lựa chọn tốt nhất. Trong một số trường hợp, bạn nên xem xét sử dụng vòng lặp "for" hoặc "do...while" để cải thiện tính rõ ràng và hiệu suất của mã.

### Ghi Chú Bổ Sung
- Vòng lặp "while" thực thi khối mã chỉ khi điều kiện đúng, có thể dẫn đến việc khối mã không bao giờ được thực thi nếu điều kiện ngay từ đầu đã sai.
- Cần cẩn trọng khi thao tác với biến điều kiện để đảm bảo tính đúng đắn của vòng lặp.

## Tóm Tắt Một Câu
Vòng lặp "while" trong TypeScript cho phép lặp lại một khối mã miễn là điều kiện được xác định là đúng, nhưng cần phải cẩn thận để tránh vòng lặp vô hạn.