<!--
Meta Description: # Từ Khóa "var" trong TypeScript: Cách Sử Dụng Và Lưu Ý Quan Trọng ## Tóm Tắt Từ khóa `var` trong TypeScript được sử dụng để khai báo biến với phạm vi...
Meta Keywords: được, biến, khai, báo, var
-->

# Từ Khóa "var" trong TypeScript: Cách Sử Dụng Và Lưu Ý Quan Trọng

## Tóm Tắt
Từ khóa `var` trong TypeScript được sử dụng để khai báo biến với phạm vi toàn cục hoặc phạm vi hàm, cho phép người dùng tạo ra các biến có thể được truy cập từ bất kỳ đâu trong hàm hoặc khối mã.

## Tài Liệu
### Mục Đích
Từ khóa `var` cung cấp một phương thức để khai báo biến trong TypeScript, nhưng nó có một số đặc điểm quan trọng mà lập trình viên cần nắm vững. Dù TypeScript khuyến khích sử dụng `let` và `const` để khai báo biến, `var` vẫn có thể được sử dụng trong một số tình huống nhất định.

### Cách Sử Dụng
Khi khai báo một biến bằng `var`, biến đó sẽ có phạm vi toàn cục nếu nó được khai báo bên ngoài bất kỳ hàm nào, hoặc phạm vi hàm nếu nó được khai báo bên trong một hàm. Điều này có nghĩa là biến có thể được truy cập từ bất kỳ nơi nào trong hàm hoặc ngoài hàm (nếu là phạm vi toàn cục).

**Cú pháp:**
```typescript
var variableName: type = value;
```

### Chi Tiết
- **Phạm vi**: Biến được khai báo với `var` có thể được truy cập từ bất kỳ nơi nào trong hàm. Nếu khai báo tại cấp độ toàn cục, nó có thể được truy cập từ bất kỳ hàm nào trong tệp mã.
- **Hoisting**: Các biến được khai báo bằng `var` sẽ được "hoisted", nghĩa là chúng sẽ được nâng lên đầu hàm hoặc phạm vi toàn cục, vì vậy bạn có thể sử dụng chúng trước khi chúng được khai báo. Tuy nhiên, giá trị của biến sẽ là `undefined` cho đến khi dòng khai báo được thực thi.

## Ví Dụ
```typescript
// Ví dụ 1: Khai báo biến toàn cục
var globalVar: string = "Hello, World!";

function greet() {
    console.log(globalVar);
}

greet(); // In ra: Hello, World!

// Ví dụ 2: Khai báo biến trong hàm
function example() {
    var localVar: number = 5;
    console.log(localVar);
}

example(); // In ra: 5
// console.log(localVar); // Lỗi: localVar không định nghĩa
```

## Giải Thích
- **Những cạm bẫy phổ biến**: Do `var` có phạm vi hàm, việc sử dụng nó có thể gây ra những kết quả không mong muốn nếu bạn không cẩn thận. Nếu sử dụng bên trong vòng lặp, biến sẽ tồn tại sau vòng lặp, có thể dẫn đến lỗi logic.
- **Khuyến nghị**: Trong hầu hết các trường hợp, nên sử dụng `let` hoặc `const` thay vì `var` để giảm thiểu sự phức tạp và tăng khả năng duy trì mã.

## Tóm Tắt Một Dòng
Từ khóa `var` trong TypeScript được sử dụng để khai báo biến với phạm vi toàn cục hoặc hàm, nhưng có thể gây ra một số vấn đề do hành vi hoisting và phạm vi không mong muốn.