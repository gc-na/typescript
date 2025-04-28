<!--
Meta Description: # Từ Khóa "true" trong TypeScript: Định Nghĩa và Cách Sử Dụng ## Tóm tắt Trong TypeScript, từ khóa "true" là một trong hai giá trị boolean cơ bản, cùn...
Meta Keywords: trong, true, dụng, typescript, một
-->

# Từ Khóa "true" trong TypeScript: Định Nghĩa và Cách Sử Dụng

## Tóm tắt
Trong TypeScript, từ khóa "true" là một trong hai giá trị boolean cơ bản, cùng với "false". Nó được sử dụng để biểu thị trạng thái đúng trong các biểu thức điều kiện và quyết định luồng chương trình.

## Tài liệu
### Mục đích
Giá trị `true` trong TypeScript dùng để biểu diễn một giá trị đúng trong các ngữ cảnh mà boolean được yêu cầu. Nó có thể được sử dụng trong các biểu thức điều kiện, vòng lặp, và các phép so sánh.

### Cách sử dụng
Giá trị `true` có thể được sử dụng trong bất kỳ phần nào của mã TypeScript nơi mà giá trị boolean được yêu cầu. Dưới đây là một ví dụ đơn giản về cách sử dụng `true` trong một điều kiện if.

```typescript
let isActive: boolean = true;

if (isActive) {
    console.log("Đối tượng đang hoạt động.");
}
```

### Chi tiết
- **Kiểu dữ liệu**: Trong TypeScript, `true` là một giá trị của kiểu `boolean`, có thể được khai báo như sau:
  ```typescript
  let isAvailable: boolean = true;
  ```

- **Biểu thức điều kiện**: Giá trị `true` có thể được sử dụng trong các biểu thức điều kiện để kiểm tra trạng thái của một biến hoặc biểu thức khác.
  
- **Sử dụng trong vòng lặp**: Bạn cũng có thể sử dụng `true` trong vòng lặp, mặc dù thường thì các vòng lặp sẽ yêu cầu một điều kiện phức tạp hơn.
  
  ```typescript
  let count: number = 0;
  while (true) {
      console.log(count);
      count++;
      if (count > 5) break;  // Kết thúc vòng lặp khi count lớn hơn 5
  }
  ```

## Ví dụ
### Ví dụ 1: Sử dụng trong điều kiện
```typescript
let isLoggedIn: boolean = true;

if (isLoggedIn) {
    console.log("Chào mừng bạn đến với trang web!");
} else {
    console.log("Xin vui lòng đăng nhập.");
}
```

### Ví dụ 2: Sử dụng trong vòng lặp
```typescript
let index: number = 0;

while (true) {
    console.log("Lặp số: " + index);
    index++;
    if (index >= 3) break;  // Kết thúc sau 3 lần lặp
}
```

## Giải thích
- **Cạm bẫy phổ biến**: Một số lập trình viên có thể nhầm lẫn khi sử dụng giá trị `true` trong các biểu thức phức tạp. Đảm bảo rằng bạn luôn kiểm tra điều kiện đúng cách để tránh lỗi không mong muốn.
  
- **Kiểu dữ liệu**: Khi bạn khai báo một biến là kiểu `boolean`, hãy chắc chắn rằng bạn chỉ gán cho nó các giá trị `true` hoặc `false`. Gán các kiểu dữ liệu khác có thể dẫn đến lỗi biên dịch.

## Tóm tắt một dòng
Giá trị `true` trong TypeScript là một phần thiết yếu của kiểu dữ liệu boolean, được sử dụng để biểu thị trạng thái đúng trong các biểu thức điều kiện và vòng lặp.