<!--
Meta Description: # Tìm Hiểu Về Kiểu Dữ Liệu Symbol Trong TypeScript ## Tóm Tắt Kiểu dữ liệu `symbol` trong TypeScript được sử dụng để tạo ra các giá trị duy nhất, thườ...
Meta Keywords: symbol, giá, trị, một, không
-->

# Tìm Hiểu Về Kiểu Dữ Liệu Symbol Trong TypeScript

## Tóm Tắt
Kiểu dữ liệu `symbol` trong TypeScript được sử dụng để tạo ra các giá trị duy nhất, thường được sử dụng làm khóa cho các thuộc tính của đối tượng mà không bị xung đột với các thuộc tính khác.

## Tài Liệu
### Mục Đích
`symbol` là một kiểu dữ liệu mới được giới thiệu trong ECMAScript 2015 (ES6) và TypeScript hỗ trợ kiểu dữ liệu này. Mục đích chính của `symbol` là tạo ra các giá trị duy nhất, giúp tránh xung đột trong việc sử dụng các thuộc tính của đối tượng.

### Cách Sử Dụng
Để tạo ra một giá trị `symbol`, bạn có thể sử dụng hàm `Symbol()`. Dưới đây là cú pháp cơ bản:
```typescript
const mySymbol = Symbol('description');
```
Trong đó, `'description'` là một chuỗi mô tả tùy chọn, giúp bạn nhận diện `symbol` khi cần thiết, nhưng không ảnh hưởng đến tính duy nhất của nó.

### Chi Tiết
- Mỗi giá trị `symbol` đều là duy nhất, ngay cả khi chúng có cùng mô tả.
- `symbol` không thể được chuyển đổi thành chuỗi hoặc số, và chúng không hiển thị khi bạn cố gắng in đối tượng mà chứa chúng.
- Bạn có thể sử dụng `symbol` như là khóa cho các thuộc tính của đối tượng, điều này giúp bảo vệ các thuộc tính khỏi việc bị ghi đè hoặc truy cập không mong muốn.

## Ví Dụ
### Tạo và Sử Dụng Symbol
```typescript
const sym1 = Symbol('mySymbol');
const sym2 = Symbol('mySymbol');

console.log(sym1 === sym2); // false, vì mỗi symbol là duy nhất

const obj = {
    [sym1]: 'Giá trị cho symbol 1',
};

console.log(obj[sym1]); // 'Giá trị cho symbol 1'
console.log(obj[sym2]); // undefined, vì sym2 không phải là khóa của obj
```

### Sử Dụng Symbol Trong Đối Tượng
```typescript
const mySymbol = Symbol('uniqueKey');

const myObj = {
    [mySymbol]: 'Đây là một giá trị bí mật',
};

console.log(myObj[mySymbol]); // 'Đây là một giá trị bí mật'
```

## Giải Thích
- **Cạm Bẫy Thường Gặp**: Một số lập trình viên mới có thể không nhận ra rằng `symbol` không phải là một chuỗi hay số, do đó không thể thực hiện các phép toán so sánh hoặc chuyển đổi giữa chúng.
- **Tính Duy Nhất**: Hãy nhớ rằng mỗi lần gọi `Symbol()` sẽ trả về một giá trị duy nhất, ngay cả khi bạn truyền vào cùng một mô tả.
- **Khó Khăn Khi Debug**: Nếu bạn in ra một đối tượng chứa `symbol`, giá trị của nó sẽ không được hiển thị trong bảng điều khiển, do đó có thể gây khó khăn cho quá trình gỡ lỗi.

## Tóm Tắt Một Dòng
Kiểu dữ liệu `symbol` trong TypeScript cho phép tạo ra giá trị duy nhất, giúp bảo vệ thuộc tính của đối tượng khỏi xung đột.