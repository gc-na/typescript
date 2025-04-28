<!--
Meta Description: # Câu Lệnh "case" trong TypeScript: Cách Sử Dụng và Ví Dụ ## Tóm tắt Câu lệnh "case" trong TypeScript là một phần của câu lệnh điều kiện switch, cho p...
Meta Keywords: case, break, lệnh, câu, một
-->

# Câu Lệnh "case" trong TypeScript: Cách Sử Dụng và Ví Dụ

## Tóm tắt
Câu lệnh "case" trong TypeScript là một phần của câu lệnh điều kiện switch, cho phép lập trình viên kiểm tra giá trị của một biểu thức và thực hiện các hành động khác nhau dựa trên giá trị đó.

## Tài liệu
### Mục đích
Câu lệnh "case" được sử dụng trong cấu trúc điều kiện switch để so sánh giá trị của một biểu thức với nhiều giá trị khác nhau. Đây là một cách hiệu quả để xử lý nhiều điều kiện mà không cần phải sử dụng nhiều câu lệnh if-else.

### Cách sử dụng
Câu lệnh "case" thường được sử dụng như sau:

```typescript
switch (expression) {
    case value1:
        // Thực hiện hành động 1
        break;
    case value2:
        // Thực hiện hành động 2
        break;
    default:
        // Thực hiện hành động mặc định
}
```

- `expression`: Biểu thức cần kiểm tra.
- `case valueX`: Giá trị để so sánh với biểu thức.
- `break`: Kết thúc câu lệnh switch sau khi thực hiện một case.
- `default`: Tùy chọn, thực hiện nếu không có case nào khớp.

### Chi tiết
- Mỗi case có thể chứa một hoặc nhiều lệnh.
- Nếu không có break, chương trình sẽ tiếp tục thực thi các case tiếp theo (tính năng gọi là "fall-through").
- Có thể sử dụng nhiều giá trị cho một case bằng cách ngăn cách chúng bằng dấu phẩy.

## Ví dụ
### Ví dụ Cơ Bản
```typescript
let day: number = 3;
let dayName: string;

switch (day) {
    case 1:
        dayName = "Chủ Nhật";
        break;
    case 2:
        dayName = "Thứ Hai";
        break;
    case 3:
        dayName = "Thứ Ba";
        break;
    default:
        dayName = "Ngày không hợp lệ";
}

console.log(dayName); // Kết quả: Thứ Ba
```

### Ví dụ với Nhiều Giá Trị
```typescript
let fruit: string = "Táo";

switch (fruit) {
    case "Chuối":
    case "Táo":
        console.log("Trái cây này ngon!");
        break;
    case "Cam":
        console.log("Trái cây này chua!");
        break;
    default:
        console.log("Trái cây không xác định.");
}
```

## Giải thích
- **Cảnh báo về break**: Nếu bạn quên thêm break, các case sau sẽ tự động được thực thi, có thể dẫn đến hành vi không mong muốn.
- **Sử dụng default**: Câu lệnh default là tùy chọn, nhưng rất hữu ích để xử lý các trường hợp không được định nghĩa trước.
- **Kiểu dữ liệu**: Các giá trị trong case có thể là số, chuỗi, hoặc bất kỳ kiểu dữ liệu nào khác phù hợp với biểu thức.

## Tóm tắt Một Dòng
Câu lệnh "case" trong TypeScript cho phép xử lý nhiều điều kiện khác nhau một cách hiệu quả thông qua cấu trúc switch.