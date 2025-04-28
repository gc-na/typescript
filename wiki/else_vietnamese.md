<!--
Meta Description: # Câu Lệnh "else" trong TypeScript: Hướng Dẫn Chi Tiết ## Tóm tắt Câu lệnh "else" trong TypeScript được sử dụng để xác định một khối mã sẽ được thực t...
Meta Keywords: else, trong, điều, kiện, câu
-->

# Câu Lệnh "else" trong TypeScript: Hướng Dẫn Chi Tiết

## Tóm tắt
Câu lệnh "else" trong TypeScript được sử dụng để xác định một khối mã sẽ được thực thi khi điều kiện trong câu lệnh "if" không thỏa mãn. Đây là một phần quan trọng trong lập trình điều kiện, giúp quản lý luồng chương trình hiệu quả.

## Tài liệu
### Mục đích
Câu lệnh "else" cho phép lập trình viên xử lý các tình huống khi điều kiện ban đầu không được thỏa mãn. Nó giúp nâng cao khả năng kiểm soát và quyết định trong mã nguồn.

### Cú pháp
Câu lệnh "else" thường được sử dụng kết hợp với "if". Cú pháp cơ bản như sau:

```typescript
if (điều_kiện) {
    // Khối mã sẽ chạy nếu điều kiện thỏa mãn
} else {
    // Khối mã sẽ chạy nếu điều kiện không thỏa mãn
}
```

### Chi tiết
- **Điều kiện**: Là một biểu thức Boolean. Nếu biểu thức này trả về `true`, khối mã trong `if` sẽ được thực thi. Nếu trả về `false`, khối mã trong `else` sẽ được thực thi.
- **Khối mã**: Là đoạn mã sẽ được thực thi dựa trên giá trị của điều kiện.

## Ví dụ
### Ví dụ cơ bản
```typescript
let điểm: number = 75;

if (điểm >= 60) {
    console.log("Bạn đã đậu.");
} else {
    console.log("Bạn đã rớt.");
}
```
Trong ví dụ này, nếu `điểm` lớn hơn hoặc bằng 60, chương trình sẽ in ra "Bạn đã đậu." Ngược lại, nó sẽ in ra "Bạn đã rớt."

### Ví dụ với nhiều câu lệnh
```typescript
let tuổi: number = 20;

if (tuổi < 18) {
    console.log("Bạn là trẻ em.");
} else {
    console.log("Bạn là người lớn.");
}
```
Ở đây, nếu `tuổi` dưới 18, chương trình sẽ in "Bạn là trẻ em." Nếu không, nó sẽ in "Bạn là người lớn."

## Giải thích
### Những cạm bẫy thường gặp
- **Quên dấu ngoặc nhọn**: Nếu bạn quên đặt dấu ngoặc nhọn `{}` cho khối mã trong `else`, chỉ một câu lệnh ngay sau `else` sẽ được thực thi.
- **Điều kiện không chính xác**: Đảm bảo rằng điều kiện trong `if` là chính xác để tránh thực thi các khối mã không mong muốn.
  
### Ghi chú bổ sung
- Bạn có thể kết hợp `else` với `if` để tạo ra các câu lệnh điều kiện phức tạp hơn thông qua `else if`.

## Tóm tắt một dòng
Câu lệnh "else" trong TypeScript cho phép thực hiện khối mã khi điều kiện trong câu lệnh "if" không thỏa mãn.