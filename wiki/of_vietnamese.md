<!--
Meta Description: # Từ Khóa "of" Trong TypeScript: Cách Sử Dụng và Ý Nghĩa ## Tóm Tắt Từ khóa "of" trong TypeScript được sử dụng chủ yếu trong các vòng lặp `for...of`, ...
Meta Keywords: các, lặp, trong, typescript, của
-->

# Từ Khóa "of" Trong TypeScript: Cách Sử Dụng và Ý Nghĩa

## Tóm Tắt
Từ khóa "of" trong TypeScript được sử dụng chủ yếu trong các vòng lặp `for...of`, giúp lặp qua các phần tử của một iterable như mảng hoặc chuỗi một cách dễ dàng và hiệu quả.

## Tài Liệu
### Mục Đích
Từ khóa "of" cung cấp một cách đơn giản để duyệt qua các phần tử của các cấu trúc dữ liệu có thể lặp, giúp lập trình viên viết mã ngắn gọn và dễ đọc hơn.

### Cách Sử Dụng
Cú pháp của vòng lặp `for...of` như sau:

```typescript
for (const item of iterable) {
    // Xử lý item
}
```

Trong đó:
- `item` là biến sẽ nhận giá trị của từng phần tử trong `iterable`.
- `iterable` có thể là một mảng, chuỗi, hoặc bất kỳ đối tượng nào có thể lặp.

### Chi Tiết
- `for...of` được giới thiệu trong ES6 (ECMAScript 2015) và được TypeScript hỗ trợ hoàn toàn.
- Vòng lặp sẽ dừng lại khi không còn phần tử nào trong `iterable`.
- Khác với `for...in`, `for...of` chỉ lặp qua các giá trị của các phần tử, trong khi `for...in` lặp qua các thuộc tính của đối tượng.

## Ví Dụ
### Ví Dụ Cơ Bản
Dưới đây là một ví dụ đơn giản sử dụng `for...of` để lặp qua một mảng số:

```typescript
const numbers = [1, 2, 3, 4, 5];

for (const num of numbers) {
    console.log(num);
}
```

### Ví Dụ Với Chuỗi
```typescript
const greeting = "Xin chào";

for (const char of greeting) {
    console.log(char);
}
```

## Giải Thích
### Những Cạm Bẫy Phổ Biến
- **Không sử dụng với đối tượng không thể lặp**: Nếu bạn cố gắng sử dụng `for...of` với một đối tượng không phải là iterable, TypeScript sẽ báo lỗi. Đảm bảo rằng bạn chỉ sử dụng `for...of` với mảng, chuỗi, hoặc các iterable khác.
- **Khác với `for...in`**: Đối với các đối tượng, hãy tránh nhầm lẫn giữa `for...of` (dùng cho giá trị) và `for...in` (dùng cho thuộc tính). Điều này có thể gây ra lỗi không mong muốn trong mã của bạn.

## Tóm Tắt Một Dòng
Từ khóa "of" trong TypeScript cho phép lập trình viên dễ dàng duyệt qua các phần tử của các cấu trúc dữ liệu có thể lặp như mảng và chuỗi.