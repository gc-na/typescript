<!--
Meta Description: # Câu lệnh "switch" trong TypeScript: Cách sử dụng và ví dụ ## Tóm tắt Câu lệnh "switch" trong TypeScript là một công cụ mạnh mẽ giúp kiểm tra giá trị...
Meta Keywords: switch, break, câu, trường, hợp
-->

# Câu lệnh "switch" trong TypeScript: Cách sử dụng và ví dụ

## Tóm tắt
Câu lệnh "switch" trong TypeScript là một công cụ mạnh mẽ giúp kiểm tra giá trị của một biến và thực thi các khối mã khác nhau dựa trên giá trị đó. Điều này giúp làm cho mã nguồn trở nên gọn gàng và dễ đọc hơn so với việc sử dụng nhiều cấu trúc điều kiện "if-else".

## Tài liệu
Câu lệnh "switch" cho phép lập trình viên kiểm tra một giá trị cụ thể (thường là một biến) và so sánh nó với nhiều trường hợp khác nhau. Cú pháp cơ bản của câu lệnh "switch" như sau:

```typescript
switch (biến) {
    case giá_trị_1:
        // Khối mã sẽ được thực thi nếu biến bằng giá_trị_1
        break;
    case giá_trị_2:
        // Khối mã sẽ được thực thi nếu biến bằng giá_trị_2
        break;
    default:
        // Khối mã sẽ được thực thi nếu không có case nào khớp
}
```

### Mục đích
Câu lệnh "switch" giúp cải thiện khả năng đọc hiểu và cấu trúc của mã bằng cách tổ chức các trường hợp khác nhau một cách rõ ràng. Điều này đặc biệt hữu ích khi bạn có nhiều điều kiện phức tạp.

### Cách sử dụng
- Đặt giá trị cần kiểm tra trong dấu ngoặc đơn sau từ khóa "switch".
- Mỗi trường hợp bắt đầu bằng từ khóa "case", theo sau là giá trị mà bạn muốn so sánh.
- Mỗi khối mã trong các trường hợp phải kết thúc bằng từ khóa "break" để ngăn chặn việc tiếp tục kiểm tra các trường hợp sau đó.
- Nếu không có trường hợp nào khớp, phần "default" sẽ được thực thi.

## Ví dụ
### Ví dụ 1: Câu lệnh "switch" đơn giản

```typescript
let diem: number = 85;

switch (diem) {
    case 90:
        console.log("Xuất sắc");
        break;
    case 80:
        console.log("Tốt");
        break;
    case 70:
        console.log("Khá");
        break;
    default:
        console.log("Cần cải thiện");
}
```

### Ví dụ 2: Sử dụng với chuỗi

```typescript
let trangThai: string = "hoạt động";

switch (trangThai) {
    case "hoạt động":
        console.log("Hệ thống đang hoạt động.");
        break;
    case "ngừng hoạt động":
        console.log("Hệ thống đã ngừng hoạt động.");
        break;
    default:
        console.log("Trạng thái không xác định.");
}
```

## Giải thích
### Những điểm cần lưu ý
- **Quên từ khóa "break":** Nếu bạn quên "break", mã sẽ tiếp tục chạy vào các trường hợp sau đó, điều này có thể dẫn đến kết quả không mong muốn.
- **So sánh kiểu dữ liệu:** Câu lệnh "switch" sử dụng so sánh nghiêm ngặt (strict comparison), vì vậy cần đảm bảo rằng kiểu dữ liệu của biến và các giá trị so sánh là giống nhau.
- **Nhiều trường hợp giống nhau:** Bạn có thể nhóm nhiều trường hợp lại với nhau nếu chúng cần thực hiện cùng một khối mã.

## Tóm tắt một câu
Câu lệnh "switch" trong TypeScript cho phép xử lý nhiều điều kiện theo cách rõ ràng và dễ hiểu, giúp cải thiện cấu trúc mã nguồn.