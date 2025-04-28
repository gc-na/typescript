<!--
Meta Description: # Từ Khóa "try" Trong TypeScript: Cách Sử Dụng và Ví Dụ ## Tóm Tắt Từ khóa "try" trong TypeScript được sử dụng để xử lý ngoại lệ, cho phép lập trình v...
Meta Keywords: lỗi, try, dụng, thể, catch
-->

# Từ Khóa "try" Trong TypeScript: Cách Sử Dụng và Ví Dụ

## Tóm Tắt
Từ khóa "try" trong TypeScript được sử dụng để xử lý ngoại lệ, cho phép lập trình viên quản lý các lỗi có thể xảy ra trong quá trình thực thi mã, nâng cao tính ổn định của ứng dụng.

## Tài Liệu
### Mục Đích
Cấu trúc `try...catch` trong TypeScript cho phép bạn thực hiện một đoạn mã và "bắt" các lỗi (exceptions) có thể xảy ra trong quá trình thực thi. Điều này rất hữu ích cho việc xử lý các tình huống không mong muốn mà không làm gián đoạn quá trình chạy của ứng dụng.

### Cách Sử Dụng
Cú pháp cơ bản của cấu trúc `try...catch` như sau:

```typescript
try {
    // Đoạn mã có thể gây ra lỗi
} catch (error) {
    // Xử lý lỗi
}
```

- **Khối `try`**: Chứa mã mà bạn muốn kiểm tra lỗi.
- **Khối `catch`**: Chứa mã để xử lý lỗi nếu có lỗi xảy ra trong khối `try`.

Ngoài ra, bạn có thể sử dụng khối `finally` để thực hiện mã mà luôn được thực thi, bất kể có lỗi hay không:

```typescript
try {
    // Đoạn mã có thể gây ra lỗi
} catch (error) {
    // Xử lý lỗi
} finally {
    // Mã luôn được thực thi
}
```

### Chi Tiết
- Bạn có thể sử dụng nhiều khối `catch` để xử lý các loại lỗi khác nhau.
- TypeScript hỗ trợ kiểm tra kiểu dữ liệu của đối tượng lỗi trong khối `catch`. Bạn có thể định nghĩa kiểu cho biến lỗi để truy cập các thuộc tính cụ thể.

## Ví Dụ
### Ví Dụ Cơ Bản
```typescript
function divide(a: number, b: number): number {
    try {
        if (b === 0) {
            throw new Error("Không thể chia cho 0");
        }
        return a / b;
    } catch (error) {
        console.error(error.message);
        return 0; // Trả về 0 nếu có lỗi
    }
}

console.log(divide(10, 2)); // Kết quả: 5
console.log(divide(10, 0)); // Kết quả: 0 và in ra "Không thể chia cho 0"
```

### Ví Dụ Với Khối `finally`
```typescript
function readFile(filePath: string) {
    let fileContent: string;
    try {
        // Giả sử có một hàm đọc tệp
        fileContent = readFileSync(filePath);
    } catch (error) {
        console.error("Lỗi khi đọc tệp:", error.message);
    } finally {
        console.log("Hoàn tất thao tác đọc tệp.");
    }
}
```

## Giải Thích
- **Lỗi Không Được Xử Lý**: Nếu không sử dụng `try...catch`, các lỗi không được xử lý sẽ gây ra việc dừng chương trình một cách đột ngột.
- **Bắt Lỗi Đặc Biệt**: Bạn có thể bắt các loại lỗi cụ thể bằng cách sử dụng các điều kiện trong khối `catch` để phân loại lỗi.
- **Thao Tác Bên Ngoài**: Nếu bạn có các thao tác bên ngoài (như gọi API), việc sử dụng `try...catch` là rất quan trọng để đảm bảo rằng ứng dụng của bạn không bị ảnh hưởng bởi những lỗi không mong muốn.

## Tóm Tắt Một Dòng
Từ khóa `try` trong TypeScript giúp xử lý ngoại lệ, cho phép lập trình viên quản lý lỗi hiệu quả, đảm bảo ứng dụng hoạt động mượt mà và ổn định.