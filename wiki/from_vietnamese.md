<!--
Meta Description: # Từ Khóa "from" trong TypeScript: Hướng Dẫn Chi Tiết và Ví Dụ ## Tóm Tắt Từ khóa `from` trong TypeScript thường được sử dụng trong ngữ cảnh nhập khẩu...
Meta Keywords: các, module, from, trong, nhập
-->

# Từ Khóa "from" trong TypeScript: Hướng Dẫn Chi Tiết và Ví Dụ

## Tóm Tắt
Từ khóa `from` trong TypeScript thường được sử dụng trong ngữ cảnh nhập khẩu (import) các module hoặc thư viện từ các file khác, cho phép lập trình viên tổ chức và tái sử dụng mã nguồn một cách hiệu quả.

## Tài Liệu
### Mục Đích
Từ khóa `from` giúp xác định nguồn gốc của module hoặc thành phần mà bạn muốn nhập vào file hiện tại. Điều này rất quan trọng trong việc xây dựng các ứng dụng lớn và phức tạp trong TypeScript.

### Cách Sử Dụng
Cú pháp cơ bản để sử dụng `from` trong câu lệnh import như sau:

```typescript
import { TênThànhPhần } from 'đường-dẫn';
```

- **TênThànhPhần**: là tên của thành phần mà bạn muốn nhập (có thể là hàm, lớp, biến, v.v.).
- **đường-dẫn**: là đường dẫn đến file chứa module mà bạn đang nhập.

### Chi Tiết
- `from` có thể được sử dụng trong nhiều ngữ cảnh khác nhau, bao gồm nhập khẩu các module bên ngoài và các module do chính bạn tạo ra.
- Bạn có thể nhập nhiều thành phần từ cùng một module bằng cách sử dụng dấu phẩy để phân tách:

```typescript
import { ThànhPhần1, ThànhPhần2 } from 'đường-dẫn';
```

- Ngoài ra, bạn cũng có thể nhập tất cả các thành phần của một module bằng cách sử dụng cú pháp `* as`:

```typescript
import * as tênBiến from 'đường-dẫn';
```

## Ví Dụ
### Ví Dụ Cơ Bản
```typescript
// File: math.ts
export function add(a: number, b: number): number {
    return a + b;
}

// File: app.ts
import { add } from './math';

const result = add(5, 3);
console.log(result); // Output: 8
```

### Nhập Tất Cả Các Thành Phần
```typescript
// File: utilities.ts
export function log(message: string): void {
    console.log(message);
}

export function error(message: string): void {
    console.error(message);
}

// File: app.ts
import * as utils from './utilities';

utils.log('This is a log message');
utils.error('This is an error message');
```

## Giải Thích
### Những Cạm Bẫy Thường Gặp
- **Đường Dẫn Sai**: Đảm bảo rằng đường dẫn đến file là chính xác. Nếu không, TypeScript sẽ không thể tìm thấy module và sẽ báo lỗi.
- **Tên Thành Phần Không Chính Xác**: Kiểm tra kỹ tên thành phần bạn đang nhập khẩu. Tên phải khớp chính xác với tên đã xuất khẩu trong module gốc.
- **Kết Hợp Các Module**: Trong trường hợp bạn cần nhập khẩu nhiều module từ nhiều file khác nhau, hãy chắc chắn rằng bạn quản lý các đường dẫn một cách hợp lý để tránh xung đột.

## Tóm Tắt Một Dòng
Từ khóa `from` trong TypeScript giúp nhập khẩu các thành phần từ các module khác, cho phép tổ chức mã nguồn hiệu quả và tái sử dụng trong các ứng dụng lớn.