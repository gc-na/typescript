<!--
Meta Description: # Câu Lệnh "break" Trong TypeScript: Hướng Dẫn Chi Tiết và Ví Dụ Cụ Thể ## Tóm Tắt Câu lệnh `break` trong TypeScript được sử dụng để thoát khỏi một vò...
Meta Keywords: break, trong, lặp, lệnh, vòng
-->

# Câu Lệnh "break" Trong TypeScript: Hướng Dẫn Chi Tiết và Ví Dụ Cụ Thể

## Tóm Tắt
Câu lệnh `break` trong TypeScript được sử dụng để thoát khỏi một vòng lặp hoặc một khối switch, giúp điều khiển luồng thực thi của chương trình một cách hiệu quả.

## Tài Liệu
### Mục Đích
Câu lệnh `break` cho phép lập trình viên ngừng việc thực thi trong một vòng lặp hoặc rời khỏi một khối điều kiện switch. Điều này rất hữu ích khi bạn muốn dừng quá trình lặp lại dựa trên một điều kiện cụ thể hoặc khi một giá trị nào đó đã được tìm thấy.

### Cách Sử Dụng
Câu lệnh `break` có thể được sử dụng trong các vòng lặp như `for`, `while`, và `do...while`, cũng như trong các câu lệnh `switch`. Dưới đây là cú pháp cơ bản:

```typescript
break;
```

Khi gặp câu lệnh `break`, chương trình sẽ thoát khỏi vòng lặp hoặc câu lệnh switch ngay lập tức.

### Chi Tiết
- **Trong Vòng Lặp:** Khi bạn sử dụng `break` trong một vòng lặp, nó sẽ dừng vòng lặp ngay lập tức và tiếp tục với mã lệnh sau vòng lặp.
- **Trong Câu Lệnh Switch:** Khi sử dụng `break` trong một câu lệnh switch, nó sẽ ngăn chặn việc thực thi các nhánh tiếp theo sau nhánh đã được thực thi.

## Ví Dụ
### Ví Dụ 1: Sử Dụng Trong Vòng Lặp
```typescript
for (let i = 0; i < 10; i++) {
    if (i === 5) {
        break; // Thoát khỏi vòng lặp khi i bằng 5
    }
    console.log(i);
}
// Kết quả: 0, 1, 2, 3, 4
```

### Ví Dụ 2: Sử Dụng Trong Câu Lệnh Switch
```typescript
let fruit = "apple";

switch (fruit) {
    case "banana":
        console.log("This is a banana.");
        break;
    case "apple":
        console.log("This is an apple.");
        break; // Thoát sau khi đã xử lý trường hợp "apple"
    default:
        console.log("Unknown fruit.");
}
// Kết quả: This is an apple.
```

## Giải Thích
### Những Lỗi Thường Gặp
- **Quên Câu Lệnh `break`:** Một trong những lỗi phổ biến là quên thêm câu lệnh `break` trong câu lệnh switch, dẫn đến việc thực thi tất cả các nhánh tiếp theo (điều này được gọi là "fall-through").
- **Sử Dụng `break` Trong Vòng Lặp Không Đúng:** Đảm bảo rằng bạn chỉ sử dụng `break` trong các vòng lặp hoặc switch, không sử dụng ở nơi khác sẽ gây lỗi biên dịch.

### Các Ghi Chú Thêm
- Sử dụng `break` một cách hợp lý có thể làm cho mã của bạn dễ đọc và bảo trì hơn.
- Cần cân nhắc khi sử dụng `break` trong các vòng lặp lồng nhau, vì nó chỉ thoát khỏi vòng lặp gần nhất.

## Tóm Tắt Một Dòng
Câu lệnh `break` trong TypeScript cho phép thoát khỏi vòng lặp hoặc khối switch một cách hiệu quả, giúp điều khiển luồng thực thi của chương trình.