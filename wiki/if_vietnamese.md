<!--
Meta Description: # Câu lệnh "if" trong TypeScript: Cách sử dụng và ví dụ ## Tóm tắt Câu lệnh "if" trong TypeScript được sử dụng để kiểm tra điều kiện và thực hiện một ...
Meta Keywords: điều, kiện, câu, lệnh, typescript
-->

# Câu lệnh "if" trong TypeScript: Cách sử dụng và ví dụ

## Tóm tắt
Câu lệnh "if" trong TypeScript được sử dụng để kiểm tra điều kiện và thực hiện một đoạn mã dựa trên kết quả của điều kiện đó. Đây là một trong những cấu trúc điều khiển cơ bản nhất trong lập trình.

## Tài liệu
Câu lệnh "if" cho phép lập trình viên đưa ra các quyết định trong mã nguồn. Khi điều kiện trong câu lệnh "if" được đánh giá là true (đúng), đoạn mã bên trong khối "if" sẽ được thực thi. Ngược lại, nếu điều kiện là false (sai), đoạn mã sẽ bị bỏ qua. 

Cú pháp cơ bản của câu lệnh "if" như sau:

```typescript
if (điều kiện) {
    // đoạn mã sẽ được thực thi nếu điều kiện là true
}
```

TypeScript hỗ trợ các biến kiểu dữ liệu khác nhau cho điều kiện, bao gồm boolean, number, string, và nhiều kiểu dữ liệu khác. Ngoài ra, bạn có thể mở rộng câu lệnh "if" với "else" hoặc "else if" để xử lý nhiều điều kiện.

Cú pháp với "else" như sau:

```typescript
if (điều kiện) {
    // đoạn mã sẽ được thực thi nếu điều kiện là true
} else {
    // đoạn mã sẽ được thực thi nếu điều kiện là false
}
```

Và với "else if":

```typescript
if (điều kiện1) {
    // đoạn mã sẽ được thực thi nếu điều kiện1 là true
} else if (điều kiện2) {
    // đoạn mã sẽ được thực thi nếu điều kiện2 là true
} else {
    // đoạn mã sẽ được thực thi nếu cả hai điều kiện trên đều false
}
```

## Ví dụ
Dưới đây là một số ví dụ minh họa cách sử dụng câu lệnh "if" trong TypeScript:

### Ví dụ 1: Câu lệnh "if" đơn giản
```typescript
let age: number = 18;

if (age >= 18) {
    console.log("Bạn đã đủ tuổi.");
}
```

### Ví dụ 2: Câu lệnh "if" với "else"
```typescript
let isLoggedIn: boolean = false;

if (isLoggedIn) {
    console.log("Chào mừng bạn đến với trang cá nhân.");
} else {
    console.log("Vui lòng đăng nhập.");
}
```

### Ví dụ 3: Câu lệnh "if" với "else if"
```typescript
let score: number = 85;

if (score >= 90) {
    console.log("Điểm A");
} else if (score >= 80) {
    console.log("Điểm B");
} else {
    console.log("Điểm C");
}
```

## Giải thích
Một số lưu ý quan trọng khi sử dụng câu lệnh "if":

- **Kiểm tra kiểu dữ liệu**: Đảm bảo rằng điều kiện bạn kiểm tra là hợp lệ và có thể đánh giá được. Việc sử dụng các kiểu dữ liệu không tương thích có thể dẫn đến kết quả không mong muốn.
- **Sự khác biệt giữa `==` và `===`**: Trong TypeScript, bạn nên sử dụng `===` để so sánh giá trị và kiểu dữ liệu để tránh các lỗi tiềm ẩn.
- **Nesting (lồng ghép)**: Tránh lồng ghép quá nhiều câu lệnh "if" vì điều này có thể làm cho mã trở nên khó đọc. Thay vào đó, hãy cân nhắc việc sử dụng cấu trúc khác như switch-case hoặc các hàm riêng biệt.

## Tóm tắt ngắn gọn
Câu lệnh "if" trong TypeScript cho phép kiểm tra điều kiện và thực thi mã dựa trên kết quả của điều kiện đó, giúp lập trình viên đưa ra quyết định logic trong ứng dụng.