<!--
Meta Description: # Từ Khóa "catch" trong TypeScript: Cách Xử Lý Lỗi Hiệu Quả ## Tóm Tắt Trong TypeScript, từ khóa `catch` được sử dụng để xử lý các lỗi xảy ra trong cá...
Meta Keywords: lỗi, catch, dụng, error, khối
-->

# Từ Khóa "catch" trong TypeScript: Cách Xử Lý Lỗi Hiệu Quả

## Tóm Tắt
Trong TypeScript, từ khóa `catch` được sử dụng để xử lý các lỗi xảy ra trong các khối mã có thể phát sinh ngoại lệ, giúp người lập trình quản lý và xử lý các tình huống không mong muốn một cách hiệu quả.

## Tài Liệu
### Mục Đích
Từ khóa `catch` được sử dụng trong câu lệnh `try-catch` để bắt và xử lý các lỗi. Điều này cho phép lập trình viên kiểm soát luồng thực thi của chương trình và xử lý ngoại lệ một cách an toàn.

### Cách Sử Dụng
Cấu trúc cơ bản của câu lệnh `try-catch` trong TypeScript như sau:

```typescript
try {
    // Khối mã có thể phát sinh lỗi
} catch (error) {
    // Xử lý lỗi
}
```

- **Khối try**: Đây là nơi bạn đặt mã mà bạn nghĩ có thể gây ra lỗi.
- **Khối catch**: Khi một lỗi phát sinh trong khối try, điều này sẽ chuyển điều khiển đến khối catch, nơi bạn có thể xử lý lỗi.

### Chi Tiết
- Bạn có thể tùy chọn sử dụng các khối finally để thực hiện mã không phụ thuộc vào việc có lỗi hay không.
- Kiểu của biến `error` trong khối catch có thể là bất kỳ loại nào, nhưng thông thường được định nghĩa là `any` hoặc `Error` để tận dụng các thuộc tính của đối tượng lỗi.

## Ví Dụ
### Ví Dụ Cơ Bản
Dưới đây là một ví dụ đơn giản minh họa cách sử dụng `catch` để xử lý lỗi:

```typescript
function divideNumbers(a: number, b: number): number {
    try {
        if (b === 0) {
            throw new Error("Không thể chia cho 0");
        }
        return a / b;
    } catch (error) {
        console.error(error.message);
        return NaN; // Trả về NaN nếu có lỗi
    }
}

const result = divideNumbers(10, 0); // Kết quả sẽ là NaN và thông báo lỗi sẽ hiển thị
```

### Ví Dụ Khác
```typescript
async function fetchData(url: string) {
    try {
        const response = await fetch(url);
        if (!response.ok) {
            throw new Error("Lỗi khi tải dữ liệu");
        }
        const data = await response.json();
        return data;
    } catch (error) {
        console.error("Đã xảy ra lỗi:", error.message);
    }
}

fetchData("https://api.example.com/data");
```

## Giải Thích
- **Cảnh báo**: Không nên sử dụng từ khóa `catch` mà không có khối `try`, vì điều này sẽ dẫn đến lỗi cú pháp.
- **Hiểu biết về lỗi**: Đảm bảo bạn hiểu cấu trúc của ngoại lệ và cách xử lý chúng. Không phải mọi lỗi đều có thể được xử lý theo cách giống nhau.
- **Hiệu suất**: Việc sử dụng `try-catch` có thể ảnh hưởng đến hiệu suất của ứng dụng nếu không được sử dụng một cách hợp lý, vì vậy hãy chỉ sử dụng chúng khi thật sự cần thiết.

## Tóm Tắt Một Dòng
Từ khóa `catch` trong TypeScript cho phép bạn xử lý các lỗi phát sinh từ khối mã, giúp bảo vệ ứng dụng khỏi sự cố không mong muốn.