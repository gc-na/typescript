<!--
Meta Description: # Từ Khóa "unique" trong TypeScript: Tạo Ra Các Kiểu Dữ Liệu Độc Nhất ## Tóm Tắt Trong TypeScript, từ khóa `unique` không phải là một cú pháp chính th...
Meta Keywords: kiểu, nhất, liệu, độc, dụng
-->

# Từ Khóa "unique" trong TypeScript: Tạo Ra Các Kiểu Dữ Liệu Độc Nhất

## Tóm Tắt
Trong TypeScript, từ khóa `unique` không phải là một cú pháp chính thức, nhưng ý tưởng về việc tạo ra các kiểu dữ liệu độc nhất (Unique Types) là một phần quan trọng trong việc tối ưu hóa loại dữ liệu và tránh xung đột kiểu.

## Tài Liệu
### Mục Đích
Các kiểu dữ liệu độc nhất trong TypeScript cho phép lập trình viên định nghĩa các kiểu mà chỉ có một giá trị duy nhất. Điều này giúp tăng cường tính mạnh mẽ và an toàn của mã nguồn bằng cách đảm bảo rằng các giá trị không thể bị lẫn lộn với nhau.

### Cách Sử Dụng
Để tạo ra kiểu dữ liệu độc nhất, bạn có thể sử dụng từ khóa `type` cùng với một giá trị cụ thể. Dưới đây là cách thực hiện:

```typescript
type UniqueString = string & { __unique: void };
```

Khi bạn định nghĩa một kiểu như vậy, bạn có thể tạo ra các giá trị độc nhất bằng cách sử dụng một hàm:

```typescript
function createUniqueString(value: string): UniqueString {
    return value as UniqueString;
}

const myUniqueValue = createUniqueString("Hello World");
```

### Chi Tiết
- **Kiểu Dữ Liệu**: Kiểu độc nhất có thể được sử dụng cho các giá trị đơn giản như chuỗi và số.
- **Bảo Vệ An Toàn**: Sử dụng kiểu độc nhất giúp ngăn chặn các lỗi do việc sử dụng nhầm kiểu dữ liệu.

## Ví Dụ
Dưới đây là một số ví dụ cơ bản về cách tạo và sử dụng kiểu dữ liệu độc nhất:

### Ví Dụ 1: Tạo Kiểu Dữ Liệu Độc Nhất
```typescript
type UserID = string & { __brand: 'UserID' };

function createUserID(id: string): UserID {
    return id as UserID;
}

const userId = createUserID("12345");
```

### Ví Dụ 2: Sử Dụng Kiểu Dữ Liệu Độc Nhất
```typescript
function getUser(userId: UserID) {
    console.log(`Fetching user with ID: ${userId}`);
}

getUser(userId); // Đúng
// getUser("12345"); // Lỗi: Argument of type 'string' is not assignable to parameter of type 'UserID'.
```

## Giải Thích
### Những Cạm Bẫy Thường Gặp
- **Không Sử Dụng Đúng Kiểu**: Một trong những lỗi phổ biến là sử dụng kiểu dữ liệu độc nhất mà không thông qua hàm tạo, điều này có thể dẫn đến lỗi kiểu.
- **Khó Duy Trì**: Khi sử dụng kiểu độc nhất, bạn cần phải chắc chắn rằng mọi giá trị đều được tạo ra thông qua hàm, nếu không có thể gây nhầm lẫn.

### Ghi Chú Bổ Sung
- Kiểu dữ liệu độc nhất hữu ích trong nhiều tình huống, đặc biệt là khi làm việc với các mã định danh hoặc khóa.
- Hãy lưu ý rằng việc tạo kiểu dữ liệu độc nhất có thể làm tăng độ phức tạp trong mã nguồn, vì vậy chỉ nên sử dụng khi thật sự cần thiết.

## Tóm Tắt Một Dòng
`unique` trong TypeScript cho phép lập trình viên tạo ra các kiểu dữ liệu độc nhất, giúp bảo vệ an toàn kiểu và tránh xung đột trong mã nguồn.