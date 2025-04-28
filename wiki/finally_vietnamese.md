<!--
Meta Description: # Từ Khóa "finally" Trong TypeScript: Cách Sử Dụng và Ý Nghĩa ## Tóm Tắt Từ khóa `finally` trong TypeScript được sử dụng trong cấu trúc điều kiện try-...
Meta Keywords: khối, lỗi, finally, try, trong
-->

# Từ Khóa "finally" Trong TypeScript: Cách Sử Dụng và Ý Nghĩa

## Tóm Tắt
Từ khóa `finally` trong TypeScript được sử dụng trong cấu trúc điều kiện try-catch để xác định một khối mã sẽ luôn được thực thi sau khi khối try hoặc catch hoàn thành, bất kể kết quả.

## Tài Liệu
### Mục Đích
Từ khóa `finally` giúp đảm bảo rằng một số mã nhất định sẽ được thực thi ngay cả khi có lỗi xảy ra trong khối try. Điều này hữu ích cho việc dọn dẹp tài nguyên hoặc thực hiện các thao tác cần thiết khác như đóng kết nối cơ sở dữ liệu, ghi nhật ký, hoặc bất kỳ hành động nào mà bạn muốn chắc chắn được thực hiện.

### Cú Pháp
Cấu trúc cơ bản của `try-catch-finally` như sau:

```typescript
try {
    // Khối mã có thể ném ra lỗi
} catch (error) {
    // Khối mã xử lý lỗi
} finally {
    // Khối mã luôn được thực thi
}
```

### Chi Tiết
- **Khối try**: Chứa mã có khả năng ném ra lỗi.
- **Khối catch**: Chứa mã xử lý lỗi nếu có lỗi xảy ra trong khối try.
- **Khối finally**: Chứa mã mà bạn muốn chắc chắn thực thi. Khối này sẽ được thực hiện bất kể có lỗi hay không.

## Ví Dụ
### Ví dụ 1: Sử Dụng Cơ Bản
```typescript
function demoFinally() {
    try {
        console.log("Bắt đầu khối try.");
        throw new Error("Có lỗi xảy ra!");
    } catch (error) {
        console.log("Xử lý lỗi: ", error.message);
    } finally {
        console.log("Khối finally luôn được thực thi.");
    }
}

demoFinally();
```
**Kết quả:**
```
Bắt đầu khối try.
Xử lý lỗi:  Có lỗi xảy ra!
Khối finally luôn được thực thi.
```

### Ví dụ 2: Đảm Bảo Dọn Dẹp Tài Nguyên
```typescript
function readFile() {
    let file: any; // Giả sử file là một đối tượng
    try {
        console.log("Mở tệp...");
        // Mã mở tệp có thể ném ra lỗi
        throw new Error("Lỗi mở tệp");
    } catch (error) {
        console.log("Lỗi: ", error.message);
    } finally {
        console.log("Đóng tệp...");
        // Đảm bảo tệp được đóng
    }
}

readFile();
```
**Kết quả:**
```
Mở tệp...
Lỗi:  Lỗi mở tệp
Đóng tệp...
```

## Giải Thích
### Những Cạm Bẫy Thường Gặp
- **Bỏ Qua Khối finally**: Nếu không sử dụng `finally`, bạn có thể bỏ lỡ các thao tác dọn dẹp cần thiết.
- **Ném Lỗi Trong Khối finally**: Nếu bạn ném lỗi trong khối `finally`, nó sẽ ghi đè lên lỗi đã ném trong khối `try`.
- **Sử Dụng Sai Cú Pháp**: Đảm bảo bạn không quên ký tự chấm phẩy hoặc mắc lỗi cú pháp khác.

### Lưu Ý
- Khối `finally` không thể được bỏ qua nếu có lỗi xảy ra trong khối `try` hoặc `catch`.
- Cú pháp này giúp mã nguồn sạch sẽ và dễ bảo trì hơn.

## Tóm Tắt Một Dòng
Từ khóa `finally` trong TypeScript đảm bảo rằng một khối mã được thực thi ngay cả khi có lỗi xảy ra trong khối try, giúp quản lý tài nguyên hiệu quả hơn.